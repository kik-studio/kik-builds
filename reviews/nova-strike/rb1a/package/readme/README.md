# Nova Strike · Review Build 1a (browser audio fix — draft)

**Build ID `0.1.0+473bb47`** · source commit `473bb47` · package prepared by the Builder.

Review Build 1 (baseline, `0c2fc79`) plus **one game change: sound now works in browsers.** Everything else plays and looks the same as Review Build 1. That package has the full set of screenshots, recordings, demos, logs, balance and performance data.

## What changed
| File | Change | Why |
|---|---|---|
| `core/audio.gd` | The Music and SFX sound channels are created by growing the channel count instead of `AudioServer.add_bus()` | In Godot 4.7.2's browser audio, `add_bus()` put the new channel in front of Master and looped Master into it, so browsers played nothing |
| `tests/test_runner.gd` | 3 new checks: Master stays channel 0; Music and SFX feed Master; the code never calls `add_bus()` | So it can't come back |
| `tests/review/*` | Review recording, demo, screenshot and log scripts (never loaded by the game) | Review packages |

In `games/nova-strike/`, nothing else differs from `0c2fc79` apart from `review/` and `docs/` notes.

## Sound in the browser: measured
- Before (Review Build 1, `0c2fc79`): **silent**. Music starts but nothing reaches the speakers (output level 0).
- After: **sound reaches the speakers**. On build `54cba84` (same game code) menu music averaged about −21 dBFS at the output and an interface click added a second sound. The result was the same on this build (`473bb47`) once it was published.
- Details and method: `tests/AUDIO_BROWSER.md`. Measured in Chromium (the desktop app's browser pane), not on a phone.

## Still true (unchanged from Review Build 1)
- Mid-range Android is below 60 fps; the Pixel 10 Pro XL meets it (Test Lab).
- Combat is less dense and spectacular than the design target, and the aircraft are smaller.
- The combat sound mix may clip (peaks at full scale).
- There are no real ads or purchases.

## Pending
- **iPhone 16 Plus (Safari):** not tested. On iPhone, the ring/silent switch mutes browser sound, so test with the switch on ring.
- The owner's phone check (Pixel APK + iPhone browser).

> Uploads, checksums, archive checks and bot runs don't prove visual quality, fun or owner acceptance.
