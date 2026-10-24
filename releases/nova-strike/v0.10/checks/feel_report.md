# Game-feel report · build 0.9+4a7fa54

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.01 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 15.1 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.32 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.0 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 2.81 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 101.7 | 1 | 1.4 | 0 | 13.6 | 13/23/32/32 | 100% | 4.04 | 4 | – |
| 1.05 | striker | victory | 115.5 | 3 | 1.0 | 0 | 15.5 | 13/14/32/41 | 100% | 2.81 | 2 | – |
| 2.01 | striker | victory | 86.1 | 1 | 1.0 | 0 | 15.1 | 18/24/37/22 | 100% | 2.72 | 3 | – |
