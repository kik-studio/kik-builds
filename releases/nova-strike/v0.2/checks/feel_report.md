# Game-feel report · build 0.1.0+f74f6b0

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.03 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.1 |
| Empty gaps over 2 s | ≤ 1 | 2/3 ⚠️ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 12.5 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.67 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.0 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 2.21 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 77.5 | 7 | 2.7 | 2 | 12.5 | 16/12/4/67 | 100% | 2.37 | 3 | Empty gaps over 2 s |
| 1.05 | striker | victory | 80.4 | 1 | 1.1 | 0 | 10.2 | 13/6/9/73 | 100% | 2.15 | 3 | – |
| 2.01 | striker | victory | 81.8 | 2 | 1.0 | 0 | 17.0 | 21/7/11/62 | 100% | 2.21 | 2 | – |
