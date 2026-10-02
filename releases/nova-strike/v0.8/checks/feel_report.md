# Game-feel report · build 0.8+0436c0a

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.01 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.1 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 13.9 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.26 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.0 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 2.83 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 93.8 | 4 | 1.4 | 0 | 13.9 | 15/21/36/28 | 100% | 3.93 | 4 | – |
| 1.05 | striker | victory | 86.3 | 0 | 0.0 | 0 | 13.4 | 16/24/36/25 | 100% | 2.83 | 3 | – |
| 2.01 | striker | victory | 86.4 | 1 | 1.1 | 0 | 14.6 | 17/23/34/26 | 100% | 2.59 | 3 | – |
