# Nova Strike v0.10: what changed (short)

Khaled's outside package in one version (PLAN.md, approved 7858e51). Player-facing list: RELEASE_CHANGELOG.md.

- M1 foundation: 4-aspect phone-tall play field (rules 3.41 opt-in), local warnings, lasers attached to their emitters, under-halo off, durable transactions, نوڤا, crash kit, vendor cleanup, audio cues.
- M2/M4 combat (lane A): new scenery packages S1-S6 (calm lane, no repeating columns), G01 phrases + one signature per sector on all 48 missions, setpieces S1-S6 with enemies, Striker re-order (L3 big beam, L4 rockets), FN-50 breaking boss parts on all 6 bosses, new enemy finish, M5 eye-comfort fixes (S1 lanterns, S3/S4 scroll, S2 low-health edge only, S6 flicker, S3 fog, HUD on top, hint fades after 6 s).
- M3 meta (lane B): bundle upgrades + 3-card Hangar + install moment, Victory payoff + Credits continue, HUD roles + touch targets, Modes screen, Endless "The Long Night", Journey strongholds. Raids 1-2 built but OFF (teaser, D-v010-64), Raid 3 teaser.
- Fixes: hidden warm-up fight no longer marks the Super hint as seen (A4); legacy tests updated to v0.10 upgrade bundles.
- Pre-flight on the final tree (rules 3.42): full suite 150/0 (job 1013160658-5f03, headless bots + unit suites), export ok, APK 178.6 MB (limit 190; was 202 MB before the v10 scenery/explosion imports went lossy 0.85), leak_check clean, layout_check 17 screens EN/AR tall/short 0 findings, release-checker dry run 13 C-lines fixed (PREFLIGHT_CHECK.md). Earlier evidence: 48/48 flow play-through + normal-play 29 clears / 19 defeats / 0 hangs (lane A, job ids in LANE_A.md); blind judges: GATE_M5_LOOK_JUDGE.md (art below bar -> disclosure), S11_R*_JUDGE.md.
- Carried to v0.11: Raids 1-3 with painted bosses, tall-shape difficulty parity (D-v010-60), GPT redo art (GPT_REDO.md, 33 requests), rewarded-ad continue.

Honest note on the art:
- 1 finished look item(s) without a passing look check yet
- 4802 art files still use the earlier look without a passing look check
- the game's look settings are not locked yet
- parts of the look are still below our own 4.5 bar; it keeps improving in the next versions