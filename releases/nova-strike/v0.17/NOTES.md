# Nova Strike v0.17 notes: the two owner look points (Khaled 2026-10-17 on v0.16)

Owner captures (his phone, v0.16): owner/khaled_title_v016.jpg, owner/khaled_play_v016.webp.

## R1 "in picture 1 the background looks pixeled" (title screen)

**Root cause: the title's moving background is a half-size, low-bitrate video, and v0.16 had no full-size copy.**
- The title shows a still (`assets/ui/title_still.webp`) and plays a 10 s loop over the whole screen on top of it
  (`game/ui/title.gd` CLIP -> `ui_screen.gd video_over`, full-rect, `expand`). Once the loop plays, only the loop is seen.
- The still is fine: the HD pack twin `hd/assets/ui/title_still.webp` is 1536x2752, lossless import (compress/mode=0).
- The loop is not: `assets/ui/video/title_loop.ogv` = Theora **540x966, 426 kbit/s** (ffprobe). `HDPack.path()` looked for
  `hd/assets/ui/video/title_loop.ogv`, found none (only `ending_once.ogv` had an HD twin) and fell back to the APK copy.
  Covering a 1344x2992 phone screen (Khaled's Pixel) scales it ~3.1x: blocky edges + compression blocks in the clouds
  and station = exactly the pixelation in his capture.
- The source is not the problem: the Kling master `art/production/scn_ui/title_clip/asset_foQM9ahE5Hj7nJAWG5rMpUCN.mp4`
  is 1076x1924 at 14.7 Mbit/s (frame match: shipped loop = this clip forward + reversed, mean frame diff 2.3-4.2 / 255).
  The Home screen hit the same softness in v0.4 and stopped playing its clip (`home.gd` BG_CLIP note); the title kept its.
- Not the cause: texture compression / size limits (every texture import is lossless since v0.13 S6, guarded by
  restore_lossless_tests), viewport stretch (the still is sharp in the same screen).

**Fix (full quality, rules 3.45):** the master re-encoded at its own size, forward + reversed (same 10 s seamless loop),
Theora q9 -> `hd/assets/ui/video/title_loop.ogv` (1076x1924, 9.7 Mbit/s, 7.7 MB, in the HD pack; the APK copy stays as
the before-pack fallback). Measured against the master (SSIM, 121 frames, both scaled to 1076x1924): v0.16 clip 0.899,
v0.17 clip 0.990. Precedent for a full-size clip on phones: `hd/assets/ui/video/ending_once.ogv` (1080x1920) ships since v0.10.

## R2 "the enemies look greyed out" (in play)

**Root cause: a flat grey added to every dark part of every enemy, from v0.10 LOOK-01.**
- The S1-S6 enemies are dark chrome / obsidian paintings with ruby gems (`assets/enemies/v05/*.png`).
- `EnemyFinish.V10_S1` (merged for every sector since v0.10 M4) sets `hull_lift 1.0`, `hull_amb (0.50, 0.51, 0.56)`, and
  the finish shader does `base += hull_amb * hull_lift * (1 - smoothstep(0, 0.40, luma(base)))`: every hull pixel darker
  than luma 0.4 (most of these paintings, rubies included) gets up to +0.5 neutral grey. It was added to lift hull planes
  off the night-blue Lantern Road plate by luminance (look_ring gate), and it does that by turning obsidian and ruby grey.
- Measured on the source paintings with that exact formula (offline + `tests/v17/look_v017_tests.gd` on v0.16 values):
  S1 mean saturation 0.27-0.48 -> 0.16-0.21 (about half), luminance 0.19-0.30 -> 0.48-0.54; across all 30 S1-S6 roles
  saturation kept 0.40-0.83, ruby share kept 0.36-0.78.
- Not the cause: sector tint (white for the restyled S roles since v0.9 r8), texture compression (lossless).
- On-screen check (each sector's real CombatWorld, mission N.03, its five enemies held still, PC render job 1017203342-9eea,
  `tests/v17/enemy_colour_capture.tscn` + `pipeline/v17_enemy_colour.py`; enemy pixels = frame with minus frame without the
  enemies; 30 enemies x 2 tiers): v0.16 kept **46 % (high) / 57 % (low) of the paintings' ruby-red share** and showed them at
  **luminance 0.50 vs 0.26 painted** = the milky pink-white hulls in Khaled's capture.

| finish variant / tier | ruby-red share kept | luminance on screen (painted 0.26) |
|---|---|---|
| v0.16 grey lift / high | 0.46 | 0.50 |
| v0.16 grey lift / low | 0.57 | 0.49 |
| no lift / high | 1.02 | 0.34 |
| gain 0.5 / high | 1.08 | 0.35 |
| **gain 1.0 / high (v0.17)** | **1.13** | **0.37** |
| gain 1.0 / low (v0.17) | 1.08 | 0.35 |
(mean saturation reads > 1 on every fixed variant because the enemies' own red glow and bloom are in the measured pixels.)

**Fix:** `EnemyFinish.V10_S1`: `hull_lift 0.0` (the grey lift off) and a new `hull_gain 1.0`: the darkest hull values are lifted
by SCALING them (`base *= 1 + hull_gain * (1 - smoothstep(0, 0.40, luma))`, at most x2 at black), which keeps hue and
saturation. Picked over "no lift" and "gain 0.5" on the side-by-side board: same colours, and the chrome still reads off the
darkest plates (S5 Crownfall). Silhouettes, hitboxes, the selective warm rim, glows and bullets are unchanged.

## Proof
Real game renders on the studio PC (RTX 5080, Compatibility renderer, HIGH tier), phone sizes tall + short; boards in `proof/`.
- **Title (R1):** `tests/v17/title_capture.tscn`, jobs 1019123056-4f29 (1080x2400) and 1019123057-e2f4 (1080x1920): BEFORE =
  the APK clip only (HDPack.force_light: v0.16's 540x966 clip, `clip=res://assets/ui/video/title_loop.ogv playing=true`), AFTER =
  through the HD pack (`clip=res://hd/assets/ui/video/title_loop.ogv playing=true`). (The first v0.17 title capture showed no
  BEFORE clip: the capture added its first title while the root was still setting up, fixed in c5a7c42.)
- **Enemies (R2):** 4 real missions (1.02, 2.02, 3.02, 5.02) tall 540x1170 (job 1017203414-54d0) + short 540x960
  (1017203342-2587), v0.16 finish vs v0.17 finish; 6 sectors' five enemies held still in their real combat scene
  (1017203342-9eea). On-screen colour check vs the paintings: table above (ruby share kept 0.46 -> 1.13, luminance 0.50 -> 0.37,
  painted 0.26).
- **BLIND JUDGE (look-judge, pairwise, rules 3.36/3.39, no key):** 16 / 16 pairs prefer v0.17 (title 2/2 at confidence 5;
  waves 8/8, confidence 3-5; sectors 6/6 at 5, "matches the paintings" 6/6). Judge notes: v0.16 title = compression blocks and
  smear; v0.17 title slightly grainy, no harm. v0.16 enemies milky/lavender, lose their silhouette (E6, L13); v0.17 dark chrome +
  ruby, "a touch lighter than the paintings", no crushed blacks or oversaturation. Stills only: the 4.5-in-motion bar is not
  claimed. Not colour issues, seen on both sides (later work): player lightning covers enemies (wave 3), formation overlap (wave 5).

## Outside review 8 (GPT, 2026-10-19): Nova items
- **No-light pack gate fresh-phone acceptance:** carried to THIS build: Test Lab fresh-install run on the released v0.17 build
  (after the 10:00 Riyadh minutes reset); result in RELEASED.md.
- **Pack reuse across versions (content_hash, notice pack-same-art):** tried as a side lane (wip/nova-strike/packreuse);
  outcome in RELEASED.md (merged only if its tests passed in time; else carried to the next full version).
- **iPhone HD-gate freeze-watchdog receipts:** triaged, `FREEZE_TRIAGE.md`. **Confirmed, not fixed here:** all 42 reports
  (builds 0.10-0.16; iPhone 11-55 s, median 44 s) are (b) recovered real main-thread freezes, not a deliberate wait (the
  watchdog only fires when no frame runs for 5 s; the gate's download/verify work is capped at 6 ms a frame) and not proven
  blocked play (no "killed" report; where events exist players went on). Cause: the first-launch shader warm the gate starts
  (`game/boot_warm.gd _one`: loads + instantiates the whole combat scene and its first draws compile every shader in one go,
  x3 crafts). Not in this two-fix look release (job scope); it is the top carried item for the next full version
  (spread the warm over frames / threaded load + phase crumbs + a "no gate frame > ~250 ms" test).

Honest note on the art:
- 2 finished look item(s) without a passing look check yet
- 5129 art files still use the earlier look without a passing look check
- the game's look settings are not locked yet
- parts of the look are still below our own 4.5 bar; it keeps improving in the next versions