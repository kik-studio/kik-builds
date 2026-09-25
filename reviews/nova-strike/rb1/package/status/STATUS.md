# Nova Strike · Review Build 1 — status matrix

**Build `0.1.0+0c2fc79`** · Builder-reported, 2026-09-25. Each row names its evidence. Status values: **complete** · **partial** · **not done** · **regressed** · **new issue**.
"Complete" means the feature is in the build and an automated test or capture shows it working. It does **not** mean it looks or feels right: that needs the owner's review and phone check (pending).

## Game
| Area | Status | Evidence |
|---|---|---|
| Full flow: Title → Home → Hangar → Campaign → Briefing → combat → Results → next; Endless; Training; Store; Settings; Mastery; Ending → Credits | complete | ui_flow 0 failures, ui_tests 0 failures, qa_suite [campaign] (6.08 → ending → credits); recording "Journey" |
| Three aircraft with pilots (Striker, Guardian, Arcanist), 3D, each with its own weapons, Tactical, Bomb and Super | complete | combat screenshots per unit (L1, L4, Super deploy frames, Bomb); recordings 3–5 |
| Hardware: 6 parts × 4 levels per aircraft, visible on Home, Hangar and combat, persistent | partial | qa_suite [equipment] + [purchase]; units_check; recording "Hangar ladder". Primary, engine and reactor change mostly by finish after their first levels; Mk I → II can be subtle at phone size |
| Temporary weapon levels L1–L4 | complete | combat_tests `levels_change_patterns_and_reset`; screenshots `combat_*_L1` vs `_L4` |
| Supers (mechanical transformations) | complete (mechanics) · partial (glance readability, Arcanist weakest) | combat_tests `super_cycle_pause_expire_restore`; `super_*_t000…t035`, `super_*_active` |
| 48 missions, 6 stages, 10-wave pacing, right-edge rail, no popups in play | complete (logic) | content_validator PASS (48 missions simulated); recording "Stage tour" |
| 6 bosses with phases | complete (logic) | content_validator (all bosses reach phases 0–3); recordings 3–5 |
| Endless | complete | content_validator endless PASS; recording "Endless" |
| Death, retry, pause, resume, victory | complete | combat_tests; qa_suite [focus]; `pause_en` screenshot |
| Costs, rewards, unlocks | complete | economy_sim PASS; qa_suite [rewards] (reward once per result), [purchase] (double tap charges once) |
| Saves: recovery, backup, interrupted write, old-save migration, offline | complete | qa_suite [saves], [offline] |
| Arabic and English | complete (logic) · partial (some small text) | test_runner loc checks; qa_suite [arabic]; all menu screenshots in `_ar` |
| Touch and multitouch | partial | simulated in combat_tests (`drag_relative_no_teleport`, `second_finger_button_keeps_steering`); real touch **pending** (owner phone check) |
| Rewarded ads, revive, Supporter, purchases | partial | UI and logic tested with fixtures; **no ad SDK or billing** in the build (buttons say so) |
| Balance | partial | bot-only (economy_sim, content_validator); no human playtest |

## Look and sound
| Area | Status | Evidence |
|---|---|---|
| Menus vs the Visual Direction Bible | partial | comparison sheets (home, hangar, campaign, briefing, results, store, pause, settings) |
| Combat vs the Visual Direction Bible | partial | comparison sheets (combat ×3, Super ×3): less density and spectacle than the target; aircraft 23–26 % of the width vs ~30 % |
| Sound on Android and native | complete (present) | recordings carry game audio (checked by the review tool) |
| Sound in browsers | **new issue** | measured silent in the browser (sounds start, output RMS 0); cause found in `core/audio.gd`; fixed for Review Build 1a |
| Combat sound mix level | **new issue** | local recording of combat peaked at 0.0 dB (mean −10 dB): possible clipping; not fixed |
| App icon and splash | partial | still the studio brand art |

## Performance and devices
| Area | Status | Evidence |
|---|---|---|
| Mid-range Android | **new issue** (below target) | Test Lab on identical game code (38f0663): Galaxy A16 25.6 fps (p95 46.7 ms), Galaxy A05s 26.7 fps, moto g 2025 45.9 fps. PERFORMANCE.md |
| Pixel 10 Pro XL | complete (automated benchmark) · pending (owner in hand) | Test Lab: 59.8 fps, p95 16.7 ms. Owner phone check pending |
| iPhone 16 Plus (browser) | pending | owner phone check |

## Changes from the earlier RC1 notes
Nothing regressed that the tests or captures show. The browser silence was already present in RC1 but only found now.
