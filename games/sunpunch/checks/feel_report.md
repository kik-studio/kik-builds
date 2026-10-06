# Game-feel report · build 0.8+c8a2b4d

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.15 | 3/3 ✅ | 0.07 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 2.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 40 | 3/3 ✅ | 13.5 |
| Time at top power level (share) | ≥ 0.0 | 3/3 ✅ | 0.14 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.04 |
| Bot deaths | ≤ 1 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 1.0 | 3/3 ✅ | 1.17 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| level_01 | spark | victory | 57.5 | 7 | 2.0 | 0 | 13.5 | 23/29/34/14 | 104% | 1.17 | 1 | – |
| level_01 | spark | victory | 57.5 | 9 | 2.0 | 0 | 13.5 | 24/28/24/24 | 109% | 1.21 | 1 | – |
| level_01 | spark | victory | 57.5 | 7 | 2.0 | 0 | 13.5 | 23/29/34/14 | 104% | 1.17 | 1 | – |
