# Game-feel report · build 0.5+efc92e6

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.15 | 0/3 ⚠️ | 0.32 |
| Longest empty gap (s) | ≤ 3.0 | 0/3 ⚠️ | 12.0 |
| Empty gaps over 2 s | ≤ 1 | 0/3 ⚠️ | 4 |
| Time to first power-up P2 (s) | ≤ 40 | 3/3 ✅ | 15.1 |
| Time at top power level (share) | ≥ 0.0 | 3/3 ✅ | 0.18 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.32 |
| Bot deaths | ≤ 1 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 1.0 | 3/3 ✅ | 1.08 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| reef_run_m3 | spark | survived | 72.0 | 32 | 12.0 | 4 | 15.1 | 21/23/38/18 | 132% | 1.08 | 1 | Empty screen time (share of play), Longest empty gap (s), Empty gaps over 2 s |
| reef_run_m3 | spark | survived | 72.0 | 32 | 12.0 | 4 | 15.1 | 21/23/38/18 | 132% | 1.08 | 1 | Empty screen time (share of play), Longest empty gap (s), Empty gaps over 2 s |
| reef_run_m3 | spark | survived | 73.0 | 27 | 10.0 | 3 | 16.1 | 22/22/30/25 | 127% | 1.19 | 1 | Empty screen time (share of play), Longest empty gap (s), Empty gaps over 2 s |
