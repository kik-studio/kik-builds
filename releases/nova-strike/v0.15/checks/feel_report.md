# Game-feel report · build 0.14+0f96989

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.01 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 13.3 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.23 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 0.99 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 2.89 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 94.5 | 1 | 1.0 | 0 | 13.3 | 14/25/31/30 | 99% | 3.87 | 4 | – |
| 1.05 | striker | victory | 85.8 | 1 | 1.0 | 0 | 14.3 | 17/22/38/23 | 99% | 2.89 | 3 | – |
| 2.01 | striker | victory | 82.7 | 0 | 0.0 | 0 | 13.0 | 16/26/39/20 | 99% | 2.32 | 3 | – |
