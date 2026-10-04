# Game-feel report · build 0.9+13e5b9c

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.04 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 13.5 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.22 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.0 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 3.27 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 97.0 | 5 | 1.0 | 0 | 13.6 | 14/23/33/30 | 100% | 4.08 | 4 | – |
| 1.05 | striker | victory | 84.7 | 2 | 1.5 | 0 | 13.3 | 16/24/38/21 | 100% | 3.27 | 3 | – |
| 2.01 | striker | victory | 85.8 | 4 | 1.0 | 0 | 13.5 | 16/26/37/22 | 98% | 2.61 | 3 | – |
