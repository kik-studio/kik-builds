# Game-feel report · build 0.18+82474e7

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.01 |
| Longest empty gap (s) | ≤ 3.0 | 2/3 ⚠️ | 1.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 13.4 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.28 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.0 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 3.03 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 93.8 | 1 | 1.0 | 0 | 13.9 | 15/24/32/28 | 100% | 3.68 | 4 | – |
| 1.05 | striker | victory | 93.0 | 4 | 3.3 | 1 | 13.4 | 14/34/23/29 | 100% | 3.03 | 3 | Longest empty gap (s) |
| 2.01 | striker | victory | 85.6 | 0 | 0.0 | 0 | 12.5 | 15/32/31/23 | 100% | 2.68 | 3 | – |
