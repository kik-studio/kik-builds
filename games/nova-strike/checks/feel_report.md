# Game-feel report · build 0.8+94735e9

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.02 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.6 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 14.1 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.31 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.0 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 2.72 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 98.7 | 2 | 1.2 | 0 | 14.1 | 14/18/36/31 | 100% | 3.71 | 4 | – |
| 1.05 | striker | victory | 110.8 | 1 | 1.6 | 0 | 14.3 | 13/18/29/40 | 100% | 2.72 | 3 | – |
| 2.01 | striker | victory | 86.4 | 2 | 1.7 | 0 | 14.0 | 16/26/32/26 | 100% | 2.44 | 3 | – |
