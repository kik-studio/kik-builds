# Game-feel report · build 0.7+58ddb97

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.0 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 0.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 13.3 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.38 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.0 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 3.24 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 104.5 | 0 | 0.0 | 0 | 9.1 | 9/22/31/38 | 100% | 4.52 | 3 | – |
| 1.05 | striker | victory | 112.6 | 0 | 0.0 | 0 | 13.3 | 12/23/23/43 | 100% | 2.83 | 1 | – |
| 2.01 | striker | victory | 85.0 | 2 | 1.0 | 0 | 17.2 | 20/19/40/21 | 100% | 3.24 | 2 | – |
