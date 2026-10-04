# Game-feel report · build 0.7+52b2075

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.15 | 0/3 ⚠️ | 0.54 |
| Longest empty gap (s) | ≤ 3.0 | 0/3 ⚠️ | 19.0 |
| Empty gaps over 2 s | ≤ 1 | 0/3 ⚠️ | 3 |
| Time to first power-up P2 (s) | ≤ 40 | 3/3 ✅ | 13.3 |
| Time at top power level (share) | ≥ 0.0 | 3/3 ✅ | 0.0 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 1.08 |
| Bot deaths | ≤ 1 | 3/3 ✅ | 0 |
| Mean enemies on screen | ≥ 1.0 | 0/3 ⚠️ | 0.61 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| level_01 | spark | survived | 69.0 | 54 | 19.0 | 3 | 13.3 | 19/40/41/0 | 108% | 0.61 | 1 | Empty screen time (share of play), Longest empty gap (s), Empty gaps over 2 s, Mean enemies on screen |
| level_01 | spark | survived | 69.0 | 54 | 19.0 | 3 | 13.3 | 19/40/41/0 | 108% | 0.61 | 1 | Empty screen time (share of play), Longest empty gap (s), Empty gaps over 2 s, Mean enemies on screen |
| level_01 | spark | survived | 69.0 | 55 | 19.0 | 3 | 13.3 | 19/27/54/0 | 107% | 0.6 | 1 | Empty screen time (share of play), Longest empty gap (s), Empty gaps over 2 s, Mean enemies on screen |
