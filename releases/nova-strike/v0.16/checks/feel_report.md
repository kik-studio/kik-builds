# Game-feel report · build 0.16+df14974

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.0 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 0.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 14.2 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.22 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 0.99 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 3.05 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 91.5 | 0 | 0.0 | 0 | 18.1 | 20/24/30/26 | 100% | 3.99 | 4 | – |
| 1.05 | striker | victory | 85.5 | 0 | 0.0 | 0 | 14.2 | 17/24/38/22 | 99% | 3.05 | 3 | – |
| 2.01 | striker | victory | 83.2 | 0 | 0.0 | 0 | 13.8 | 17/25/37/22 | 100% | 2.86 | 3 | – |
