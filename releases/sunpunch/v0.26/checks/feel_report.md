# Game-feel report · build 0.26+bdf8e1d

Automated: measured from 11 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.15 | 11/11 ✅ | 0.0 |
| Longest empty gap (s) | ≤ 3.0 | 11/11 ✅ | 0.0 |
| Empty gaps over 2 s | ≤ 1 | 11/11 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 40 | 0/11 ⚠️ | 123.7 |
| Time at top power level (share) | ≥ 0.0 | 11/11 ✅ | 0.0 |
| Pickups collected (share) | ≥ 0.7 | 10/11 ⚠️ | 1.0 |
| Bot deaths | ≤ 1 | 11/11 ✅ | 1 |
| Mean enemies on screen | ≥ 1.0 | 11/11 ✅ | 6.86 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| level_06 | spark | defeat | 20.4 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 6.86 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 12.6 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 6.38 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 10.5 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 6.27 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 18.0 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 6.74 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 6.9 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 5.86 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 7.0 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 5.86 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 163.1 | 0 | 0.0 | 0 | 137.8 | 84/16/0/0 | 100% | 8.25 | 1 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 149.9 | 0 | 0.0 | 0 | None | 100/0/0/0 | 100% | 9.4 | 0 | Time to first power-up P2 (s) |
| level_06 | spark | defeat | 110.4 | 0 | 0.0 | 0 | None | 100/0/0/0 | 100% | 9.08 | 0 | Time to first power-up P2 (s) |
| level_07 | spark | defeat | 126.3 | 0 | 0.0 | 0 | 109.6 | 87/13/0/0 | 94% | 10.65 | 0 | Time to first power-up P2 (s) |
| level_07 | spark | unknown | 93.0 | 0 | 0.0 | 0 | None | 100/0/0/0 | 36% | 11.59 | 0 | Time to first power-up P2 (s), Pickups collected (share) |
