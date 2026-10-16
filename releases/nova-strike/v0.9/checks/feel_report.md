# Game-feel report · build 0.9+0a16bff

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.01 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 13.5 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.35 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.0 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 2.8 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 101.3 | 1 | 1.2 | 0 | 13.5 | 13/20/32/35 | 100% | 4.02 | 4 | – |
| 1.05 | striker | victory | 115.9 | 1 | 1.0 | 0 | 13.8 | 12/19/32/37 | 99% | 2.75 | 2 | – |
| 2.01 | striker | victory | 86.2 | 0 | 0.0 | 0 | 13.3 | 15/25/36/24 | 100% | 2.8 | 3 | – |
