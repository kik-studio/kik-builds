# Game-feel report · build 0.3+496d427

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.04 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.5 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 12.6 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.6 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.0 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 2.19 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 78.4 | 6 | 2.8 | 1 | 6.5 | 8/8/12/72 | 100% | 2.79 | 3 | – |
| 1.05 | striker | victory | 80.2 | 4 | 1.0 | 0 | 18.2 | 23/6/13/58 | 100% | 2.19 | 2 | – |
| 2.01 | striker | victory | 81.5 | 2 | 1.5 | 0 | 12.6 | 15/12/12/60 | 100% | 2.09 | 2 | – |
