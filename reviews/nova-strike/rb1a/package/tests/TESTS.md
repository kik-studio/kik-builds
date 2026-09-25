# Test reports · Review Build 1a

Re-run by the Builder on 2026-09-25 on an exact export of this build's game code (Godot 4.7.2 headless, a private user folder per suite). Logs are next to this file.

| Suite | Result |
|---|---|
| test_runner | passed 50, failed 0 (3 new: Master stays bus 0 · Music and SFX send to Master · no `AudioServer.add_bus()`) |
| combat_tests | 35 run, 0 failed |
| qa_suite | passed 174, failed 0 |
| ui_tests | 0 failures |
| browser audio (AUDIO_BROWSER.md) | **PASS** in Chromium; iPhone Safari pending |

ui_flow, content_validator, units_check and economy_sim weren't re-run: the only game-code change is in `core/audio.gd`, and their Review Build 1 results stand.

Builder-reported. These confirm behaviour and data; they don't judge looks, feel or fun.
