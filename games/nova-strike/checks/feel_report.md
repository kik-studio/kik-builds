# Game-feel report · build 0.8+7d30bcb

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.01 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 13.2 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0.4 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.0 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 2.9 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 110.9 | 2 | 1.0 | 0 | 9.1 | 8/21/28/43 | 100% | 4.44 | 3 | – |
| 1.05 | striker | victory | 109.9 | 1 | 1.0 | 0 | 13.3 | 12/19/29/40 | 99% | 2.9 | 1 | – |
| 2.01 | striker | victory | 84.2 | 1 | 1.0 | 0 | 13.2 | 16/28/33/23 | 100% | 2.86 | 2 | – |
