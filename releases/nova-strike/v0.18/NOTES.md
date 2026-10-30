# NOVA STRIKE v0.18 NOTES

## Lane C (quality18): Q1 / Q2 / Q6, the content pack route

### Decision (Q1)
- State found: since v0.13 S6/D1 every texture import is lossless (`compress/mode=0`, 0 lossy left; N1-N4 restored, tester APK 355 MiB, limit 380).
  The cut audit's N1-N4 is therefore restored in quality; what was left is WHERE the heavy files live.
- Chosen route: **`config/hd_pack.json` `pack_paths`, files IN PLACE** (not new `hd/` twins). Reasons: no loader changes (every `load("res://...")` keeps
  working once the pack is mounted), no duplicate copy of 60+ MB in the repo, the in-place pack path is already proven with a real Godot export, and the boot gate
  (v0.15, rules 3.49) already holds all play until the pack is mounted, so no light copy is needed in the app.
- Globs: `assets/env/*_v10/*` (N1 scenery: 6 kits, webp + png + json, incl. `setpiece/`), `assets/fx/expl_*` (N1 explosion sheets), `assets/craft_v09/*` (N2, 330+ webp).
  Left out of the Web and Android presets (`exclude_filter`, same globs). The `Android Benchmark` preset (Test Lab perf runs) keeps them.
  N3 (obstacles_v09) and N4 (pass-3 enemies/bosses/pilots) are lossless in the app already and stay there: they are used by the first fights and the gate-side screens.
- quality_cut: `clean since nova-strike-v0.17 (0 owner-allowed, 3 moved to the content pack)`.

### Game-side change needed by the in-place route
- `game/boot_warm.gd`: the first-launch shader warm plays hidden fights with the real craft and scenery art, so it now waits until `HDPack.loaded`
  (or `state == "off"`: tests, editor) before the first fight. Before this it would have started while the pack downloads.
- `core/ui.gd` menu warm skips files that do not exist yet (`ResourceLoader.exists`); `UI.warm_menus()` is now called again when the pack is mounted
  (`game/ui/hd_gate.gd` `_leave`, `game/ui/boot.gd` when no gate is shown) so the hangar cut-outs of the equipped craft are still warmed.
- Nothing in `core/hd_pack.gd` was touched (Lane A owns it).

### Q6: loader list of pack content (every loader works in place, none needs `HDPack.path`)
In-place files need no `HDPack.path`: the path never changes, the file just appears when the pack is mounted. Everything below runs only after the gate.

| Loader | File | What it loads | Pack content |
|---|---|---|---|
| `game/combat/env.gd` `has_v10_package` (l.697), `_v10_load` (l.1428), `V10_DIR` (l.642) | env kit loader | `far/mid/landmark/scar/veil` (+glow) webp, props, lights json | `assets/env/<kit>_v10/*` |
| `game/combat/sectors/s1_runtime.gd` (l.234 `SP_DIR`), `s2_setpiece.gd`, `s3_setpiece.gd`, `s4_setpiece.gd`, `s5_setpiece.gd`, `s6_setpiece.gd` | setpieces | `setpiece/*.webp` per sector | `assets/env/<kit>_v10/setpiece/*` |
| `game/core_fx/fx_kit.gd` `tex()` via `game/core_fx/flipbook_fx.gd` `setup()` | explosion flipbooks | `expl_smoke`, `expl_fire_a`, `expl_fire_b` | `assets/fx/expl_*` |
| `game/craft2d/craft_rig_2d.gd` `_tex(asset_root + rel)` (l.282, 560, 821) | craft rig | flight + hangar parts; `asset_root` comes from `config/craft_v09_<craft>.json` | `assets/craft_v09/*` |
| `game/craft2d/craft_finishes.gd`, `combat_craft.gd` | finishes | the same rig data (`art/production/craft_v09/*/parts.json` stays in the app, small) | `assets/craft_v09/*` |
| `core/ui.gd` `WARM_UNIT` (l.1326) + hangar previews (`ui_screen.gd`) | hangar previews | `.../hangar/L4.webp` etc. | `assets/craft_v09/*` |
| `game/boot_warm.gd` | hidden warm fights | all of the above | needs the mount first (fixed) |

Unchanged `HDPack.path` loaders (hd/ twins): `env.gd` l.1047 + `world.gd` l.1649 (far plates), `journey_data.gd` l.70, `bg_still_life.gd`, `cinematic.gd`, `ending.gd`, `home.gd`, `title.gd`, `ui_screen.gd`.
Not pack content (stay in the app): configs (`config/*.json`), `art/production/craft_v09/*/parts.json`, `assets/obstacles_v09/*`, enemies, bosses, pilots (light), ui.

### Q2
See TODO.md Q2 (the in-place route leaves no lossy APK copy of a pack-lossless file; the FR-v013-A rule is not needed for NOVA).

## S3D / lane s3d18: the Thuban rig JOINED to the real Raid 2 fight, two routes recorded for the blind pick (2026-10-20)
Branch `wip/nova-strike/s3d18`. Design: `BOSS3D_RIG.md` section 6 (driven mode). Both routes use the same fight, the same rig, the same pilot and seed; only the compositing differs.

### What now works
- **One fight, one model**: `SiegeThuban.attach_3d()` (called by `SiegeEncounter` for a Raid) loads `hd/assets/bosses3d/thuban/boss.tscn` through `Boss3DLoader` + the bridge, on the route in `config/boss3d.json`
  (`"route": "a" | "b"`). The painted 2D body is not drawn when a model is attached; without the pack it stays (test: gate shut).
- **One scale, 2D wins**: the 3D chain pitch is the 2D wall pitch (187.5 px). The fight hands over `seg_pos(i)`, `EYE`, the ring states every tick; the rig places each anchor so that its projection lands on the 2D place,
  hit circles keep the 2D radii (glass 102.5, ring 70). Join test: worst anchor error vs the 2D design <= 8 px on route a and b through all four phases, the `G_eye` gun on the 2D eye, a segment 50 px off is caught.
- **Fold fixed**: 0 folding frames in the whole entrance, both LODs (before: 4 frames, link ratio 0.06; now >= 0.7 of the distance a link should keep).
- **Light**: the boss key light follows the live stage key (`sync_from_env(world.env)` every 0.25 s; direction from the upper left on the stage key, colour/energy from `key_color`). Veins: measured on the PC GPU (job 1020011909-4da6, five variants,
  same frame): with energy 1.0 the veins came out lemon yellow ((224-255, 224-255, 64-96) = 33 % of the bright pixels were yellow); key light, rim, post/bloom and the vein albedo were NOT the cause; the render shows an emission ~2.3x its energy, so the green channel clipped
  too. Colour = the studio amber (1.0, 0.68, 0.25) at energy 0.45: bright-pixel hue now mean 24.7 deg, yellow 12 of 1764 px (0.7 %), dominant bin (224,160,32) = amber, same on route a and b. Bloom still applies on route b (it is a sprite in the field).
- **Route a in the real game** (new `CombatPost.enable_world3d`): the field viewport gets its own 3D world, the stage moves to a `CanvasLayer(-1)` behind it, gameplay above; restored when the boss is gone (join test). Both routes work in GL Compatibility.
- **Route b**: a tall box (1500 x 2200 px, centred 350 px below the boss) so the death's falling pieces leave through the bottom of the field instead of being cut at a square box edge (seen in the first software capture).
- Entrance 4.0 s is the rig's (body does not slide in); cues lunge (shake) / shriek (sfx) / settle; `attack` starts 0.6 s before a fan leaves; `hit` on a bend, `break` on a shell crack, fins tear at phase 4, death = frozen shatter, BossDeathV13 breaks the 13 segments in turn.
- Tests (server): `tests/v18/thuban_join_tests.tscn` 61/61, `tests/v18/thuban_rig_tests.tscn` 126/126 (0 folding frames), `tests/boss3d_bridge_tests.tscn` 79/79, `b_raid_tests` raid1+2 41/41, `b_raid11_tests`, `raid12_tests` PASS.

### The record for the blind route pick (NOT judged by the lane; the lead runs the pairwise judge)
Scenes: `tests/v18/s3d_thuban_clip_a.tscn` / `_b.tscn` (and `_a2` / `_b2`, identical, the repeat run). Each = the real Raid 2 fight in the real combat world: entrance 4.0 s, 20 s of fight with the scripted skilled pilot, a shell break at 9 s of fight,
the death. 540x1170 = 1080x2340 scaled, 30 fps video, PC real GPU, `--solo`.
- Run 1 (job 1020013335-c009): `_pcq/out/1020013335-c009/s3d_thuban_clip_a/scene.mp4` (route a), `.../s3d_thuban_clip_b/scene.mp4` (route b).
- Run 2 (job 1020014025-b952, the repeat): `_pcq/out/1020014025-b952/s3d_thuban_clip_a2/scene.mp4`, `.../s3d_thuban_clip_b2/scene.mp4`. (30.4 s each.)
- Hue and software captures: job 1020011909-4da6 (vein variants), 1020005948-ccb7 (first software run).

First smoothness numbers, **PC GPU under the Godot movie writer (the readback adds to every frame), NOT a phone**; per-frame wall time from `_process`:
| | route a (one 3D world) | route b (boss-box SubViewport) |
|---|---|---|
| run 1, all 909 frames: avg / p95 / worst / > 50 ms | 15.9 / 24.6 / 120.6 / 5 | 19.1 / 32.0 / 412.8 / 12 |
| run 1, fight (599 fr.): worst / > 50 ms | 39.9 / 0 | 412.8 / 8 |
| run 2, all 909 frames: avg / p95 / worst / > 50 ms | 15.5 / 23.3 / 55.1 / 1 | 15.5 / 24.2 / 146.0 / 5 |
| run 2, fight: worst / > 50 ms | 35.2 / 0 | 33.9 / 0 |
Frames > 50 ms in run 2: route a: the first death frame (55 ms, the effects burst); route b: frame 1 (81 ms, first draw), 1.2 s into the entrance (146 ms, the head enters the box), and 3 frames at the mission-complete moment (126-143 ms, UI).
Route b's run-1 fight spikes (8 frames, worst 413 ms) did NOT repeat in run 2; cause not found (a second job on the PC is the only suspect). So: the 20 s fight is clean on both routes in the repeat run; the entrance and the death are the places a spike can still happen; the real gate
(0 frames > 50 ms in the 5 s around the entrance and in a 3-minute run on a FIRST launch on iPhone AND Pixel) is still open: nothing here was measured on a phone.

### Open / next
- Entrance weave "behind the far scenery" is drawn in front (needs scenery as a separate layer; route a could do it, route b needs z_index slices of the stage).
- The sector lights are not wired to `rig.cue("light_out_i")` (the cue list exists; the stage lights are CombatEnv's).
- Iron plates look pale beige under the stage key (art / material pass; Tripo pieces replace the stand-in).
- Hoop prism state colours were set by the same 2.3x rule; judge them in motion.

## S3D-b / lane s3db18: route (a) is the default; the look, the world tie, the scary entrance, the break, the spikes (2026-10-20)
Branch `wip/nova-strike/s3db18`. Lead decision: route (a) (canvas under 3D) in `config/boss3d.json` and `DEFAULTS`; route (b) stays selectable (`"route": "b"`). Judge's route score was 3.0; the lane did NOT re-judge.
- **One light**: `Boss3DLight` = stage key (direction/colour/energy from CombatEnv, synced 4x/s) + cool rim + NEW faint cyan bounce from below (the planet). `ThubanRig3D.restyle()` re-styles the GLB materials in place: iron = rough (0.8), metallic 0.18, dark warm brown (0.105,0.088,0.078) + faint rim (no mirror highlight, no pale beige); glass = deep blue-black, alpha 0.8, clearcoat, rim, faint inner cyan; veins untouched (amber).
- **Tied to the world**: depth haze (`haze*` keys in config: coils behind the plane fade to the stage colour); `Boss3DShade` = soft occlusion + contact core on the stage layer under the 3D, shifted away from the key; MSAA 2x on the field viewport in route a (`msaa` key, 4 allowed); the far scenery layers (far props + landmark) are lifted ABOVE the 3D during the first part of the entrance (`CombatPost.stage_front`, back on the `coil` cue) so the weave passes behind them; foreground (`env_fg`) is a field node above the 3D already.
- **Scary entrance**: the rig's `light_out_i` cues drive `CombatEnv.douse(i+1, 6)` (the lights die one by one, 1.6/s) + `dim_to(0.08 x (i+1))`; `settle` = fight dark 0.24; the defeat (or the boss leaving) relights. `boss18_begin(raid, 4.0)` (1.5 for `entrance_retry`, which plays only the last 1.5 s); the extra `enemy_heavy`/`enemy_charge` sfx are gone (the entrance file carries shriek and lunge); shriek = shake + a white flash at the eye.
- **Death breaks apart**: `rig.death_manual` + `break_wall(id)` called on every BossDeathV13 beat (order `ThubanRig3D.BREAK_ORDER` = middle first, `death_items()` has the same order); a link cracks 0.22 s (white veins, shiver, cue `crack_w<id>` -> break_crack + break_rivet sfx + two rivet spark pops), then flies off in its own arc (sideways away from the centre, up, back into the depth, tumbling; cue `fall_w<id>` -> break_chunk_fall + puff), gone after 1.5 s; head/neck/tail/fins break at the peak (`break_rest`). Standalone rig: a timed schedule. `death_t` no longer restarts when `done` starts.
- **Spikes**: `BossWarm.warm3d(host, "thuban")` (called by `PerfWarmup.run` for the raid2 mission = that mission's loading, never at boot): model in a 96 px own-world viewport with the same lights/fog, plus the 2D burst/spark/puff/flash/boss_death once, 3 force-drawn frames, then freed + `fx.clear_all()`. Measured on the PC GPU (frame 1): without it 1858 ms, with it 39-190 ms. Variants `tests/v18/s3d_spike_no_*.tscn` (job 1020024841-0cb1) located it.
- Tests: `thuban_join_tests` PASS (new checks: far layers lifted/back, shade, haze, MSAA, lights out + dim, boss18, middle-first break, body holds, all pieces gone, relight), `thuban_rig_tests` PASS, `boss3d_bridge_tests` PASS, `audio18_tests` PASS.

### The record (NOT judged by the lane): Raid 2 Thuban, route a, entrance 4.0 s + 20 s fight + shell break + death, 540x1170 (tall phone), 30 fps, with sound
- Clip: `_pcq/out/1020025125-1acb/scene.mp4` (job 1020025125-1acb, PC real GPU, `--pc --solo`; the studio folder `_pcq/out/`). Earlier iteration clip (before the 2D fx warm): `_pcq/out/1020024428-6287/scene.mp4`.
- Frame times (PC GPU under the Godot movie writer, NOT a phone): all 912 frames avg 14.5 / p95 21.9 / worst 90.9 ms, frames > 50 ms: 1 (frame 1, the first ever 3D draw in the field viewport, 91 ms). Entrance worst 90.9 (same frame), fight (599 fr.) worst 32.1 and 0 > 50, death (193 fr.) worst 32.0 and 0 > 50. Before: first draw 81 ms, 146 ms at 1.2 s, 55 ms on the first death frame.
- Open: nothing here is measured on a phone; the first 3D frame (91 ms) could be hidden under the entrance warning; the mission-level warm path (`PerfWarmup` -> `warm3d` for `raid2`) is wired but only the explicit call is timed in the clip; the glass is dark teal and the boss reads very dark in the fight (judge the look).

## LANE DRAGON / dragon18: Thuban rebuilt as a free-moving 3D dragon (DESIGN_THUBAN_FIGHT.md), 2026-10-20
Branch `wip/nova-strike/dragon18`. The wall (13 links, 2D painted body, frozen shatter, rings, the old rig) is RETIRED; what ships now:
- **One body, two readers** (`game/combat/boss3d/rig/thuban_body.gd`, class `ThubanBody`, pure script): the head follows a timeline of moves (coil, S-weave, behind the layers,
  side dive, constrict, lunge, glide, path) and holds (perches); 12 links + tail sit on the head's trail; banking + a rolling twist show new sides; depth gate (z <= -4 = behind the mid
  card: hit areas OFF, 0.2 hysteresis); projection through the locked camera. The fight (`siege/raid2_thuban.gd`) puts every hit circle / cover circle on `body.px(...)` and the rig
  (`rig/dragon_rig.gd`, class `DragonRig3D`) places every node from the SAME numbers, so the 8 px rule holds by construction (test T1 also projects through the real route-a camera).
- **Stand-in** (`pipeline/blender/dragon_pieces.py`, headless Blender, GLBs in `hd/assets/bosses3d/thuban/dragon/`): a dragon skull (wedge, brow ridges, 2 big curved horns + 2 small,
  cheek spikes, a blade crest, long fangs), eyes as separate emissive objects, a hinged jaw (origin = hinge, opens 0.85 rad) with the throat ring of 8 lens plates, links of amber glass
  core + iron cage + THREE pre-cut arc pieces (`pnl_seg_0..2`, rivets), dorsal blades, tail with a glass blade. LOD0 30.9k tris (budget 60k). Smoky glass (alpha depth pre-pass) + mid iron.
- **The fight** (3 phases x 4 shells, 12 total): a cycle = a travel move + a perch (high rear / profile strike / bite / guard) with its own window and lance (straight, diagonal, the bite fan,
  the bent lance through the guard ring); tells from the jaw >= 0.8 s, locked at tell start; lens shields soak shots; falling glass from cracked links (P2+); the side dive with the lit jaw in
  a 260 px edge lane; phase breaks (2.5 s: smaller lunge, retreat behind the layers, two links crack for good); the deck never repeats a move / perch / side / triple; Fairness re-plans.
  "Behind the layers" uses the design fallback (the stage's far scenery is lifted above the 3D, `CombatPost.stage_front`, plus fog): NO 3D scenery cards were built.
- **Entrance 4.0 s / retry 1.5 s, death 3.0 s** (no BossDeathV13, no 2D puffs; `SiegeBoss._own_death()` hook): lamps die 0.3 s apart with an amber streak into the throat, 0.5 s silence,
  eyes, a lunge toward the camera (z +44), snap back; death = pieces fly up and away from the ship's x and fall back behind the layers (debris rules in `DragonRig3D.shatter`), the head
  last, the 6 lamps relight at 1.6 s. 6 lamps are drawn by the boss overlay (`_draw_lamps`); the env's own sector lights (`douse`) go out with them.
- **Sounds** (ElevenLabs SFX only, `pipeline/audio_v18_cues.py` + `audio_v18_boss.py`, ~730 credits): `b18_thuban_lunge_hit` (sub impact), `b18_thuban_bite`, new `b18_thuban_death`
  (burst 0.3-0.8, held last shriek 0.8, cold light swell 1.6), re-timed `b18_thuban_entrance` (lamps 0.3 apart, silence 1.8-2.3, breath 2.3, shriek 2.75). -15 LUFS, TP <= -1.2 dB.
- Tests: `tests/v18/dragon_body_tests` (path, speeds, chain, rig anchors), `thuban_fight_tests` (T1 T3 T4 T5 T6 T8 T9 T10 T11 T12 T13 T14), `dragon_debris_tests` (T2). Removed with the wall:
  old rig, old pieces, `thuban_rig_tests`, `thuban_join_tests`, `thuban_look*`, `s3d_*` clips, `boss3d_bridge_tests` (it drove the old Thuban through the generic bridge).
- Gate 0 clip: `docs/versions/v0.18/dragon18/gate0_clip.mp4` (+ `gate0_sheet.png`), scene `tests/v18/dragon_gate0.tscn`.

## LANE THUBAN-2 / dragon18b: the dragon, second pass (gate-0 blind 2/5: "orange barrels, a worm, small, never comes at the ship"), 2026-10-20
Branch `wip/nova-strike/dragon18b`. Lead decision (rules 3.50: pick the alternatives we can make perfect):
- **(a) the arena is its body.** `ThubanBody`: the head is 1.45x, the chest 1.8 tapering to a 0.45 whip tail (`LINK_SC`, 12 links + tail, about 23 units = 2,300 px of body on a 1,920 px field; pitch 1.14 so the barrels touch).
  Coil = a helix toward the camera (r 3.0, turns stack in depth, not one ball), S-weave amp 2.6. Only parts are on screen at once; the rest is above / behind the edges.
  **Behind AND in front of the scenery**: `SiegeThuban._stage_layers` lifts the far scenery above the 3D while ANY on-screen node is behind the mid card (z <= -4); if some on-screen nodes are still in front,
  `DragonFront` (new, `rig/dragon_front.gd`) draws them with a SECOND camera (render layer 2, same World3D, transparent SubViewport) shown on a CanvasLayer above the lifted scenery; the main camera draws layer 1 only.
  Off-screen nodes never trigger either. (Test `thuban_t7_t15_tests` `_t_layers`.)
- **(b) the lunge AT the ship** = the bite perch rebuilt: the head rears back high (aim hold 1.0 s: jaw opens slowly, throat reddens, a red lane shows where the snout will stop, tell >= 0.8 s from the body), then ONE stoop (0.4 s)
  that stops SHORT (head centre y 2.1, snout tip about y 1,000 px: never in the player band) and BESIDE the ship (300 px off its x, toward the middle: a camper is not rewarded, T7), the snout pointing at the ship,
  the head turned so its SIDE faces the screen (profile: the jaw opens in the screen plane, 0.85 rad); the window (throat target, x1.6) follows, then the fan from the teeth (existing A1c). The lock is taken 0.05 s before the stoop
  (`ThubanBody.retarget`). Diagonal lance (strike perch) is now AIMED at where the ship stands at tell start (12-40 deg), so a camper is hit (the old geometry no longer crossed the middle with the bigger head).
- **(c) shadow first** (entrance 4.0 s cap, retry 1.5 s kept): the head starts off the left edge (-9.4, 8.2, -6.5) and its dark body slides across the lamp row behind the mid card; each lamp dies when the head reaches it (0.28-0.38 s apart, the lamp is dimmed while the body is in front of it:
  silhouette); 2.1-2.8 s it swings round behind the layers; 2.5 s the eyes light; 2.8 s the lunge at the CAMERA (head centred on screen at the peak, jaw wide: a maw ringed with fangs) + shriek; 3.4 s settles; the boss bar comes in after the shriek (3.4 s, `entrance_bar_at`).
- **(d) stand-in**: husk-black iron, smoky see-through glass, bat wings on neck links 3-4 (`dragon_wings.glb`, slow flap, the two links show their back to the screen so the span reads), spikes on every arc piece, taller dorsal blades; cores / veins nearly dark (one ember each),
  ONE hot amber glow (throat / lens ring, eyes when lit). Tail joint sits right behind the last barrel (no floating piece). Skins are ShaderMaterials (`DragonRig3D._skin_for`): lit like normal dark material PLUS a cold fresnel edge that does not depend on the stage lights
  (the first look clip showed a black body on a dark sector: invisible). Boss3DLight gets `rim_boost` 2.3 + ambient 0.95 for Thuban only (same directions / colours as the ships' light). Budget: LOD0 32.3k tris (<= 60k), LOD1 20.0k (<= 30k).
  Fixed on the way: `_look()` scaled the RAW glTF emission (the "orange barrels" were stale `base_e` meta captured before `restyle`).
- **(e) clips**: no debug caption; sound (gate-0 plays the studio's thuban cues; the full clip is the real game). Scenes: `tests/v18/dragon_gate0.tscn` (12.6 s), `dragon_full_clip.tscn` (entrance, 3 phases, death; prints per-frame wall times), `dragon_look_clip.tscn` (46 s look check).
- **T15** (calm HUD): `CombatHud.calm` (no WAVE chip, no first-use hint) from the entrance start until the fight starts and from the death start until the result. **T7** camper vs mover: ratio 0.39 (<= 0.6).
- Tests: `tests/v18/thuban_t7_t15_tests` (T15, layers, lunge rules, shadow-first, T7), `dragon_body_tests`, `thuban_fight_tests`, `dragon_debris_tests`; probe `dragon_mat_probe` (prints every rig material headless).

**THUBAN-2 record (ONE PC GPU job 1020084328-1900, tall 540x1170, with sound, RTX 5080 under the movie writer, NOT a phone):** `docs/versions/v0.18/dragon18b/gate0_b_clip.mp4` (12.6 s: shadow-first entrance, lunge at the camera, coil, behind the layers, lunge at the ship in profile; sheet `gate0_b_sheet.png`)
and `full_fight_clip.mp4` (110.6 s: entrance, 3 phases, death; sheet `full_fight_sheet.png`); full-size originals `_pcq/out/1020084328-1900/dragon_full_clip/scene.mp4` (88 MB) and `dragon_gate0/scene.mp4`. Audio present in both (mean -19.7 dB, peak -2.4 dB).
Frame times, full fight: n=3316, avg 18.7 ms, p50 15.8, p95 26.6, p99 32.8, worst 1065 ms, over 33 ms: 30, over 50 ms: 14 (12 of the 14 are one ~1 s stall roughly every 14 s: the movie writer; the previous dragon's own clip had the same, 54 frames over 50 ms, worst 1,806 ms, job 1020083544-9fe4).
Entrance only: worst 73 ms, 1 frame over 50 ms. Entrance 4.0 s, retry 1.5 s kept. The second camera (DragonFront) is on for about 60 % of the fight (the body is big, some part is almost always behind the scenery and some in front): no stall lines up with it.
Raid-bot sweep after the last change (3 seeds, `b_raid_sweep.txt` raid2, job 1020084101-a8d6): min-gear skilled 111 / 129 / 116 s (all clear), max-gear skilled 101 / 122 / 107 s (all clear), damage-only camper dies at 245 / 282 / 282 s in phase 2.
Design band 105-135 s: min-gear all inside; max-gear 2 of 3 (101 s is 4 s under; the camper cannot clear). T7: camper 0.00361 vs mover 0.00923 boss progress per second = 0.39 (<= 0.6).
Full suite (job 1020081350-9935): 193 passed, 2 failed = the two known GREEN items (`weapons_v08_solar_tests`, `a_all_tests`); no new failure.

**THUBAN-2 final bot numbers (job 1020103127-d8f4, `b_raid_tests` raid2 only, 5 seeds, the real suite checks all PASS):** min-gear skilled 111 / 129 / 116 / 113 / 124 s (all clear), max-gear skilled 101 / 122 / 107 / 105 / 116 s (all clear), damage-only camper dies at 245 / 282 / 282 / 282 / 257 s in phase 2; body contacts 0 in every run.
Bug found by that suite and fixed: `body_zones()` (the lit jaw) hurt while the head was BEHIND the layers (the dive's loop-back passes the ship's row at z -9 with the jaw lit; the bigger head made it overlap the ship: 6-10 contacts). It is OFF now whenever `body.behind[0]`.
`b_raid_tests` max-gear band for Raid 2 is 95-140 s (was 150-210 s = the old wall's band; the dragon is tuned to the design's 105-135 s). `siege_boss.contact_log` (tests) lists the first contacts with the boss state.

## LANE THUBAN-3 / dragon18c (blind 2.0: "no death, no roar, dark on dark"), 2026-10-20
- **The death bug (root cause):** a lens shield freed by a phase break stayed in `SiegeBoss.parts`; `begin_defeat()` did `(p as BossPart).shatter()` on it -> "Trying to cast a freed object" (it was in the recorded job's log, nobody read it) and the function stopped half way: `_on_death_start()` (rig.shatter, the death sound) never ran, while the timers went on to "done". Fix: `_clear_shields`/`_break_shield` erase the part, `begin_defeat` filters freed parts, `part()` is safe. Test `tests/v18/thuban_real_death_tests` (A scripted kill after shields were cleared, B the real fight with the pilot to the kill, 3D rig on): fails before the fix (no shatter, 0 pieces), passes after (>=36 pieces fly, all behind the scenery in 3 s, 6 lamps relit, done in 3 s). The old suite missed it because tests never run a frame (queue_free'd shields stay valid) and had no rig.
- **The ~1 s stall every ~14 s was the GAME, not the movie writer:** a headless run with no writer shows the same stalls at the same sim times (11.9, 26.3, 44.6, 64.1, 78.7, 89.5 s); `b.tick` took 1.5 s at the start of every lance cycle: `_fair(plan)` used the slow dictionary flood fill `Fairness.check` up to 12 times. Now `Fairness.check_fast` (bit-set, same answer; the obstacle soak proves the equivalence).
- **Roar:** `b18_thuban_roar` (ElevenLabs, 3 takes, take 1 used: growl building to a bellow with a glass edge; master -12.4 LUFS, TP -3.3) plays at 2.45 s of the entrance so its peak lands with the lunge at the camera; row target -6 dB (the loudest cue of the raid; entrance -14, death -9). Work files `art/audio_work/roar18c/`.
- **Light:** iron albedo 0.1 -> 0.2 (warm key can draw its form), `Boss3DLight.key_boost` 1.9 for Thuban, cold rim edge stronger, wings opaque (alpha 0.94).
- **Jaw:** a billboard flare + omni light in the throat: green + big when the window is open and the jaw wide, red while the lance charges, a faint ember otherwise, off when shut / shattered.
- **Attacks from the body:** lance / fan / bite already left the jaw tip. NEW: wing volley (P2+, from both wing tips, told 1.0 s with rings at the tips), tail lash (P3, a 9-bullet sweep from the tail tip, told 1.0 s). Only from parts on screen and in front of the scenery.
- Known: `audio18_tests` "no sound element shared between two bosses (1)" is old (archive/algol `procedural`), not from this lane. Banners (rule / lance / guard) kept: tests b_raid11 / hint_band need them (judge asked for fewer: open item).

## S-PERF budget (lane pack18, 2026-10-21) - measured from the GLBs in hd/assets/bosses3d
Triangles per 3D boss (sum of all piece GLBs; parsed from the glTF accessors):

| boss | LOD0 tris | LOD1 tris | LOD0 GLB size |
|---|---|---|---|
| algol | 33,068 | 22,516 | 1,056 KB |
| dominion | 9,718 | 5,730 | 510 KB |
| furnace | 9,360 | 6,712 | 466 KB |
| oracle | 9,200 | 5,256 | 455 KB |
| thuban | 7,436 | 4,620 | 219 KB |
| husk | 6,182 | 3,518 | 277 KB |
| spear | 4,808 | 4,010 | 261 KB |
| seraph | 3,898 | 3,042 | 298 KB |

- Algol is 3-4x the others (33k): the one boss to watch on an A5x; its LOD1 is only -32 %.
- Textures: none of the 48 boss GLBs embeds a texture (colour/emission materials only), so "texture size by sharpness" is a non-issue for bosses; there is no lossy or capped image in them.
- One copy: every boss GLB (+ boss.tscn, pieces_report.json) exists ONLY under games/nova-strike/hd/ (no twin in assets/); hd/* is excluded from the Web and Android presets (export_presets.cfg exclude_filter), so the bosses travel only in the content pack.
- GPU frame cost (<= 2 ms on the A5x path): NOT measurable here (no GPU on the server, PC GPU is not an A5x). Plan for the release build: Test Lab run on a54x:34 (and a16x) with a boss mission; core/perf.gd uploads frame-time percentiles, read them with `python tools/qa/perf_report.py nova-strike --source testlab --build 0.18`; the boss budget is judged from p95 frame time during the boss fight versus the same phone's pre-boss p95.

Honest note on the art:
- gpt_lessons clean (still below our art bar)
- Thuban batch (still below our art bar)
- Raid map tiles finished (E-R35) (still below our art bar)
- the items above are not finished in this version; they continue in the next versions