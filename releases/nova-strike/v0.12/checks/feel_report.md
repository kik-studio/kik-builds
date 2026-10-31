# Game-feel report · build 0.10+eb75b6d

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.01 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 14.3 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.26 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.0 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 2.65 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 89.7 | 1 | 1.3 | 0 | 21.3 | 24/16/34/26 | 100% | 3.94 | 4 | – |
| 1.05 | striker | victory | 111.1 | 1 | 1.0 | 0 | 14.3 | 13/20/28/39 | 100% | 2.65 | 2 | – |
| 2.01 | striker | victory | 86.5 | 1 | 1.0 | 0 | 13.8 | 16/26/35/23 | 100% | 2.65 | 3 | – |
