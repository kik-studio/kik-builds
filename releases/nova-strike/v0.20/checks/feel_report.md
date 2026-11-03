# Game-feel report · build 0.20+6c5f495

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.0 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 0.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 13.3 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.26 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.0 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 3.36 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 101.2 | 0 | 0.0 | 0 | 21.7 | 21/12/34/33 | 100% | 3.9 | 4 | – |
| 1.05 | striker | victory | 88.7 | 2 | 1.3 | 0 | 13.3 | 15/29/30/26 | 100% | 3.36 | 2 | – |
| 2.01 | striker | victory | 84.0 | 0 | 0.0 | 0 | 13.0 | 17/28/34/21 | 99% | 3.13 | 3 | – |
