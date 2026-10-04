# Game-feel report · build 0.9+52b2075

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.03 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 13.4 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.28 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.0 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 2.97 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 94.8 | 3 | 1.4 | 0 | 13.4 | 14/20/37/28 | 100% | 3.98 | 4 | – |
| 1.05 | striker | victory | 95.3 | 4 | 1.0 | 0 | 15.4 | 16/20/35/28 | 100% | 2.97 | 3 | – |
| 2.01 | striker | victory | 86.6 | 1 | 1.0 | 0 | 12.8 | 15/27/34/25 | 100% | 2.49 | 3 | – |
