# Game-feel report · build 0.1.0+85e2f8f

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0.01 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 1.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 2/3 ⚠️ | 16.3 |
| Time at top power level (share) | ≥ 0.2 | 0/3 ⚠️ | 0.0 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 0.92 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 2.48 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 81.3 | 0 | 0.0 | 0 | 16.3 | 20/72/8/0 | 92% | 3.01 | 3 | Time at top power level (share) |
| 1.05 | striker | victory | 84.6 | 1 | 1.0 | 0 | 48.5 | 57/4/39/0 | 86% | 2.48 | 2 | Time to first power-up P2 (s), Time at top power level (share) |
| 2.01 | striker | victory | 84.2 | 1 | 1.0 | 0 | 15.7 | 19/21/49/11 | 93% | 2.28 | 3 | Time at top power level (share) |
