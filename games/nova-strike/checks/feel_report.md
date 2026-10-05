# Game-feel report · build 0.9+f729138

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.01 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 13.2 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.26 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.0 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 2.92 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 90.9 | 3 | 1.5 | 0 | 13.4 | 15/22/38/26 | 100% | 3.84 | 4 | – |
| 1.05 | striker | victory | 114.7 | 0 | 0.0 | 0 | 13.1 | 11/18/32/39 | 100% | 2.73 | 2 | – |
| 2.01 | striker | victory | 87.7 | 1 | 1.0 | 0 | 13.2 | 15/25/34/26 | 99% | 2.92 | 3 | – |
