# Game-feel report · build 0.7+5975cb8

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.0 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 0.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 6.6 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.71 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 0.98 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 3.01 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 96.5 | 0 | 0.0 | 0 | 5.0 | 5/4/6/85 | 98% | 4.52 | 3 | – |
| 1.05 | striker | victory | 91.9 | 0 | 0.0 | 0 | 6.6 | 7/5/16/71 | 97% | 3.01 | 2 | – |
| 2.01 | striker | victory | 83.2 | 1 | 1.1 | 0 | 7.2 | 9/6/18/68 | 100% | 2.7 | 2 | – |
