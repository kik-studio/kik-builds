# Game-feel report · build 0.24+be8290f

Automated: measured from 3 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Unknown | Median |
|---|---|---|---|---|
| Empty screen time (share of play) | ≤ 0.1 | 3/3 ✅ | 0 | 0.0 |
| Longest empty gap (s) | ≤ 3.0 | 3/3 ✅ | 0 | 0.0 |
| Empty gaps over 2 s | ≤ 1 | 3/3 ✅ | 0 | 0 |
| Time to first power-up P2 (s) | ≤ 30.0 | 3/3 ✅ | 0 | 17.5 |
| Time at top power level (share) | ≥ 0.2 | 3/3 ✅ | 0 | 0.45 |
| Pickups collected (share) | ≥ 0.7 | 3/3 ✅ | 0 | 0.73 |
| Bot deaths | ≤ 0 | 3/3 ✅ | 0 | 0 |
| Mean enemies on screen | ≥ 2.0 | 3/3 ✅ | 0 | 3.16 |

**Unknown checks: 0** (none)

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.01 | arcanist | victory | 93.1 | 0 | 0.0 | 0 | 14.5 | 16/18/22/45 | 73% | 3.46 | 4 | – |
| 1.05 | striker | victory | 90.1 | 2 | 1.4 | 0 | 19.0 | 21/16/33/30 | 73% | 3.16 | 3 | – |
| 2.01 | striker | victory | 84.2 | 0 | 0.0 | 0 | 17.5 | 21/14/20/45 | 79% | 2.88 | 3 | – |
