# Game-feel report · build 0.23+9012acf

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Unknown | Median |
|---|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0 | 0.01 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 0 | 1.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 0 | 11.7 |
| Time at top power level (share) | ≥ 0.2 | 2/3 ⚠️ | 0 | 0.21 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 0 | 0.96 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 0 | 3.21 |

**Unknown checks: 0** (none)

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 85.0 | 1 | 1.0 | 0 | 11.7 | 14/24/37/25 | 95% | 3.6 | 4 | – |
| 1.05 | striker | victory | 86.6 | 1 | 1.1 | 0 | 10.4 | 12/40/26/21 | 98% | 3.21 | 3 | – |
| 2.01 | striker | victory | 83.4 | 0 | 0.0 | 0 | 13.0 | 16/26/40/18 | 96% | 2.58 | 3 | Time at top power level (share) |
