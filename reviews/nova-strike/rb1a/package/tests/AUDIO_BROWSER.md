# Browser audio test · Review Build 1a

**Result: PASS (measured in Chromium). Sound reaches the speakers.**

## Method (Builder, 2026-09-25)
Same method as Review Build 1:
- The published web build was loaded with an observer script placed in front of the engine.
- The script wrapped `AudioContext`, put an analyser just before the speakers, recorded every audio-node connection and counted the sound buffers started.
- It ran in Chromium, in the desktop app's browser pane.

## Results
| Build | AudioContext | Buffers started | Output level (RMS, 3 s after load) | Routing |
|---|---|---|---|---|
| `0c2fc79` (Review Build 1) | running | 1 (menu music) | **0.000** (silent) | Master cut from the speakers and looped into Music/SFX |
| `54cba84` (the fix; same game code as Review Build 1a) | running | 1 (menu music) | mean **0.090**, max 0.168 (about −21 dBFS) | Master → speakers; Music → Master; SFX → Master; music sample → Music |
| `54cba84`, after tapping NEW GAME | running | 2 (+ interface sound) | max 0.204 | same |
| `473bb47` (this build, re-checked after it was published) | running | 1 (menu music) | mean **0.091**, max 0.155 | Master → speakers (never cut); Music/SFX → Master |

## Limits
- This was measured in Chromium, not Safari. iPhone Safari is **pending**; on iPhone the ring/silent switch mutes browser sound.
- It measures that sound reaches the output, not that the mix sounds right.
