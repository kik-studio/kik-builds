# Nova Strike v0.19 notes

## LOD (lane lod19)
- One door: `Boss3DLoader.instance()` (and `apply_lod()` for raid2's dragon, which instances its own scene) sets the rig's `use_lod1`
  before the rig enters the tree (rigs build their pieces in `_ready`), and tags the node `boss_lod` = 0 / 1.
- Rule: the game's existing quality tier (`core/quality.gd`, autoload `Quality`: device classify by GPU / screen / cores ->
  frame-time probe stored per GPU -> remote `quality_tier` / per-model keys -> Settings -> `KIK_QUALITY`) decides.
  `low` and `medium` (`Boss3DLoader.LOD1_TIERS`) draw LOD1 (<= 30k tris, config/boss3d.json `boss_lod1_max`), `high` draws LOD0
  (<= 60k, `boss_on_screen_max`). Chosen once per boss load; a tier step mid-fight keeps the loaded mesh, the next boss follows the new tier.
- Tests force either with `Boss3DLoader.force_lod` (0 / 1; -1 = by tier). A boss with no LOD1 yet is listed in config/boss3d.json
  `lod1_pending` (today: none; thuban's dragon rig got `use_lod1` + the `*_scene_lod1` exports in v0.19 from the Tripo LOD1 pieces in thuban/dragon/lod1/, 24.7k tris).
- Test: tests/v19/boss3d_lod_tests.tscn (in the release runner).