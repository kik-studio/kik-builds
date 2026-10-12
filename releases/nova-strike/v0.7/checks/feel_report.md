# Game-feel report · build 0.7+b5fe72a

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.0 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 0.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 14.1 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.36 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.0 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 3.65 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 98.0 | 0 | 0.0 | 0 | 9.1 | 9/23/32/36 | 100% | 4.33 | 3 | – |
| 1.05 | striker | victory | 106.4 | 0 | 0.0 | 0 | 14.1 | 13/17/28/41 | 100% | 3 | 1 | – |
| 2.01 | striker | victory | 86.8 | 1 | 1.0 | 0 | 18.0 | 21/16/42/21 | 100% | 3.65 | 2 | – |
