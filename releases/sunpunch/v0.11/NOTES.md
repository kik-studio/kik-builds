SUNPUNCH v0.11: the full game, harder and never boring (obstacles in every level, ranks, real 3D aircraft, crash fix)
- **One obstacle per level, always with enemies:** ten obstacle families (shell clusters, lantern chains, crystal shards + dam, horn rings, planted needles, the forge wheel, refilling nests, closing cliff walls, the Moon Shelf exam, the shark shadow), each taught, tested and twisted inside its level; operator elites (Lamplighter Puff, Horn Claw, Gatekeeper) run the obstacles and shut them down when killed. Bot tests: every family is fair over 50 seeds and every bot can dodge, break and use it.
- **Harder in steps:** per-level dials (enemy HP, bullet speed, fire rate, aimed share), acts rising inside each level, L4 shields, L5 splitters, L7 nests, L9 shield carriers, no enemy silently leaving the screen; ARMOUR ties the levels to upgrades (D-v11-12, owner: "Don't soften", FN-51): Level 3 with no upgrade fell from ~85 % to 25 % clear (improving bot), Level 6 one rank short 0 %, at the recommended aircraft 88 % (L3) / 50 % (L6) (FUN_NUMBERS 7d, 8 seeds).
- **Ranks I-III for every aircraft** (hangar RANK UP, in-flight rank light strips, launch-panel recommend chip); career sim: improving/skilled bots reach Level 10 at Helios I in ~30 min with ≤ 1 replay per step on average (before armour).
- **Power on time:** sun-core carriers bring LV2 at ~22-29 s.
- **Visible health:** crack light at 66/33 %, sparks and smoke at 10 %.
- **Level 1 tutorial:** still start, MOVE, Sunpunch and super prompts, shells open into the reef.
- **Real 3D aircraft for all four** on Home (Meshy 7.1 + our Blender finish) and a 3D assembly reveal on purchase. Internal blind look-judge: Spark as shipped in v0.9, Striker / Phoenix / Helios 3.5 each (below the 4.5 bar, shipped labelled).
- **Boss:** Retry from Inferno, falling-reef backdrop, alignment audit at 3 phone sizes (0.00 px drift).
- **Crash fix:** the Home 3D crash on Khaled's Pixel 10 Pro XL was Android's low-memory killer; Home 3D memory cut (60k-triangle model, ASTC maps, MSAA 2x, smaller view: hero video memory 144 -> 62 MB on the PC). Real-phone re-check: Khaled's own phone (phone check item) + TestFlight.
- **Sound:** 39 new cues (78 SFX) for obstacles, carriers, elites, crack light, ranks and reef lights.
- **Gate evidence (shipped build 0.11+4dc7227):** cloud test suite 5305/0; campaign_run flow PASS all on 7d8705a (same game files; every level at its recommended aircraft one rank up, nothing forced; buys + assembly, rank I->III x4, Home x4, swaps memory +0.0 %; evidence/G-PLAY/); PC review evidence of the same game files (e6c5ec9); independent check FAIL -> one fix round -> RECHECK PASS; PC suite 5322/0 on the earlier A+B merge (before armour); leak_check: nothing from another game; APK ~135 MB.
- **Honest gaps:** 3 new 3D aircraft below the internal 4.5 bar; obstacle pieces L4-L10 are low drafts; elites Needle Matron / Forge Claw, sun-core carrier art, hurt-squash/breathe and the Daystar ring were cut (PLAN §11 cut order); armour sims are 8 seeds on L3/L6 only (the skilled bot still clears L3 with no upgrade); phone bench numbers (U11-2) not taken (Test Lab daily limit; Brain phone gate applies).
- **Spend (internal):** Meshy 205 of 400 credits; GPT Image ~20 low drafts + ~12 high finals (direct key); ElevenLabs 78 SFX.

Honest note on the art:
- Striker, Phoenix and Helios Home 3D at internal blind 3.5 (bar 4.5) (below the art bar, carried)
- obstacle pieces L4-L10 are low drafts (~2.5-3 internal) (below the art bar, carried)
- operator elites and in-flight rank light strips not judged in motion (below the art bar, carried)
- 1 finished look item(s) without a passing look check yet
- 592 art files still use the earlier look without a passing look check
- parts of the look are still below our own 4.5 bar; it keeps improving in the next versions