# Game-feel report · build 0.22+local

Automated: measured from 18 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.15 | 18/18 ✅ | 0.0 |
| Longest empty gap (s) | ≤ 3.0 | 18/18 ✅ | 0.0 |
| Empty gaps over 2 s | ≤ 1 | 18/18 ✅ | 0.0 |
| Time to first power-up P2 (s) | ≤ 40 | 2/18 ⚠️ | 27.85 |
| Time at top power level (share) | ≥ 0.0 | 18/18 ✅ | 0.0 |
| Pickups collected (share) | ≥ 0.7 | 17/18 ⚠️ | 1.0 |
| Bot deaths | ≤ 1 | 18/18 ✅ | 1.0 |
| Mean enemies on screen | ≥ 1.0 | 18/18 ✅ | 4.71 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| level_06 | spark | defeat | 7.9 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 4 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 14.2 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 5.07 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 11.6 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 4.67 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 9.4 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 4.4 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 9.3 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 4.4 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 6.3 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 3.86 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 114.2 | 0 | 0.0 | 0 | 27.4 | 24/76/0/0 | 100% | 6.46 | 0 | – |
| level_06 | spark | defeat | 175.4 | 0 | 0.0 | 0 | None | 100/0/0/0 | 100% | 5.65 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 164.7 | 0 | 0.0 | 0 | 28.3 | 17/83/0/0 | 100% | 5.01 | 0 | – |
| level_07 | spark | defeat | 11.9 | 0 | 0.0 | 0 | None | 100/0/0/0 | 0% | 4.5 | 0 | Time to first power-up P2 (s), Pickups collected (share) |
| level_07 | spark | defeat | 22.2 | 0 | 0.0 | 0 | None | 100/0/0/0 | 100% | 5.74 | 0 | Time to first power-up P2 (s) |
| level_07 | spark | defeat | 15.7 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 4.75 | 0 | Time to first power-up P2 (s) |
| level_07 | spark | defeat | 5.6 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 4 | 0 | Time to first power-up P2 (s) |
| level_07 | spark | defeat | 4.2 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 3.8 | 0 | Time to first power-up P2 (s) |
| level_07 | spark | defeat | 5.4 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 4 | 0 | Time to first power-up P2 (s) |
| level_07 | spark | defeat | 84.1 | 0 | 0.0 | 0 | None | 100/0/0/0 | 100% | 8.06 | 0 | Time to first power-up P2 (s) |
| level_07 | spark | defeat | 99.3 | 0 | 0.0 | 0 | None | 100/0/0/0 | 100% | 7.54 | 0 | Time to first power-up P2 (s) |
| level_07 | spark | survived | 257.0 | 0 | 0.0 | 0 | None | 100/0/0/0 | 72% | 6.37 | 0 | Time to first power-up P2 (s) |
