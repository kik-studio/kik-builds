# Nova Strike · Review Build 1 (baseline — draft)

**Build ID `0.1.0+0c2fc79`** · source commit `0c2fc79` · pinned by the Brain on 2026-09-25 · package prepared by the Builder.

This is the full-game release candidate from the overnight build, frozen as the **baseline** so later builds can be compared against it. It is a draft for review, not an approved or finished game.

## Play it
- Browser: https://kik-studio.github.io/kik-builds/reviews/nova-strike/rb1/ (the pinned copy, never overwritten)
- Android APK: the same page.
- **Known issue in this build: no sound in browsers.** The Android APK and the recordings have sound. Review Build 1a fixes the browser sound (see "Known issues").

## What's in this package
| Item | What it is | Evidence type |
|---|---|---|
| README (this file) | What the build is, what's inside, what's known | Builder-reported |
| Technical documentation (PDF) | How the game is built: engine, structure, saves, data, builds, tests | Builder-reported |
| Status matrix | Complete / partial / not done / new issue, with the evidence for each row | Builder-reported (rows cite automated tests or captures) |
| Screenshots, all screens | 32 menu screens (English + Arabic) and 26 combat shots, at phone size 1080×2340, build ID on screen | Builder: captured from the labelled code; automated: files and checksums |
| Visual comparisons (owner-only: they show Visual Direction Bible pages) | 14 sheets: design target page next to the real screen, in colour, grayscale and glance size | Builder: generated; **no new verdicts** (see COMPARISONS.md) |
| Recordings (6) | Unedited takes of the real game played by the bot pilot, with game sound, build ID on screen | Automated: recorded by the review tool at a commit whose game code equals 0c2fc79 |
| Demos (6) | Short takes: equipment, weapon levels, Supers, pickups, environments (stage tour), audio behaviour; what the demo sets up is named on screen | Automated: recorded the same way |
| Event logs | All 48 missions + Endless flown by the bot: waves, enemy-free periods, pickups, weapon levels, Supers | Builder-reported (logs included) |
| Test reports | 8 test suites re-run on the labelled code, plus the browser audio test (fails in this build) | Builder-reported results; logs included |
| Balance | The game's data tables (units, prices, enemies, bosses, 48 missions) exported to JSON, and the balance notes | Builder: exported from the labelled code |
| Performance | What was measured on real phones, and what's still pending | Measured vs pending, labelled per line |
| Audio files + audio manifest | Every sound and music file in the build, and where each came from | Automated: files and checksums |
| 3D and 2D masters (owner-only) | The generated 3D models and the canon/production art the game is built from | Owner-only |
| Source (owner-only) | The game folder at commit 0c2fc79, clean export | Automated: archived by git |

## The recordings
All are single unedited takes from the real game code, played by the built-in bot pilot. What the bot does isn't how a person plays, so these show the game working, not how it feels to play.
1. **Journey** (~3 min): Title → Home (the three aircraft) → Hangar (install a part) → Campaign → Briefing → mission 1.01 → Results → Training (Guardian and Arcanist Supers) → boss 1.08. *The bot is invulnerable in this take* (stated on screen).
2. **Hangar ladder** (~2 min): every hardware part on all three aircraft, Mk I → Mk IV, through the real Install button, then Home with the three fully upgraded aircraft. *Credits are added for the take* (stated on screen).
3. **Striker vs ALGOL** (mission 1.08, hardware Mk I), full run, bot can lose.
4. **Guardian vs Furnace Sovereign** (mission 2.08, Mk II), full run, bot can lose.
5. **Arcanist vs Storm Seraph** (mission 3.08, Mk III), full run, bot can lose.
6. **Endless** (Guardian, Mk II): about 2 minutes, then ended from the Pause menu (if the bot is still alive).
7. **Stage tour** (listed with the demos): 24-second excerpts of mission x.03 in all six stages. *Bot invulnerable, excerpts cut on purpose* (stated on screen).

Demos: equipment (Striker Mk I → IV, then in combat), weapon levels L1 → L4 per aircraft, the three Supers, pickups, audio behaviour. In these the demo sets things up (level, Super meter, drops, credits), and says so on screen.

Hardware levels in 3–5 are chosen by the Builder to roughly match that point in the campaign; they are not measured from real players.

## Known issues (as of this build)
- **No sound in browsers** (all browsers). Measured: the game starts its sounds but the browser output is silent. Cause: a Godot 4.7.2 web bug triggered by how the game created its sound channels. Fixed for Review Build 1a (`core/audio.gd`). The APK and the recordings are not affected.
- **Mid-range Android performance below target.** Measured today on the same game code: Pixel 10 Pro XL 59.8 fps (meets the target); moto g 2025 45.9; Galaxy A16 25.6; Galaxy A05s 26.7. See PERFORMANCE.md.
- **Combat is less dense and less spectacular than the design target**, and the aircraft are smaller in combat than in the target (23–26 % of the width vs ~30 %). The comparison sheets show it.
- **The combat sound mix peaks at full scale** (measured in a local recording: peak 0.0 dB, mean −10 dB), so it may clip on some speakers. Not fixed yet.
- **No real ads or purchases**: those buttons say "not available in this test build".
- Balance is tested with the bot only, not with people.

## Pending
- Khaled's own phone check (Pixel 10 Pro XL APK + iPhone 16 Plus browser): **pending**.
- iPhone frame rate in the browser, and heat over a long session on any phone: **pending** (see PERFORMANCE.md).
- Audio masters: **unavailable**. The sound tools wrote the final files directly, so there are no separate masters.

> Uploads, checksums, archive checks and bot runs don't prove visual quality, fun or owner acceptance.
