# SUNPUNCH v0.21: what changed (the big connected upgrade, Khaled's package U01-U21)
- Kill-gated waves (U13): a wave ends at its last required defeat, the next starts within 1.0 s; required enemies never leave (FN-44); hidden bounded pressure when a player stalls (tell floor 0.6 s). Every stage carries an authored order (U14, STAGES.md).
- Underpower rule (O8): at a gap of 2+ tiers below the level's reference aircraft, pressure starts at once and landed damage drops; L3 with no upgrade clears 0/10 (improving bot) and 2/10 (skilled), 10 seeds, NORMAL PLAY. Flights with the recommended aircraft are identical with the rule on/off (132 flights). Armour on every level is exactly v0.20's (Khaled Q1, golden table test).
- Aircraft (U20, U11, U16, U10, U21): side units fire from LV1 (LV1 total output unchanged, 35/65 split), shots born at the drawn port, normal-flight size curve 1.20 (rank 1) to 0.75 (rank 20) once on today's size (Supers unchanged), per-family Super profile 2.5/3/3/3.5/4 s with prime/unfold/fire/reassemble, power buttons with six states, READY pulse, identity palette, 48 px. 3-D in flight stays THE path (Q4); 2-D fallback flag smoke-tested.
- Stones (O3): shader reacts to hit (flare in own hue), volley (charge + ripple) and bank (glint sweep); no new lights or parts.
- Obstacles (U12, U17, O15): boulders (shoot-through ridge with a pre-opened gap), wreck slabs (scorched iron, slow tumble), crystal gate pair (closing jaws), lantern chain, crane with an iron weight and a lamp; red-orange heat edge (not enemy-bullet pink); glyph warnings (source + lane + action, no text); loot never born on a lethal hazard; intro cards in a top band; the hit core reaches the 36 px fuselage for the new families (art and hits agree).
- Home (U01-U08, U02-U03): LV1 default, manual previews, equal thumbnails, contained upgrade button with have/need/remaining from one view model, road dots, bigger logo, contact shadow + reflection; flash cap 0.20 luminance jump (measured 0.022 / 0.041).
- Results (U18, B003, B006, B010, U09, U19): victory departure + clear credited once (pause/background/skip safe), capped boss contact reads 'blocked', Continue label fits EN/AR, Coil loop ceiling, local Legendary signal, Vault gate weave (demand >= the classic corridor on every step; KEY/REWARD words only).
- Menus (O5): three blind polish rounds on nine screens EN + AR (one button system, one header, aligned Level Clear stars, rebuilt Shot Down, Store/Settings/launch sheet/map/Vault card fixes); layout_check 0 findings on 19 screens, UI14 strict green.
- Ibrahim's GPT art (M4): shipped where it beat the stand-in in motion for the NEW obstacle families (boulders, slabs, crystal gate, lantern chain, crane weight; D-v21-1, then Khaled's owner decision D-v21-3 'not old. new. start everything': they ship, listed as new and still being improved). Replacements of existing art (hangar, Vault gate/canyon, victory reef, elites, DAYSTAR medallion) stay off: below 4.5 (D-v12-7).
- Bugs from the package register fixed with tests: B001/B002/B004/B005/B007/B008/B009/B011/B013 and the flaky Sector 2 isolation; perf watchdog with hysteresis for 30/60/120 Hz.
- Runtime 3-D menu thumbnails built but OFF (D-v21-2: PowerVR crash path not guarded yet).

- 2026-10-14 (lead, release build 1 miss): a CI test step fails on any `SCRIPT ERROR` line even with 0 failed checks (tools/ci/test.sh). Every pre-flight test log is now read for `SCRIPT ERROR` as well as RESULT/FAIL before the build.

Honest note on the art:
- polish pass all nine menus (blind POLISH >= 4.5) (below the art bar, carried)
- A-JUDGE: blind look-judge + POLISH >= 4.5 on Home, one obstacle encounter, victory (below the art bar, carried)
- 4 finished look item(s) without a passing look check yet
- 1060 art files still use the earlier look without a passing look check
- parts of the look are still below our own 4.5 bar; it keeps improving in the next versions