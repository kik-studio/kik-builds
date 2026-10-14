# Game-feel report · build 0.17+7fb91ae

Automated: measured from 18 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.15 | 18/18 ✅ | 0.0 |
| Longest empty gap (s) | ≤ 3.0 | 18/18 ✅ | 0.0 |
| Empty gaps over 2 s | ≤ 1 | 18/18 ✅ | 0.0 |
| Time to first power-up P2 (s) | ≤ 40 | 7/18 ⚠️ | 28.45 |
| Time at top power level (share) | ≥ 0.0 | 18/18 ✅ | 0.0 |
| Pickups collected (share) | ≥ 0.7 | 14/18 ⚠️ | 0.86 |
| Bot deaths | ≤ 1 | 18/18 ✅ | 1.0 |
| Mean enemies on screen | ≥ 1.0 | 18/18 ✅ | 2.07 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| level_06 | spark | defeat | 63.8 | 2 | 1.0 | 0 | 28.0 | 44/36/20/0 | 69% | 2.44 | 0 | Pickups collected (share) |
| level_06 | spark | defeat | 38.3 | 0 | 0.0 | 0 | None | 100/0/0/0 | 59% | 1.77 | 0 | Time to first power-up P2 (s), Pickups collected (share) |
| level_06 | spark | defeat | 18.2 | 0 | 0.0 | 0 | None | 100/0/0/0 | 100% | 1.89 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 11.0 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 2 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 10.8 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 2 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 16.3 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 2.12 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 45.0 | 2 | 1.0 | 0 | 26.5 | 59/41/0/0 | 96% | 2.02 | 0 | – |
| level_06 | spark | defeat | 55.4 | 0 | 0.0 | 0 | None | 100/0/0/0 | 56% | 2.68 | 0 | Time to first power-up P2 (s), Pickups collected (share) |
| level_06 | spark | defeat | 51.9 | 2 | 1.0 | 0 | 27.7 | 53/45/1/0 | 92% | 2.29 | 0 | – |
| level_07 | spark | defeat | 8.9 | 0 | 0.0 | 0 | None | 100/0/0/0 | 0% | 1.56 | 0 | Time to first power-up P2 (s), Pickups collected (share) |
| level_07 | spark | defeat | 31.6 | 0 | 0.0 | 0 | 28.5 | 90/10/0/0 | 75% | 2.5 | 0 | – |
| level_07 | spark | defeat | 83.0 | 0 | 0.0 | 0 | 29.0 | 35/29/13/23 | 88% | 2.55 | 0 | – |
| level_07 | spark | defeat | 6.7 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 2 | 0 | Time to first power-up P2 (s) |
| level_07 | spark | defeat | 4.5 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 2 | 0 | Time to first power-up P2 (s) |
| level_07 | spark | defeat | 6.7 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 2 | 0 | Time to first power-up P2 (s) |
| level_07 | spark | victory | 233.7 | 0 | 1.0 | 0 | 40.5 | 17/5/5/73 | 86% | 2.5 | 1 | Time to first power-up P2 (s) |
| level_07 | spark | defeat | 106.3 | 0 | 0.0 | 0 | 28.4 | 27/22/12/39 | 89% | 2.57 | 1 | – |
| level_07 | spark | victory | 212.7 | 1 | 2.0 | 1 | 28.5 | 13/17/18/52 | 86% | 2.56 | 1 | – |
