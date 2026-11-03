# SADDAH v0.3 — what's new (DRAFT by P3, 2026-10-04; internal candidate)

Every level is now its own little journey, with a real finish, and the game plays and looks better. It is an **internal candidate**: the art is not at the bar we set ourselves yet, and no outside players have tested it (see "Known gaps").

## What's new for players
- **54 stages made again, one by one.** Each has its own idea, a rhythm that changes, a short exciting final section (8 to 15 seconds) and a safe, calm finish. Each one ends at its own place (a well house, a camp gate, a skybridge tower, a tunnel mouth, a cable-car lookout ...) and has its own third-star challenge.
- **No more empty running.** There is always something to do: nothing waits more than about four seconds without a choice, and the time spent just waiting dropped from about half of each stage (51 %) to roughly a fifth to a third. Coin trails guide you with lines, lane changes and jump arcs; some have an optional riskier route; power-ups sit where you can enjoy them.
- **Speed that builds.** Many stages start gently and speed up by up to 20 % towards the end, some come in waves. Every jump and slide still gives you a fair window, also with Assist.
- **Controls you can trust.** Early jump presses are remembered, a late press at a ledge still works, a wrong swipe can be cancelled, and the jump that could not be cleared in stage 1-1 is fixed. No automatic play.
- **A finish worth reaching.** The results screen shows what you earned and why (Qoroosh, stars, first clear), how close the next outfit or upgrade is, and the next stop. Tap and it lands at once. The old ad button is gone. Each world's last stage gives a keepsake.
- **Earlier rewards.** Your first purchase is possible after stage 1-2 (it was after 1-4), and the whole campaign still earns more than everything in the shop costs. Nothing is needed to finish the story.
- **Failing teaches.** A short line says what to do ("Slide under the frame"), a retry takes under two seconds, and after a miss inside the final section you can "Try the finale" again without replaying the whole stage.
- **Power-ups are readable.** A ring shows how long the magnet, shield or boost lasts, blinks before it ends, and ends softly so you are never dropped into a crash.
- **A journey map.** The nine worlds now join into one long painted road. Saddah's marker walks to the next stop, the next region is revealed when you finish a world, you can drag the map with a finger, it remembers where you were, and there is a calm version for reduced motion.
- **Menus.** New Home picture that keeps Saddah's face and the Amanah in view on any screen, a briefing with a route card (from where, to where, what is new), painted portraits, a new shop shelf, three clearly different outfits.
- **Pause, Settings, Back now works.** Opening Settings from Pause keeps your run exactly as it was, with your coins, and Resume uses the normal 3-2-1 count. (Before, it threw you to Home and lost the run.)
- **Better look.** The phone game now uses the richer renderer with soft shadows and a light mood for each world, a camera that sits higher and further ahead so you see more of the world, a painted road for each world (gravel track, city asphalt, festival paving, mountain track, flagstones, limestone avenue, coral stone, canyon sand, graphite deck), a landmark in the distance of every world, and many new 3D props along the way. Saddah is rebuilt (new head, shemagh, backpack, thobe, hands).
- **Sound.** A short sting when you enter each world and a music layer in each final section, a coin sound that climbs as you collect, small vibrations on pickups and near misses (can be turned off).
- **Still the same promise:** no combat, no required purchases, Makkah handled with restraint, NEOM shown as an inspired future vision. Arabic and English, right-to-left, text up to 150 %, reduced motion, assist timing.

## Movement (FEEL2)
- **Snappier jump:** 0.66 s in the air (was 0.85 s), a quick rise and a faster fall, almost no hang at the top; judged 4.5/5 in motion.
- **A real slide:** Saddah drops feet-first, head about half as high, with a camera dip, a streak shadow and side spray, and pops straight back into the run (judged 3.0/5: the robe and ghutra still hide the legs from the chase camera).
- **Cleaner jump pose:** knee up and out, free arm out, the case held tight (judged 4.0/5).
- **The camera stays clear:** beams stay solid while you pass under them, obstacles right at the lens hide instead of smearing, passed ones slide away; the red "!" rides beside Saddah and "Close one!" is rare (lens judged 2.5/5 before its last fixes, which are checked by tests only).
- **All 54 stages retuned to the new jump** (51 regenerated, W01-L01/L03 by hand, four reseeded); waiting time without a decision is now under the 35 % rule everywhere (e.g. Makkah L01 42 % -> 17 %).

## Known gaps (honest)
- **Saddah's look is not at the bar.** An independent judge scored the rebuilt hero **3.2 out of 5** in motion (round 1: 2.3, round 2: 2.9) against our bar of 4.5. Shemagh cloth, one expression on the face, thobe materials and a hand-keyed run/jump/slide are the gaps; the painted portraits in the menus score 4.5 by our own check only.
- **The worlds are not at the bar.** Strict judge scores in motion, beside the original boards: Desert 3.75, Riyadh 3.75, Qiddiya 3.5, Tuwaiq 3.25, Taif 3.5, Makkah 3.25, Jeddah 3.5, AlUla 3.0, NEOM 3.0 (bar 4.5). The strip beside the track is still sparser than the boards. The map scores 4.34 to 4.37.
- **FR-23: recordings are not from the phone renderer.** The PC job helper still forces the older renderer, so most clips and judge evidence are not exactly what a phone shows. Real phone recordings and performance numbers on the release candidate do not exist yet.
- **FR-24: the art needs its own round.** Reaching 4.5 for the hero and the nine worlds is a dedicated art round (hero head, cloth and animation rebuilt in parts; denser props and light per world), planned after this candidate.
- **People gates are OPEN** (decision OD-1: Khaled has not named the testers yet): eight fresh players, a native Saudi voice and cultural review, and a human playtest of stages in all nine worlds. Kit is ready in `human_test/`. Until they run, the fun, the Arabic polish and the cultural review are claims, not results.
- A few stages differ from the matrix: climax shorter in W01-L02 and W05-L02, two obstacle types unused in W05 and W07, route-choice lines missing in six stages.
- Arabic text is a careful first pass, not yet read by a native reviewer.

CHECKLIST totals and the evidence behind every line: `CHECKLIST.md`.
