# Browser audio test · Review Build 1 (`0.1.0+0c2fc79` web build)

**Result: FAIL (measured): the browser build is silent.**

## How it was measured (Builder, 2026-09-25, Chromium in the desktop app's browser pane)
The published web build was loaded in an iframe with a small observer script added in front of the engine. The script:
- wrapped `AudioContext` and put an analyser just before the speakers;
- recorded every audio-node connection;
- counted the sound buffers started.

## What it showed
- The AudioContext was **running** (not blocked by autoplay rules).
- The menu music buffer **started** (a 64 s buffer).
- The output level at the speakers was **0** (RMS 0.000 over 3 s, sampled every 100 ms).
- The connections explain why:
  - after the game added its Music bus, the browser's Master bus output was **disconnected from the speakers** and connected into the Music bus;
  - after the SFX bus was added, Master fed into SFX and SFX into Music;
  - so nothing reached the speakers.

## Cause
In Godot 4.7.2's browser audio ("sample" playback), `AudioServer.add_bus()` calls the browser side with position −1. The browser side treats −1 as a real index and files the new bus **in front of** Master. From then on the engine and the browser disagree on which bus is which. `core/audio.gd` created its Music and SFX buses this way at start-up.

## Fix (not in this build)
Grow `AudioServer.bus_count` instead of calling `add_bus()`. The browser side then appends buses in the same order as the engine. The fix is in Review Build 1a, with a regression check in `tests/test_runner.gd`, and was ported to the starter kit by the Brain (FR-3).

Native builds (Android APK, the recordings) are not affected: they mix audio inside the engine.
