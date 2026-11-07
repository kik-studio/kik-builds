# Game-feel report · build 0.25+86c374e

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Unknown | Median |
|---|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0 | 0.0 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 0 | 0.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 0 | 14.4 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0 | 0.44 |
| Pickups collected (share) | ≥ 0.7 | 2/3 ⚠️ | 0 | 0.72 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 0 | 3.08 |

**Unknown checks: 0** (none)

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 87.1 | 0 | 0.0 | 0 | 15.5 | 18/14/20/48 | 65% | 3.78 | 4 | Pickups collected (share) |
| 1.05 | striker | victory | 84.8 | 1 | 1.0 | 0 | 12.1 | 14/33/13/39 | 72% | 3.08 | 3 | – |
| 2.01 | striker | victory | 80.3 | 0 | 0.0 | 0 | 14.4 | 18/21/17/44 | 77% | 2.78 | 3 | – |
