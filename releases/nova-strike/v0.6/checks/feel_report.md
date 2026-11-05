# Game-feel report · build 0.6+e3fc4f4

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.02 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.5 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 8.6 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.82 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 0.99 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 2.58 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 89.3 | 1 | 1.0 | 0 | 4.5 | 5/3/7/85 | 99% | 4 | 3 | – |
| 1.05 | striker | victory | 85.4 | 2 | 2.1 | 1 | 8.6 | 10/4/15/71 | 98% | 2.58 | 2 | – |
| 2.01 | striker | victory | 87.3 | 2 | 1.5 | 0 | 9.2 | 10/2/6/82 | 99% | 2.56 | 2 | – |
