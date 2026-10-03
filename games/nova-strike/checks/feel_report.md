# Game-feel report · build 0.9+da2ee65

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.02 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 12.9 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.34 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.0 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 3.06 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 102.2 | 4 | 1.8 | 0 | 12.9 | 13/20/34/34 | 100% | 3.93 | 5 | – |
| 1.05 | striker | victory | 116.9 | 2 | 1.0 | 0 | 12.7 | 11/26/19/44 | 100% | 2.75 | 2 | – |
| 2.01 | striker | victory | 85.9 | 0 | 0.0 | 0 | 13.0 | 15/27/35/24 | 100% | 3.06 | 3 | – |
