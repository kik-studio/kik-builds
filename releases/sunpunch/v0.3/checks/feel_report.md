# Game-feel report · build 0.3+7976c70

Automated: measured from 4 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.15 | 4/4 ✅ | 0.0 |
| Longest empty gap (s) | ≤ 3.0 | 4/4 ✅ | 0.0 |
| Empty gaps over 2 s | ≤ 1 | 4/4 ✅ | 0.0 |
| Time to first power-up P2 (s) | ≤ 40 | 4/4 ✅ | 14.8 |
| Time at top power level (share) | ≥ 0.0 | 4/4 ✅ | 0.2 |
| Pickups collected (share) | ≥ 0.7 | 3/4 ⚠️ | 0.88 |
| Bot deaths | ≤ 1 | 4/4 ✅ | 0.0 |
| Mean enemies on screen | ≥ 1.0 | 4/4 ✅ | 1.98 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| reef_run_m2 | spark | survived | 71.0 | 0 | 0.0 | 0 | 14.8 | 21/24/22/34 | 88% | 2.06 | 1 | – |
| reef_run_m2 | spark | survived | 71.0 | 0 | 0.0 | 0 | 14.8 | 21/24/22/34 | 88% | 2.06 | 1 | – |
| reef_run_m2 | spark | defeat | 52.0 | 2 | 1.0 | 0 | 15.7 | 30/34/30/6 | 92% | 1.9 | 1 | – |
| reef_run_m2 | spark | survived | 15.2 | 0 | 0.0 | 0 | 13.6 | 90/10/0/0 | 67% | 1.75 | 0 | Pickups collected (share) |
