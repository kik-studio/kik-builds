# Game-feel report · build 0.11+e6c5ec9

Automated: measured from 18 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.15 | 18/18 ✅ | 0.0 |
| Longest empty gap (s) | ≤ 3.0 | 18/18 ✅ | 0.0 |
| Empty gaps over 2 s | ≤ 1 | 18/18 ✅ | 0.0 |
| Time to first power-up P2 (s) | ≤ 40 | 4/18 ⚠️ | 27.3 |
| Time at top power level (share) | ≥ 0.0 | 18/18 ✅ | 0.0 |
| Pickups collected (share) | ≥ 0.7 | 15/18 ⚠️ | 0.97 |
| Bot deaths | ≤ 1 | 18/18 ✅ | 1.0 |
| Mean enemies on screen | ≥ 1.0 | 18/18 ✅ | 2.01 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| level_06 | spark | defeat | 27.4 | 0 | 0.0 | 0 | None | 100/0/0/0 | 67% | 1.89 | 0 | Time to first power-up P2 (s), Pickups collected (share) |
| level_06 | spark | defeat | 28.2 | 0 | 0.0 | 0 | None | 100/0/0/0 | 100% | 1.83 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 20.2 | 0 | 0.0 | 0 | None | 100/0/0/0 | 100% | 1.86 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 10.4 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 1.91 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 10.4 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 2 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 10.3 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 2 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 68.9 | 0 | 0.0 | 0 | 27.2 | 40/34/26/0 | 97% | 2.36 | 0 | – |
| level_06 | spark | defeat | 64.0 | 0 | 0.0 | 0 | 51.3 | 80/18/2/0 | 100% | 2.05 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 64.2 | 0 | 0.0 | 0 | 50.8 | 79/19/2/0 | 100% | 2.03 | 0 | Time to first power-up P2 (s) |
| level_07 | spark | defeat | 21.0 | 0 | 0.0 | 0 | None | 100/0/0/0 | 100% | 2.41 | 0 | Time to first power-up P2 (s) |
| level_07 | spark | defeat | 15.4 | 0 | 0.0 | 0 | None | 100/0/0/0 | 46% | 2.19 | 0 | Time to first power-up P2 (s), Pickups collected (share) |
| level_07 | spark | defeat | 15.4 | 0 | 0.0 | 0 | None | 100/0/0/0 | 55% | 2.19 | 0 | Time to first power-up P2 (s), Pickups collected (share) |
| level_07 | spark | defeat | 6.8 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 2 | 0 | Time to first power-up P2 (s) |
| level_07 | spark | defeat | 4.5 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 2 | 0 | Time to first power-up P2 (s) |
| level_07 | spark | defeat | 4.5 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 2 | 0 | Time to first power-up P2 (s) |
| level_07 | spark | defeat | 73.2 | 0 | 0.0 | 0 | 26.9 | 37/63/0/0 | 94% | 3.65 | 0 | – |
| level_07 | spark | defeat | 99.7 | 0 | 0.0 | 0 | 27.4 | 28/24/26/23 | 97% | 3.42 | 1 | – |
| level_07 | spark | defeat | 73.2 | 0 | 0.0 | 0 | 26.5 | 36/64/0/0 | 94% | 3.64 | 0 | – |
