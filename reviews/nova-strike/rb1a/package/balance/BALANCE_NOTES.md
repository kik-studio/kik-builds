# Nova Strike — Balance (economy + difficulty)

*CONTENT, overnight polish wave 2 (2026-09-25). Tools: `tests/economy_sim.tscn`, `tests/content_balance.tscn`, `tests/content_real_capture.tscn`.*

## 1. Economy (TRB §12, 48-mission simulation)

**How it's run:** `HOME=/tmp/nshome godot --headless --path . res://tests/economy_sim.tscn` (exits 0 on PASS).
The sim uses the real game data: `Missions.get_def().reward_first/reward_repeat`, `UnitDefs.TIER_PRICES` and the real prerequisite rule in `Profile.can_buy` (tiers 3 and 4 need milestones), run on a scratch profile that is never saved.

**Player model:** plays 1.01 → 6.08 in order. The first attempt at a mission can fail (10 % in ch1 up to 28 % in ch6; a failure pays 18 Credits of salvage, then the player retries). "Modest replay" means one replay of the mission just cleared, every 4 missions (12 replays in the whole campaign). The player spends greedily on the main unit, raising the lowest family first.

**Expected equipment** (installed module tiers out of 24 at the start of each chapter, and the bar a chapter must be comfortable at): ch1 0 · ch2 4 · ch3 8 · ch4 12 · ch5 16 · ch6 20.

### Final numbers
- **Rewards** (`missions.gd _build`): first clear = `110 + 32·(chapter−1) + 4·(index−1)`, boss ×1.6, replay = 70 % of first clear. That gives 1.01 = 110, 1.07 = 134, 1.08 = 221, 6.01 = 270, 6.07 = 294, 6.08 = 477. All 48 first clears add up to 10 577. (Before: 100 + 28·c + 3·i, boss ×1.5, total 9 240.)
- **Prices** (`UnitDefs.TIER_PRICES`): tiers 1–4 cost **150 / 300 / 520 / 820** (before: 150/320/560/900). A fully upgraded unit (6 families × 4 tiers) costs **10 740** (before: 11 580).

| profile | Credits earned | main unit fully upgraded at | 2nd unit tiers at end | tiers at ch2/3/4/5/6 (target 4/8/12/16/20) |
|---|---|---|---|---|
| baseline, no ads, 1 replay per 4 missions | 13 124 | **6.03** | 10 | 7 / 12 / 16 / 19 / 23 |
| no replays at all | 10 811 | 6.08 | 0 | 6 / 11 / 14 / 18 / 21 |
| baseline + trying a 2nd unit at ch3 (3 tier-1 modules) | 13 124 | 6.04 | 10 | 7 / 12 / 15 / 19 / 22 |
| ad user (doubles every eligible result, upper bound) | 26 014 | 4.03 | 24 | 11 / 18 / 22 / 24 / 24 |
| ad user (doubles half of results) | 19 485 | 5.02 | 21 | 9 / 15 / 19 / 23 / 24 |
| Supporter (always 2×, never 4×) | 26 014 | 4.03 | 24 | same as ad-every |

Before tuning, the baseline player never fully upgraded a unit (reached 20 of 24 tiers at ch6 and ran out of campaign).

**What the sim asserts** (all pass):
- The baseline player is at or above the expected equipment at the start of every chapter.
- Trying a 2nd unit never pushes the main unit below target.
- A player who never replays is at most 2 tiers behind.
- The baseline main unit is fully upgraded between 5.08 and the end of the campaign.
- Ad and Supporter players get there faster.
- Ad and Supporter income stays below the cost of 3 full units, so they can't max everything.
- Supporter income is 1.8–2× baseline (never 4×).

**Reading it:**
- A baseline player hits the first milestone (Enhanced, 6 tiers) right after chapter 1.
- They can afford a 2nd unit's first modules in chapter 3 at the cost of about one tier of delay.
- They finish one unit fully upgraded around 6.03–6.08.
- Ad and Supporter players end with about two maxed units, not three.
- Endless income isn't counted; it's extra on top.

## 2. Difficulty / fairness (real combat scene)

**Harness:** `godot --headless --path . --fixed-fps 60 res://tests/content_balance.tscn -- missions=… units=… equip=base|expected diff=…`

- It runs `scenes/combat.tscn` with a "decent player" pilot and god mode off.
- The pilot is like `CombatWorld._bot`, but it re-decides only 5 times per second (reaction latency).
- It avoids telegraphed beams and zones (warn and active), and never plans a path through a live beam.
- It can also move up or down between three rows.
- `equip=expected` installs the chapter's expected tiers.
- It prints `BAL mission unit equip diff result time lost% hits fired peak phase causes`, plus the enemy state-machine transition counts.

### Finding: Standard had almost no pressure
With the old numbers, 1.04 fired **14 hostile bullets in the whole mission**, and 6.05 fired 80.

In 3.04, 60 enemies spawned:
- 33 died during entry.
- 21 died holding position before their first telegraph.
- **Only 4 attacks were ever made.**

A bot that doesn't dodge at all (`combat_flow` god=0) cleared 5.04 and 6.05 on base equipment with 66–70 % hull left. Bosses died 20–45 s after appearing: base Striker beat Dominion Prime's 12 000 HP in about 45 s.

The cause is a mismatch in damage output, not bullet patterns. `EnemyDefs` HP is tuned against a baseline of about 100 DPS (per the file header). The measured player output with in-mission L1–L4 plus Super is about 250–300 DPS.

### Changes
- **Chapter durability scales** (`Missions.HP_SCALE` / `BOSS_HP_SCALE`, applied by `Encounter` spawn opts and `Boss.setup` to the body and parts):
  - Wave enemies: 1.3 / 1.5 / 1.7 / 1.9 / 2.1 / 2.3. Tutorial 1.01 stays at 1.0.
  - Bosses: 1.5 / 1.7 / 1.9 / 2.1 / 2.3 / 2.3.
  - This is a deliberate exception to "not raw HP". The problem was the opposite of unavoidable damage: enemies never got to act, and boss phases flashed past. The per-chapter ramp also absorbs the expected module upgrades.
- **First shot sooner:** `EnemyUnit` sets its initial cooldown to 0.2 × the role cooldown + 0–0.5 s (was 0.6 × + 0–0.8 s), so arriving roles telegraph quickly. Later cadence is unchanged.
- **Stage pressure ramp:** the default `aggression` (cooldown scale) goes 1.0 / 0.9 / 0.82 / 0.76 / 0.7 / 0.65 (was 1.15 … 0.9). Tutorial overrides are kept.
- **After the changes:**
  - 6.05 fires 656 bullets (was 86).
  - 1.08 fires 476, and the boss fight takes about 100 s.
  - Boss fights at expected equipment last about 40–100 s, and all phases are seen.

### Table: Standard, decent-player pilot (after changes unless noted)
| mission | unit / equip | result | time s | hull lost | bullets fired | notes |
|---|---|---|---|---|---|---|
| 1.01/1.04/1.07 | all 3 / expected | win | 88–91 | 0 % | 10–24 | before the changes |
| 2.02/2.06/3.03 | all 3 / expected | win | 88–90 | 0 % | — | before the changes |
| 4.01/4.04/4.07, 5.01/5.04/5.07 | all 3 / expected | win | 88–89 | 0 % | — | before the changes |
| 1.04 | Striker / base | win | 88 | 0 % | 24 | after |
| 3.04 | Striker / base | win | 88 | 0 % | 44 | after |
| 6.05 | Striker / base | win | 96 | 0 % | 656 | after |
| 1.08 Algol | Striker / base | win | 121 | 0 % | 476 | after (autoplay bot before: 13–73 % lost, all from beams it didn't avoid) |
| 4.08 Null Oracle | S / G / A expected | win | 56 / 97 / 95 | 0 % | 68–166 | after |
| 5.08 Regent's Spear | S / G / A expected | win | 90 / 225 / 83 | 0 % | 76–372 | after |
| 6.08 Dominion Prime | S / G / A expected | win | 73 / 41* / 51* | 0 % | 244–412 | *started at a checkpoint act (harness bug, now fixed) |
| 5.04, 6.05 (non-dodging bot) | Striker / base | win | 90–97 | 15–30 % | — | worst-case "doesn't dodge" pilot |

**Fairness:** with the telegraph-aware pilot, no damage was unavoidable anywhere in the sample. Every hit the old autoplay bot took came from beams it ignored, not from bullets it couldn't escape.

**Open:** Standard is still lenient. A dodging pilot takes no damage, and a non-dodging one keeps more than 70 % hull. The real lever is player DPS versus content HP (combat owns player DPS). Next steps:
- Agree on a target DPS per chapter and equipment level, then re-run `content_balance`.
- Story and Veteran weren't re-measured this wave. They inherit the same scales, and Story's own mods still apply: cooldown ×1.35, telegraph ×1.3, 1 fewer shot, 0.8 budget.

## 3. Wave 3 content pass (readability, density, bosses) — final numbers

*CONTENT, wave 3 (2026-09-25). Player DPS is now normalized by combat (see "DPS (combat)" below); every number here was measured after that.*

### Wave enemies: HP scales kept, pressure from timing
- `Missions.HP_SCALE` stays **1.3 / 1.5 / 1.7 / 1.9 / 2.1 / 2.3**. Against the normalized DPS (~150 mid-mission L2–L3 base, × ≈1 + 0.045·expected tiers) it gives: fodder 0.3–0.45 s, assault 0.8–1.5 s (Weaver ch1 1.1 s; ~0.8 s at L4), elite 4.5–6 s. All inside the TRB §16 bands, so no HP inflation.
- The leniency was timing: ~70 % of fodder died before its first telegraph. Fixes (no HP change):
  - Fodder's first cooldown is 0–0.3 s, so it telegraphs as the entry grace ends. Other roles use 0.15 × cd + 0–0.35 s.
  - The entry hands over to formation at 80 % of the glide, so units telegraph while settling. Grace (fully on-screen + 0.35 s) is unchanged.
  - **Reinforcement top-ups** (`Encounter._pressure_topup`): on a non-breather wave, one fodder group flies in from a side when:
    - everything authored has spawned,
    - the wave is at least 3 s old,
    - live threat is under 30 % of the budget,
    - the next wave is more than 4 s away.
  - Top-ups per wave: **Story 0, Standard 1, Veteran 2** (4 per group on Veteran). Veteran also keeps its side-mirroring remix.
  - Early hand-over: a cleared wave starts the next one up to 6 s early (was 5 s), 3 s after its start (was 4 s).
- Sizes: fodder is 145–150 px and assault 175–205 px (was 110–180), next to a player at ~200–225 px. Formation spacing was widened to match.

**Pressure measured with `content_balance` (decent-player pilot, expected equipment, Standard unless noted).** The TTK line is new: `life` = seconds from wake to death (includes the ~1.1–1.3 s entry), `silent` = died before any telegraph.
| mission | unit | bullets fired (wave 2 → now) | fodder silent (before → now) | hull lost |
|---|---|---|---|---|
| 1.04 | Striker | 24 → 82 | 73 % → 53 % | 0 % |
| 1.04 | Guardian | — → 166 | → 30 % | 0 % |
| 3.04 | Striker | 44 → 54 | 60 % → 40 % | 2 % (1 collision) |
| 4.01 | Guardian | — → 102 | → 21 % | 0 % |
| 5.06 | Striker | — → 118 | 42 % → 46 % | 6 % (1 collision) |
| 6.05 | Striker | 656* → 238 | 48 % → 42 % | 0 % |
| 3.04 Veteran | Arcanist | — → 238 | 38 % | 0 % |
\*The wave-2 figure was measured on base equipment with the pre-normalization DPS.

Standard is still forgiving for the telegraph-aware pilot (0–6 % hull), but waves now fire during entry and stretches have no dead air.

### Bosses: HP scale per chapter re-tuned
`Missions.BOSS_HP_SCALE` = **1.45 / 1.95 / 2.2 / 2.45 / 2.2 / 2.3** (was 1.5 / 1.7 / 1.9 / 2.1 / 2.3 / 2.3). Dominion Prime's authority modules go from 520 to **380** HP: the act-1 gate took Guardian about 60 s against about 13 s for Striker.

Fight time (s, boss spawn → defeat) at expected equipment. Each cell is one run. Runs are not deterministic, and repeats vary ±30 % (for example, 6.08 Guardian ran 229 / 155 / 221 / 116):
| boss | Striker | Guardian | Arcanist | notes |
|---|---|---|---|---|
| 1.08 Algol | 127 | 136 | 158 (111 earlier) | inside 90–180 |
| 2.08 Furnace | 108–118 | 128 / 157 / 285 | 80–109 | measured at ×1.85 and ×2.05; the final value is ×1.95. Guardian's outliers all come from phase 1: 87 s of 157, because its slow shells miss the heat-vulnerability windows |
| 3.08 Seraph | 105 | 110 | 93 | final ×2.2 |
| 4.08 Oracle | 96 | 108 | 94 | Striker and Guardian measured at ×2.35; Arcanist at the final ×2.45 |
| 5.08 Spear | 107–207 | 60–73 | 90 (×2.0) / 150 (×2.2) | the final ×2.2 is a middle value. Guardian is consistently fast here: its splash hits the three subsystems and the body together |
| 6.08 Dominion | 82–99 | 116–221 | 93 | measured with 380 HP modules |

**Open:**
- The ≤1.4× spread between units holds for 1.08, 3.08 and 4.08. It does not hold for 2.08 (Guardian's phase 1 is slow), 5.08 (Guardian fast) or 6.08 (Guardian slow on the moving modules). Every other run landed in 90–180 s.
- These gaps come from how each unit's damage lands on multi-part bosses in real play, not from boss HP. The bench spread is 1.06–1.11.
- Suggested follow-ups:
  - A per-boss armor/part-exposure pass (Spear subsystems further from the body).
  - A multi-run median in `content_balance` (add a `runs=` argument).

### Presentation changes (Boss / BossPart / Encounter / EnemyUnit)
- **Boss intro lines:** a unique `world.hud.say()` line per boss for the entrance (`boss.<id>.intro`), each phase shift (`.shift`) and the defeat (`.down`). All are in `i18n/content.csv`, EN + AR.
- **Phase shift:** a double shock ring off the body, a short tinted flash and the shift line, on top of the existing bullet clear and shake.
- **Defeat:**
  - A soft glow bloom and two shock rings replace the flat disc.
  - A final white-out and wide ring play.
  - Destroyed-part sockets fade with the body. They used to float in empty space.
  - Algol calls `content_event("beacon")` to relight the beacons it dimmed on entry.
- **Boss homes** moved 30–90 px lower (Algol 500, Furnace 490, Seraph 450, Oracle 470, Spear 490, Dominion 480), so tall sprites clear the HUD strip and boss bar.
- **Hazard identity art** (`Encounter.HazardDecor`, drawn under enemies and under the coral damage shapes):
  - Vents: a scorched grate with heating slats and shimmer, then a flame burst.
  - Corridors: emitter pylons at both ends with arcing lightning.
  - Wells: a rotating violet vortex with infalling motes.
  - Artillery: a rotating reticle and a falling shell that lands when the warning ends.
- **Tethers and links:**
  - The Tender tether is a 16/6/2 px layered beam with travelling pulses.
  - The shielded target gets a filled bubble.
  - Relay links are 12/4 px.
- **Escort objective (1.04, `convoy: [3, 7]`):**
  - Three friendly couriers (procedural, cyan ring, hull bar) fly up through the raiders' crossing lane.
  - Raiders within 380 px strafe them, with visible tracers and hit tint.
  - A lost courier explodes and shows a toast. No mission failure.
- **2.04 "convoy":** now has a real crossing siege-barge target.
- **Objective targets** spawn at y 300–360 (was 250), below the HUD.
- **Fixes:**
  - Boss missions deliver the power pickups of approach enemies that escape after the boss spawns. This fixed the 5.08 "2 power" validator fail.
  - The Furnace slag-zone hazard claim now covers the Story-scaled warning. This fixed a 2.08 Story overlap.

### Captures (xvfb, 540×1170, `tests/content_real_capture.tscn`)
- New arguments:
  - `missions=2.06@12~zones` captures at the first frame after 12 s where the condition holds. Conditions: `zones`, `beams`, `tether`, `objective`.
  - `fast=1` (default) turns off the render loop while fast-forwarding, so 6 stages take about 45 s.
  - `bhp=0.35` is a capture-only boss HP multiplier to reach every phase quickly.
- Frames for this wave:
  - Stages: `real_1.03 / 1.04 / 2.06 / 3.03 / 4.01 / 5.06 / 6.04_mid.png`.
  - Bosses: `real_<x.08>_entry / phase1..4 / defeat.png`.
  - Before/after montages: `mont_before.png`, `mont_after1.png`, `mont_boss_a/b.png`, `mont_c2.png`.

### Test status (end of wave 3)
- `content_validator`: PASS on Standard, Story and Veteran.
- `economy_sim`: PASS (economy unchanged; table in §1).
- `combat_tests` and `test_runner` (47/0): pass.
- `demo_run`: reaches "mission done ... result=true" and "end".

## 4. Wave 4 content pass: boss fairness, 6.04, finale

*CONTENT, wave 4 (2026-09-25). This supersedes the wave 3 boss table in §3.*

### Multi-run boss median
**Command:**
`godot --headless --path . --fixed-fps 20 res://tests/content_balance.tscn -- missions=1.08 units=unit_striker,unit_guardian,unit_arcanist equip=expected runs=3 seed=1`

- **Runs:** run *r* is seeded with `seed*1000+r`. That value goes to the global RNG (pickups, shot jitter) and to `Encounter.seed_salt`, which salts the encounter, EnemyUnit and boss seeds. The salt is test-only and is 0 in the game.
- **Speed:** `--fixed-fps 20` runs 3 world steps of 1/60 s per frame, about 8 s per boss mission.
- **Output:** `BOSSFIGHT` lines (fight time, weapon level at boss spawn and average level, boss/part HP, phase log), then one `MEDIAN` line per mission, unit and equipment.
- **Other arguments:**
  - `checkpoint=N` starts 6.08 at act N, as a Retry does.
  - `route=1` lets the real victory path run and prints the screen it routes to.
  - `BAL` lines now include `objs_together` (the most objective targets alive at once).

**Findings before the fix:**
- The biggest cause of spread was the pilot, not the boss. The old pilot ignored pickups, so about 1 run in 3 reached the boss at L2 and stayed there. Those runs took about 2× longer for every unit (6.08: 198 s vs 108 s; 3.08 Guardian: 204 s). The wave 3 "Guardian slow" cells were mostly these runs.
- Real per-unit gaps that remained:
  - Algol: Striker was 1.45× Guardian, because flat armor 2 eats rapid-fire bolts.
  - Dominion act 1: Guardian took 31–35 s vs 12–15 s. The sealed crown body sits in front of the upper modules and absorbed shells.
  - Dominion act 2: its 280 px, 0.55 rad/s drift outran shells.
  - Spear: all three units were under 90 s once they arrived at L4.

**Boss-side changes (no per-unit code):**
- **Every boss, phase shift:** drops a power core if the pilot is below L4, so an under-powered arrival can recover.
- **Algol:** armor 0.8 (was 2; new optional `armor` key in `bosses.gd`).
- **Furnace Sovereign:** for 0.7 s after a vent closes, damage still lands at the vent value (×1.25), so shells fired into the vent count. After that, stored heat takes 0.4× (was 0.25×).
- **Dominion Prime:**
  - Act 1 "authority conduit": hits on the sealed crown arc to the weakest living module at 50 %, with a small ring on that module.
  - Act 1 drift is 30 px (was 60).
  - Act 2 drift is 190 px at 0.42 (was 280 at 0.55).
- **Regent's Spear:** the subsystems are further from the body, at (∓0.21, −0.20) and (0, 0.22) (were ∓0.12/−0.18 and 0/0.08), so one splash can't hit the body and a subsystem together.
- **`Missions.BOSS_HP_SCALE`:** now **1.75 / 1.95 / 2.2 / 2.6 / 3.0 / 2.5** (was 1.45 / 1.95 / 2.2 / 2.45 / 2.2 / 2.3). Only bosses use it, so the economy is unaffected.
- **Pilot:** `content_balance` now goes for falling power cores while below L4, as a decent player does.

**Result:** median boss fight time in seconds (3 seeded runs each, Standard, expected equipment, god mode off). Every run was a win with 0 % hull lost.
| boss | Striker | Guardian | Arcanist | max/min |
|---|---|---|---|---|
| 1.08 Algol | 102 | 93 | 95 | 1.10 |
| 2.08 Furnace Sovereign | 114 | 98 | 91 | 1.25 |
| 3.08 Storm Seraph | 103 | 100 | 92 | 1.12 |
| 4.08 Null Oracle | 107 | 97 | 98 | 1.10 |
| 5.08 Regent's Spear | 114 | 92 | 96 | 1.24 |
| 6.08 Dominion Prime | 98 | 91 | 100 | 1.10 |

Every median is inside 90–180 s and every spread is at most 1.25×, against a 1.4× target. Run-to-run spread inside a cell is now 1–15 %; it was up to 2×.

### 6.04 "Three Anchors"
- The mission used to send one siege-barge anchor in each of waves 3, 6 and 9. Now all three arrive together in wave 5 in a new `triad` formation in `Encounter.expand`: 330 px apart, the centre one 70 px back, arrivals staggered by 0.5 s.
- Measured `objs_together=3` for all units. Results (time, hull lost):
  - Standard: S 90 s, G 94 s, A 89 s, all 0 % lost.
  - Veteran: S 84 s, G 94 s, A 83 s, all 0 % lost.

### 6.08 finale (real combat scene, pilot, god mode off, expected equipment)
- All 4 acts ran for all three units: act 1 gate after 8–11 s, act 2 about 35 s, act 3 about 25 s, act 4 about 14 s.
- **Checkpoint:** `checkpoint=3` (Guardian) starts at act 3, goes 3 → 4 → defeat in 43 s, and wins.
- **Ending route:** `route=1` (Striker) went through `Game.finish_combat` with victory=true and 334 credits, then `Router` to `ending`.
- **Captures:** `evidence/content_wave4/real_6.08_entry / phase1..4 / defeat.png` and `mont_6.08_acts.png` (these use capture `bhp=0.35`).

## 5. Wave 5 content pass: scale, boss phase visuals, training layout

*CONTENT, wave 5 (2026-09-25). Runs alongside COMBAT's player-craft scale-up (Striker/Arcanist 23 %, Guardian 26 % of the width).*

### Scale
- **Enemies ×1.2** (`enemies.gd`), hit radii scaled with them (still ~70 % of the visual half-width): fodder 176–180 px, assault 210–246, elites 306–400, dummies 170 / 330.
- **Formations** (`Encounter.expand`) widened to match: pair 420 px (was 360), line ≤ 240 px and ≤ 960/n (was 205, 900/n), triad 370 px with the centre one 80 px back, v 185, arc radius 390, column 180, flank 195, cross/sweep 195–205. Anchors are clamped to x 100–980.
- **Bosses** +4–6 % (Algol 740, Furnace 830, Seraph 900, Oracle 760, Spear 830, Dominion 830); part sprites ×1.1. Homes were moved down so each sprite's top edge sits at about y 225, below the HUD band and boss bar. The bottom edge stays above about y 1060, so the player keeps a band of at least 500 px. Boss minion anchors moved down 80 px to follow.
- **`Missions.BOSS_HP_SCALE`** is now **1.75 / 1.95 / 2.2 / 2.85 / 3.3 / 2.5** (ch4 and ch5 +10 %). The bigger, lower bodies took more hits and pushed 4.08 Guardian and 5.08 Arcanist under the 90 s floor (83 s and 85 s). The validator's boss-scale sanity cap is now 3.5.

### Boss median re-check (3 seeded runs, Standard, expected equipment)
Command as in §4, with `--fixed-fps 20` and `runs=3 seed=1`.

| boss | unit | wave 4 | wave 5 |
|---|---|---|---|
| 1.08 Algol | Striker | 102 | 110 |
| 2.08 Furnace Sovereign | Guardian | 98 | 99 |
| 3.08 Storm Seraph | Arcanist | 92 | 91 |
| 4.08 Null Oracle | Guardian | 97 | 93 (83 before the HP fix) |
| 4.08 Null Oracle | Striker | 107 | 119 |
| 5.08 Regent's Spear | Arcanist | 96 | 93 (85 before the HP fix) |
| 5.08 Regent's Spear | Guardian | 92 | 92 |
| 5.08 Regent's Spear | Striker | 114 | 121 |
| 6.08 Dominion Prime | Striker | 98 | 98 |

- Every checked median is inside 90–180 s.
- Checked spreads: 4.08 is 1.28× and 5.08 is 1.32×, against the 1.4× target.
- The Striker is now the slowest unit in ch4 and ch5, partly because of COMBAT's parallel player changes. Re-run the full 18-cell table once both waves have landed.

### Boss phase visuals
All drawn in code over the existing sprites, in `boss.gd` (`_build_phase_fx`, `_draw_phase_fx`, `_phase_tint`) and in `boss_part.gd` (burning sockets).
- **Geometry:** seeded per boss and phase with a private RNG, so the gameplay RNG is untouched.
- **Phase break:** 10 armor chunks shed and tumble for 2.2 s, and a 1.5 s hot flare shows on the new wounds.
- **Destroyed parts:** leave burning sockets with smoke, flame and sparks.
- **Per boss:**
  - Algol: plates torn off the ring, fractures along the ring, the scar opens into a molten slit. Phase 3 darkens the body; the sections orbit and the eye housing splits.
  - Furnace: phase 2 has permanently glowing vents, heat haze, burning stacks, seams and a warm tint. Phase 3 is red-hot with more haze.
  - Seraph: phase 2 has collapsed pylon mounts that arc to the hull. Phase 3 is the detached form, with blue afterimages and a crackling rim.
  - Oracle: phase 2 has dead sensors that flicker static and a dimmer shell. Phase 3 exposes the core, with a rotating iris and cracks.
  - Spear: phase 2 has hull fires and scorched fractures. Phase 3 adds more fires, a breach and a darker hull.
  - Dominion: act 2 unseals, with gold fractures and a rune ring. Act 3 has violet corruption. Act 4 is white-hot, with rays and broken crown plates.
- **Effect style:** thin lines at alpha 0.8 or less, smoke at alpha 0.42 or less. Enemy bullets stay on their own layer above.
- **Captures:** `evidence/content_w5/` has `boss_<id>_entry / phase1..N / defeat.jpg` and `mont_<id>_phases.jpg`, with capture-only `bhp=0.25`.

### Training
- All targets are now in the middle band, y 640–1140. The heavy dummy moved from y 330 to y 640, so its HP bar is clear of the unit chips.
- The cluster is at the left, the shielded pair at the right, and the mover at y 1140.
- Capture: `evidence/content_w5/training_guardian.jpg`.

## DPS (combat)

*COMBAT, wave 3 (2026-09-25). Harness: `HOME=/tmp/nshome godot --headless --path . res://tests/dps_bench.tscn [-- units=striker equip=base]` (manual stepping, no hostiles; exits with the number of failed TRB §07 checks, currently 0).*

**What's measured:** sustained damage per second over 6 s after a 1 s warm-up.
- `single` = one fodder-sized target (r 40) ~680 px ahead.
- `boss` = one boss-flagged target (r 110), so boss rules apply (half Solar heat, +10 % Void slug vs bosses).
- `cluster` = 7 targets (r 30) in a 90 px hex; the value is the **total** across all of them.
- `base` = no modules; `full` = all 6 families at tier 4. SUPER = L4 while the Super is active.

**How it's tuned:** `Arsenal.DPS_NORM[unit][level]` scales every damage path through `damage_mult()`, and `Arsenal.SUPER_NORM[unit]` keeps the measured Super/L4 at the unit's `super_damage_mult`.
Structural changes:
- Striker: L4 heat flare is smaller, and flare splash hits at most 2 neighbours at 0.25.
- Guardian: shell splash is limited to 3 targets at 0.25, and compression bursts are smaller. Null Torpedo damage is 24 (was 30) with a mark bonus of 6 (was 12). Bastion Eclipse adds a 3-torpedo siege salvo.
- Arcanist: more chain tokens with gentler falloff, so it clears groups better; overload on an isolated target is weaker.

| unit | equip | L1 single / boss / cluster | L2 | L3 | L4 | SUPER |
|---|---|---|---|---|---|---|
| Striker | base | **100** / 83 / 114 | 135 / 187 / 274 | 170 / 236 / 345 | **220** / 262 / 444 | **375** / 442 / 763 |
| Guardian | base | **85** / 94 / 106 | 115 / 127 / 197 | 145 / 160 / 250 | **187** / 296 / 465 | **281** / 412 / 761 |
| Arcanist | base | **80** / 80 / 213 | 108 / 108 / 257 | 136 / 190 / 380 | **176** / 246 / 582 | **282** / 390 / 821 |
| Striker | full | 208 / 176 / 232 | 281 / 369 / 516 | 386 / 498 / 683 | 442 / 510 / 819 | 847 / 985 / 1522 |
| Guardian | full | 153 / 158 / 190 | 207 / 214 / 349 | 391 / 400 / 771 | 412 / 588 / 902 | 691 / 940 / 1861 |
| Arcanist | full | 172 / 171 / 417 | 229 / 228 / 464 | 312 / 403 / 710 | 404 / 520 / 1098 | 635 / 850 / 1672 |

**Ratios** (base equipment):
- Focused DPS: Striker 100 : Guardian 85 : Arcanist 80 at every level.
- L4 is 2.2× L1.
- Super/L4 is 1.70 (S), 1.50 (G) and 1.60 (A).
- Clustered, Arcanist leads: 1.86× Striker at L1 and 1.31× at L4.

**Boss DPS spread** (max/min across units): 1.06 at L1 and 1.11 at L4 on base; 1.23 and 1.08 on full. Before this pass it was 2–3× (Striker 6.08 ~71 s vs Guardian 1.08 ~166 s).

**Full equipment** is about 2.0–2.3× base. Module hardware differs per unit: Guardian torpedoes only arrive from L3, so Guardian full L4/L1 is 2.7, and reactor tier 4 adds +0.2 to the Super multiplier.

**For content (HP re-tune):**
- The `EnemyDefs` "~100 DPS baseline" is now true: it's base Striker L1, single target.
- In a mission, base-equipment DPS spans roughly 80–220 (L1–L4) and 280–375 during Supers.
- At the chapter's expected equipment, multiply by about 1 + 0.045 × installed tiers (≈1.9× at 20 tiers).
- The old measured ~250–300 DPS came from the un-normalized L4/heat/compression spikes (Striker base L4 was 557 single, 1717 clustered). The chapter HP scales (1.3…2.3) were compensating for that and can come down.
