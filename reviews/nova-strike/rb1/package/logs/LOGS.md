# Event logs · Review Build 1 (`0.1.0+0c2fc79`)

**What:** every campaign mission (48) and one Endless run, flown by the built-in bot pilot (**not invulnerable**), with an observer reading the live combat scene: waves, enemy-free periods, pickups, weapon level L1–L4, Bomb and Super uses, hull, result. Made by `tests/review/event_log.gd` on an exact export of `0c2fc79` (Godot 4.7.2, headless, fixed 30 fps simulation). Builder-reported, 2026-09-25.

**Files:** `<mission>.jsonl` (one event per line: `wave`, `enemy_free`, `pickup_spawned/collected/lost`, `level`, `super`, `bomb`, `boss_spawned`, `died`, and a `sample` every second with enemies, hostile bullets, hull, Super charge, score) · `summary.json` · `SUMMARY.md` (one row per mission).

**Setup:** units rotate Striker / Guardian / Arcanist; hardware per stage Mk I, II, II, III, III, IV (bought through the real purchase path). One run per mission; numbers vary a little between runs (random drops and spawns). Endless was capped at 180 s and then ended from the Pause menu ("timeout" in the table).

## What the logs show (measured, this run)
- **Pacing:** all 48 missions were won by the bot. The 42 standard missions each ran all **10 waves in 89–97 s** (median 91 s). Boss missions ran 92–178 s. They show 4 rail marks because the rail marks boss phases, not waves.
- **Enemy-free time:** a stretch with no enemy and no hostile bullet on screen for 1 s or more. Median 16 s per standard mission; the longest single gap was 10.3 s.
  - The highest totals were 1.01 (51 s), 2.01, 1.02, 2.06, 4.01 and 6.02 (30 s or more).
  - This matches the visual review finding that early missions are sparse.
- **Power pickups:** the bot collected at least 2 in every mission (median 5 of about 7–8 spawned). Uncollected pickups drifted off screen.
- **Weapon levels:** L4 was reached in 46 of 48 missions, at a median of 41 s into the mission.
- **Super:** used about 2 times per mission (median).
- **Bomb:** used 0 times. The bot pilot doesn't use Bombs, so Bomb behaviour is covered by combat_tests, not these logs.
- **Damage:** the bot never dropped below 78 hull. It plays more safely than a person would, so these logs say nothing about difficulty for people.

These are bot measurements of pacing and systems. They don't show how the game feels to play.
