# Test reports · Review Build 1 (`0.1.0+0c2fc79`)

Re-run by the Builder on 2026-09-25 on an exact export of commit `0c2fc79` (plus the review recording scripts in `tests/review/`, which the game never loads). Godot 4.7.2 headless on Linux, one private user folder per suite. Logs are next to this file (one known harmless engine warning about headless materials removed from the logs).

| Suite | What it checks | Result |
|---|---|---|
| test_runner | config, build ID, settings save, Arabic/English strings, audio buses, fixed play area on 5 screen shapes | passed 47, failed 0 |
| combat_tests | steering, multitouch, weapon levels, Bomb, Super cycle, bosses, readability coverage, rewards once, Arabic HUD | 35 run, 0 failed |
| qa_suite | saves (fresh, corrupt → backup, interrupted write, v1 migration), purchases, rewards, campaign graph, equipment consistency, Arabic, focus, offline | passed 174, failed 0 |
| ui_tests | every screen builds in EN and AR, touch targets, honest "not available" states | 0 failures |
| ui_flow | every menu button leads where it should | 0 failures |
| content_validator | all 48 missions and Endless simulated with the bot at 3 difficulties; bosses reach every phase | PASS |
| units_check | every aircraft, every hardware tier builds with its parts on real mounts | PASS |
| economy_sim | credit income vs prices along the campaign | PASS |
| browser audio (AUDIO_BROWSER.md) | sound reaches the speakers in the web build | **FAIL**: silent (fixed in Review Build 1a) |

Builder-reported. These confirm behaviour and data; they don't judge looks, feel or fun.
