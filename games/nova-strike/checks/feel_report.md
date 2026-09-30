# Game-feel report · build 0.6+922baeb

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.02 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 6.6 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.73 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 0.99 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 2.69 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 87.0 | 0 | 0.0 | 0 | 4.9 | 6/2/8/85 | 99% | 3.84 | 3 | – |
| 1.05 | striker | victory | 89.1 | 2 | 1.7 | 0 | 8.1 | 9/5/13/73 | 98% | 2.09 | 2 | – |
| 2.01 | striker | victory | 82.1 | 5 | 1.0 | 0 | 6.6 | 8/16/10/66 | 99% | 2.69 | 2 | – |
