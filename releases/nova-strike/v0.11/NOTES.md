# Nova Strike v0.11: what changed (short)
Full round after v0.10 (0.10+eb75b6d), ONE build, ship on build (D-v011-1, Khaled 2026-10-13: 'do the whole fix, along with anything in pipeline in 1 go'). Lines: TODO.md; lanes: LANE_A/B/C.md.
- F1 / FN-53: the HD pack uploads with the build (config/game.json "hd_upload": true); test_runner guards the opt-in.
- F3: a network HD download never holds the first flight: "Play now" at once (EN + AR), hd_pack_tests.
- C4 TECH-07: native quality: Mali-G68 class no longer starts on Low, bounded probe windows up and down, "Reset Auto Quality" in Settings (EN + AR).
- C7: Crashlytics forced test crash button in the studio test screen (test builds only).
- X-bullet: per-sector enemy bullet colour (all six sectors).
- A2: tall-phone parity levers (spread angle, director slot clearing, per-sector bullet speed + S3 cadence, rail arrival); identity on 16:9; S3 bullets capped at arrival parity (fairness test).
- X-sockets: new Striker hull sockets (splayed cannons, beam muzzle, lance_core, no L3 racks), Super drawn 10 % larger.
- R17 Raids: Raids 1-2 ON with painted bodies and the readability rework; Raid 3 built and tested, OFF (blind gate not passed).
- Art (lane C): Striker L3/L4/S hulls flight + hangar, S1/S3 props cleaned, S4 setpiece slab + claw.
- R4: blind fun pairwise result in R4_FUN.md (exit not met; next-round lines).
Changed areas since eb75b6d: quality/settings/studio test UI, crash kit hook, attack director + six sector brains + enemy bullets (A2), raids 1-3, HD gate, Striker hull art + sockets. Carried and open: TODO.md [~] lines (and RELEASED.md after the send).

Honest note on the art:
- ART: CARRY 6: Striker L3/L4/S hulls, scenery S1-S6, enemy finish (LOOK-01), Journey, setpieces, boss break... (below the art bar, carried)
- 4907 art files still use the earlier look without a passing look check
- the game's look settings are not locked yet
- parts of the look are still below our own 4.5 bar; it keeps improving in the next versions