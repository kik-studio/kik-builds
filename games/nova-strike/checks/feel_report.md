# Game-feel report · build 0.7+1975f2e

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.01 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 13.5 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.31 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 0.99 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 2.81 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 94.9 | 1 | 1.0 | 0 | 9.1 | 10/24/35/31 | 100% | 3.82 | 3 | – |
| 1.05 | striker | victory | 114.1 | 0 | 0.0 | 0 | 13.5 | 12/18/27/43 | 99% | 2.81 | 1 | – |
| 2.01 | striker | victory | 90.4 | 3 | 1.0 | 0 | 15.1 | 17/24/33/27 | 98% | 2.6 | 2 | – |
