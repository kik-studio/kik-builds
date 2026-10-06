# Game-feel report · build 0.4+3f033b1

Automated: measured from 1 bot run(s) (event logs). Targets: config/build_checks.json feel.targets (+ studio defaults). It shows pacing and systems working; it does **not** show that a person finds it fun.

## Summary (runs passing each target)

| Target | Threshold | Passing runs | Median |
|---|---|---|---|
| Empty screen time (share of play) | ≤ 1.0 | 1/1 ✅ | 0.11 |
| Longest empty gap (s) | ≤ 999 | 1/1 ✅ | 9.0 |
| Empty gaps over 2 s | ≤ 999 | 1/1 ✅ | 1 |
| Time to first power-up P2 (s) | ≤ 999 | 0/1 ⚠️ | – |
| Time at top power level (share) | ≥ 0.0 | 1/1 ✅ | 0.0 |
| Pickups collected (share) | ≥ 0.6 | 1/1 ✅ | – |
| Bot deaths | ≤ 0 | 1/1 ✅ | 0 |
| Mean enemies on screen | ≥ 0.0 | 1/1 ✅ | 1.89 |

## Per run

| Run | Unit | Result | Play s | Empty % | Longest gap | Gaps>2s | → P2 s | Time at P1/P2/P3/P4 % | Pickups | Mean enemies | Supers | Fails |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| W01-L03 | saddah | unknown | 81.0 | 11 | 9.0 | 1 | None | 0/0/0/0 | – | 1.89 | 0 | Time to first power-up P2 (s) |
