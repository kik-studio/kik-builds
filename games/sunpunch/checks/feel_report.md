# Game-feel report · build 0.2+5975cb8

Automated: measured from 5 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.15 | 5/5 ✅ | 0.0 |
| Longest empty gap (s) | ≤ 3.0 | 5/5 ✅ | 0.0 |
| Empty gaps over 2 s | ≤ 1 | 5/5 ✅ | 0 |
| Time to first power-up P2 (s) | ≤ 999 | 0/5 ⚠️ | – |
| Time at top power level (share) | ≥ 0.0 | 5/5 ✅ | 1.0 |
| Pickups collected (share) | ≥ 0.7 | 5/5 ✅ | – |
| Bot deaths | ≤ 1 | 5/5 ✅ | 0 |
| Mean enemies on screen | ≥ 1.0 | 5/5 ✅ | 1.77 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| reef_run_m1 | spark | defeat | 43.9 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 1.73 | 1 | Time to first power-up P2 (s) |
| reef_run_m1 | spark | survived | 21.5 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 1.86 | 0 | Time to first power-up P2 (s) |
| reef_run_m1 | spark | survived | 73.0 | 1 | 1.0 | 0 | None | 100/0/0/0 | – | 1.77 | 2 | Time to first power-up P2 (s) |
| reef_run_m1 | spark | defeat | 43.9 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 1.73 | 1 | Time to first power-up P2 (s) |
| reef_run_m1 | spark | survived | 21.5 | 0 | 0.0 | 0 | None | 100/0/0/0 | – | 1.86 | 0 | Time to first power-up P2 (s) |
