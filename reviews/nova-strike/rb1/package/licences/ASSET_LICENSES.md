# Asset licence log

Every image, sound, music track and font in this game is listed here with its source and proof that we may use it commercially.

| Asset (path) | Type | Source / tool | Licence / terms | Human edits | Date |
|---|---|---|---|---|---|
| assets/fonts/BalooBhaijaan2.ttf | Font | Google Fonts | SIL OFL 1.1 (OFL-BalooBhaijaan2.txt) | — | 2026-09-24 |
| assets/fonts/Tajawal-*.ttf | Font | Google Fonts | SIL OFL 1.1 (OFL-Tajawal.txt) | — | 2026-09-24 |
| assets/brand/logo.png | Logo | Recraft V4 (paid API) | Output owned by KiK Studio (Recraft terms) | Cleaned and recoloured by Claude | 2026-09-24 |
| assets/audio/coin.ogg | SFX | ElevenLabs SFX v2 (Creator plan) | Commercial use allowed on paid plan | Converted to ogg | 2026-09-24 |
| assets/audio/menu_music.ogg | Music | Stable Audio 3.0 (Stability API) | Output owned by us; Community licence under $1M/yr revenue | Converted to ogg | 2026-09-24 |

## Concept art (not in the game)

| Asset | Source / tool | Licence / proof | Used in game? |
|---|---|---|---|
| art/concepts/striker_concept_v1.png | Nano Banana Pro (gemini-3-pro-image) via Gemini API, studio prompt, 2026-09-24 | Google Gemini API terms: generated output owned by user, commercial use allowed | No, concept only (direction check) |
| art/concepts/striker_concept_v2.png | Nano Banana Pro (gemini-3-pro-image) via Gemini API, studio prompt (no old art used as input), 2026-09-24 | Google Gemini API terms: output owned by user, commercial use allowed | No, concept only |
| art/concepts/guardian_concept_v1.png | Nano Banana Pro via Gemini API, studio prompt + our Striker v2 as style reference, 2026-09-24 | Gemini API terms: output owned by user, commercial use allowed | No, concept only |
| art/concepts/arcanist_concept_v1.png | Nano Banana Pro via Gemini API, 2026-09-24 | same | No, dropped (too close to Striker) |
| art/concepts/arcanist_concept_v2.png | Nano Banana Pro via Gemini API, studio prompt, 2026-09-24 | same | No, concept only |
| art/concepts/striker_evolution_v1.png | Nano Banana Pro via Gemini API, our Striker v2 as reference, 2026-09-24 | Gemini API terms | No, concept only |
| art/concepts/striker_concept_v3.png, guardian_concept_v2.png, arcanist_concept_v3/v4/v5.png | Nano Banana Pro via Gemini API, studio prompts (our own concepts as reference), 2026-09-24 | Gemini API terms | No, concept only (v4 dropped: copied Striker shape) |

## Audio in the prototype
| assets/audio/sfx/*.wav | Placeholder SFX synthesised by Claude in Python (numpy), 2026-09-24 | Original, owned by KiK Studio | Yes (prototype only; replaced by designed SFX in stage 4) |
| assets/fonts/DejaVuSans-Symbols.ttf | Font subset (✓ ● ○ ★ ☆ symbols only) of DejaVu Sans, 2026-09-24 | DejaVu / Bitstream Vera licence: free for commercial use and modification | Yes |

## EXP-001 Striker assets (experiment builds only until the route is chosen)

<a id="striker-canon"></a>**Canon v1.1 views** (`art/canon/striker/`): Nano Banana Pro via Gemini API from studio prompts, 2026-09-24. Gemini API terms: output owned by us, commercial use allowed. Sheet assembled by `pipeline/make_canon_sheet.py`.

<a id="striker-route-b"></a>**Route B (3D)** `assets/units/striker_b/`:
| Asset | Source / tool | Licence / terms | Human edits |
|---|---|---|---|
| unit_striker.glb | Rodin Gen-2.5 High (Hyper3D) via Scenario Pro API, job in `pipeline/jobs_v11.json`, raw file vaulted as `striker_v11_rodin25_high.glb` | Scenario Pro terms: generated outputs owned by the customer, commercial use (re-confirm at release) | None by hand: scripted rig `pipeline/rig_striker.py` |
| unit_lancepod.glb | Rodin Gen-2.5 High via Scenario Pro from our Gemini pod render (`art/production/striker/design/pod_q34.png`), job in `pipeline/jobs_pod.json` | same | Scripted: `pipeline/rig_lancepod.py` |
| Comparison-only models (not in game): Meshy 7.1, Tripo P1, Hunyuan 3D 3.1 Pro | Meshy Pro / Scenario Pro, vaulted as `striker_v11_*.glb` | Hunyuan terms have regional limits: never shipped | — |

<a id="striker-route-a"></a>**Route A (2D)** `assets/units/striker_a/`: Scenario Seedream 5.0 Pro Layerize on the canon v1.1 top views, jobs in `pipeline/jobs_2d.json`, raw layers vaulted as `striker_v11_layers_2d.zip`. Scenario Pro terms (as above). Scripted processing only (`register_layers.py`, `build_route_a.py`).

**Background** `assets/backgrounds/lantern_road_far.jpg`: our Gemini far plate (`art/production/lantern_road/far_plate_v1.png`), resized. Test layer for EXP-001 only.

## Release build assets (overnight 2026-09-24/25) — full provenance in the JSON logs
| Family | Paths | Source / tool | Licence / terms | Log |
|---|---|---|---|---|
| Enemies (13), bosses (6 + parts), stage plates + props (6 kits), pilot portraits (3), screen backdrops, pickups | `assets/enemies/`, `assets/bosses/`, `assets/env/`, `assets/pilots/`, `assets/ui/`, `assets/pickups/` | Nano Banana Pro (Gemini API), studio prompts with VDB pages as style references; background removal by `tools/art/remove_bg.py` | Gemini API terms: output owned by us, commercial use | `art/sources_2d.json` |
| Guardian, Arcanist hulls + hardware parts; Striker seeker pod | `assets/units/guardian/`, `assets/units/arcanist/`, `assets/units/striker_b/hw_*` | Gemini canon views → Rodin Gen-2.5 High via Scenario Pro; scripted rigs (`pipeline/rig_*.py`); raw GLBs in the asset vault | Scenario Pro terms (re-confirm at release) | `art/sources_3d.json`, `pipeline/jobs_units.json` |
| Sound effects (44), music loops (11) | `assets/audio/sfx/`, `assets/audio/music/` | ElevenLabs SFX v2 (paid plan); Stable Audio 3.0 | commercial use on our plans | `art/sources_audio.json` |
| Fonts: Cinzel, Rajdhani (+ Tajawal) | `assets/fonts/` | Google Fonts | SIL OFL 1.1 (licence files included) | `art/sources_ui.json` |
