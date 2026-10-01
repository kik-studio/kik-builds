# Game-feel report · build 0.7+10cb441

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.02 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 11.3 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.26 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.0 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 2.83 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 96.7 | 2 | 1.0 | 0 | 9.1 | 9/26/32/33 | 100% | 4.74 | 3 | – |
| 1.05 | striker | victory | 86.1 | 1 | 1.0 | 0 | 15.4 | 18/19/37/26 | 100% | 2.83 | 2 | – |
| 2.01 | striker | victory | 85.9 | 4 | 1.0 | 0 | 11.3 | 13/26/37/24 | 100% | 2.49 | 2 | – |
