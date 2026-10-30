# Game-feel report · build 0.22+148813e

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.0 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 0.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 12.0 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.28 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 0.95 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 3.42 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 91.0 | 0 | 0.0 | 0 | 15.5 | 17/19/36/28 | 95% | 3.63 | 4 | – |
| 1.05 | striker | victory | 92.6 | 2 | 1.0 | 0 | 10.5 | 11/32/27/30 | 99% | 3.42 | 2 | – |
| 2.01 | striker | victory | 85.1 | 0 | 0.0 | 0 | 12.0 | 14/28/31/27 | 96% | 2.49 | 3 | – |
