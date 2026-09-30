# Performance · Review Build 1 (`0.1.0+0c2fc79`)

## Measured on real phones (Firebase Test Lab, 2026-09-25 ~09:06–09:10 UTC)
Automated benchmark: the Android Benchmark APK plays boss mission 1.08 (Guardian vs ALGOL) with the bot for 75 s and uploads its frame times. Read with `tools/qa/perf_report.py nova-strike`. Test Lab matrix `matrix-1kvodiup687ed`.

**Build measured: `0.1.0+38f0663`.** Inside `games/nova-strike/` it differs from `0c2fc79` only in `review/HANDOFF.md`, so the game code is identical to this review build.

| Phone | Class | Avg fps | p95 frame | p99 frame | Stalls | vs 60 fps target |
|---|---|---|---|---|---|---|
| Pixel 10 Pro XL (Android 16) | flagship (the studio's phone model) | 59.8 | 16.7 ms | 16.7 ms | 2 | meets |
| moto g 2025 (Android 15) | mid-range | 45.9 | 25.0 ms | 27.7 ms | 3 | below |
| Galaxy A16 5G (Android 15) | mid-range | 25.6 | 46.7 ms | 55.6 ms | 41 | well below |
| Galaxy A05s (Android 15) | low/mid-range | 26.7 | 48.1 ms | 88.9 ms | 71 | well below |

Earlier measurement for comparison: Galaxy A16 on build c9fb713 (before the phone performance mode): 23.4 fps, p95 56.8 ms, p99 75.0 ms. The performance mode helped a little (p95 56.8 → 46.7 ms) but mid-range phones are still far from 60 fps.

## Not measured / pending
- **iPhone 16 Plus (browser):** pending the owner's phone check. Browsers were silent in this build (fixed in Review Build 1a); frame rate in Safari not measured.
- **Pixel 10 Pro XL by hand (APK), heat over a long session:** pending the owner's phone check.
- Long-session (sustained, 10+ minutes) behaviour: not measured on any phone.

## Not device measurements
The `linux GenericDevice` rows in `perf_report` come from the studio's Linux machines with software rendering (tests, video and review recordings). They are not phone performance and are not used here.

## Next fix (Builder's plan, not done)
Draw the bullets and enemies in batches (MultiMesh), lower the 3D layer's resolution further on mid-range phones, and re-measure on the same four phones.
