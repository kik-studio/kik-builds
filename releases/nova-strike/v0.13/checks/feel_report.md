# Game-feel report · build 0.12+4e810f5

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.01 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 13.0 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.28 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.0 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 3.11 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 91.9 | 2 | 1.5 | 0 | 13.0 | 14/30/28/28 | 100% | 4.23 | 4 | – |
| 1.05 | striker | victory | 114.5 | 1 | 1.0 | 0 | 11.5 | 10/20/30/40 | 100% | 2.44 | 2 | – |
| 2.01 | striker | victory | 88.0 | 0 | 0.0 | 0 | 13.9 | 16/27/32/25 | 99% | 3.11 | 3 | – |
