# Game-feel report · build 0.19+7d735d7

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.01 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 15.8 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.27 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 0.99 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 3.36 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 93.5 | 0 | 0.0 | 0 | 21.2 | 23/18/31/28 | 99% | 4.08 | 4 | – |
| 1.05 | striker | victory | 87.8 | 1 | 1.0 | 0 | 15.8 | 18/21/39/22 | 98% | 3.36 | 2 | – |
| 2.01 | striker | victory | 92.6 | 1 | 1.0 | 0 | 14.3 | 23/33/17/27 | 99% | 2.73 | 3 | – |
