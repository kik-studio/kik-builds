# Game-feel report · build 0.5+9595356

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.0 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 0.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 8.2 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.76 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 0.99 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 3.59 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 106.5 | 0 | 0.0 | 0 | 4.4 | 4/6/3/87 | 99% | 4.97 | 3 | – |
| 1.05 | striker | victory | 111.1 | 0 | 0.0 | 0 | 12.2 | 11/6/16/67 | 98% | 3.59 | 2 | – |
| 2.01 | striker | victory | 87.8 | 1 | 1.0 | 0 | 8.2 | 9/10/4/76 | 100% | 2.71 | 2 | – |
