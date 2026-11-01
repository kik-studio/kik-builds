# Game-feel report · build 0.4+0a00b06

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.03 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 11.6 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.73 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 0.94 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 2.38 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 78.4 | 2 | 2.0 | 0 | 5.8 | 7/10/9/73 | 93% | 2.87 | 3 | – |
| 1.05 | striker | victory | 82.9 | 0 | 0.0 | 0 | 12.3 | 15/2/8/76 | 100% | 2.38 | 3 | – |
| 2.01 | striker | victory | 81.3 | 3 | 1.0 | 0 | 11.6 | 14/2/11/73 | 94% | 2.3 | 2 | – |
