# Game-feel report · build 0.1.0+e83ae23

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 2/3 ⚠️ | 0.09 |
| Longest empty gap (s) | ≤ 3.0 | 1/3 ⚠️ | 3.1 |
| Empty gaps over 2 s | ≤ 1 | 1/3 ⚠️ | 2 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 13.6 |
| Time at top power level (share) | ≥ 0.2 | 1/3 ⚠️ | 0.15 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 0.88 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 2/3 ⚠️ | 2.1 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 84.3 | 16 | 3.1 | 3 | 11.4 | 14/22/35/29 | 100% | 1.36 | 2 | Empty screen time (share of play), Longest empty gap (s), Empty gaps over 2 s, Mean enemies on screen |
| 1.05 | striker | victory | 86.0 | 4 | 2.1 | 1 | 20.8 | 24/29/33/14 | 73% | 2.26 | 2 | Time at top power level (share) |
| 2.01 | striker | victory | 85.5 | 9 | 3.1 | 2 | 13.6 | 16/38/31/15 | 88% | 2.1 | 2 | Longest empty gap (s), Empty gaps over 2 s, Time at top power level (share) |
