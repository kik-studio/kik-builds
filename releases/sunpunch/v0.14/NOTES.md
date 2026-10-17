# SUNPUNCH v0.14: what changed (engineering notes)

Plan: `PLAN.md` (binding approval line + Khaled's later decisions). Lanes and evidence: `HANDOFF*.md`, `rr/`. Decisions: `docs/DECISIONS.md` D-v14-*.

- **Progress + economy:** 20 named aircraft (`config/frames.json`, migration `core/frames_migrate.gd`), ECONOMY rev 7 (rising coin curve, Noonfire = 1,000,000), Normal/Legendary per level, continue with coins, failed-run coins, coin Store in test mode (`core/iap/*`), SunPunch upgrades on the launch sheet only (POWER tab removed, owner 2026-10-10).
- **Home:** real 3D for all 20 aircraft (`core/home_hero_3d.gd`, `assets/models/v14/`), per-ship move pool, carousel, flight-level track, upgrade transformation, coin+settings pair, preview sandbox; PowerVR/Vulkan crash guard (`pixel3d_guard`).
- **Sector 2 (L11-L20):** Wreck Field runtime (`core/flight/s2.gd`), Rust Dusk sky, 4 enemies + obstacles, Coil boss rounds 4-5 (`core/flight/coil*.gd`), UNLOCK reveal; squeeze root fix + guard (`tests/test_v14_squeeze.gd`).
- **Sector 1:** one look per sector (lane F3), obstacles with depth, intro cards, honest razor telegraph, health rings, wing hitboxes, laser pulse, alerts, choreographed formations (lane F2), Big Bite raids REMOVED (owner 2026-10-10).
- **Menus:** campaign map (Arabic layout root fix), launch sheet, Store remake, Level Clear r4-r5, the Vault on the map (rise, timed tap-crack, entry card), iPad (`ios_ipad`).
- **Audio:** 45 v14 cues registered and called (lane F2).
- **In flight:** 2D art for all 20 aircraft (lane F4; 3D in flight closed by the owner).
- **Analytics/crash:** Crashlytics crumbs at Home flip, 3D load, buy, upgrade reveal, level start; progression ids reef_L/wreck_L + frame.
- **Tools/polish:** `fake_insets` in `core/ui.gd`, `layout_check` block in `config/game.json` (rules 3.39).
- **Test modes (named per the 10-10 outside review):** `campaign_run` flow runs use no-death, 8x time and revives = FLOW proof only; difficulty, fun and phone timing come from normal-play bot runs (`economy_sim`, level bots) and the phone guard. Each evidence in the release report names its mode.

Honest note on the art:
- 3D aircraft families 2-5 on Home (blind 2.5-3.5; family 1 owner 4.5), below the 4.5 bar, shipped disclosed... (below the art bar, carried)
- In-flight art of the 20 aircraft (blind 3.0), below the 4.5 bar, shipped disclosed (rules 3.38, owner... (below the art bar, carried)
- Home look (blind 2.5; owner 4.5 on round 4), below the 4.5 bar, shipped disclosed (rules 3.38, owner... (below the art bar, carried)
- Map, launch sheet and Store (blind 3.5-4.0), below the 4.5 bar, shipped disclosed (rules 3.38, owner... (below the art bar, carried)
- Level Clear round 5 (blind 3.2-3.8), below the 4.5 bar, shipped disclosed (rules 3.38, owner... (below the art bar, carried)
- The Vault on the map and its card (blind 2.6-3.4), below the 4.5 bar, shipped disclosed (rules 3.38, owner... (below the art bar, carried)
- Sector 1 one look and the L10 Maw arena (blind 2.5-3.0), below the 4.5 bar, shipped disclosed (rules 3.38,... (below the art bar, carried)
- Sector 2 Rust Dusk look and enemies (blind 3.0-3.5), below the 4.5 bar, shipped disclosed (rules 3.38,... (below the art bar, carried)
- Boss Coil round 5 (blind 3.0), below the 4.5 bar, shipped disclosed (rules 3.38, owner FN-v14-finish-all) (below the art bar, carried)
- Obstacles with depth L1-L10 (blind 2.5-3.5), below the 4.5 bar, shipped disclosed (rules 3.38, owner... (below the art bar, carried)
- Bosses 3-4 concept art (blind 2.5-3.6), below the 4.5 bar, shipped disclosed (rules 3.38, owner... (below the art bar, carried)
- 26 finished look item(s) without a passing look check yet
- 963 art files still use the earlier look without a passing look check
- parts of the look are still below our own 4.5 bar; it keeps improving in the next versions