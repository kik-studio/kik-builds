# SUNPUNCH v0.20: what changed
- Every aircraft (all 20) flies as its real 3-D model in the levels, at every flight level and in the SunPunch super (one model per aircraft: levels 1-2 show its full hull; one switch: config/v14.json e_flight3d, ON; OFF = the 2-D aircraft exactly as before).
- The aircraft rolls into the steer (right -> rolls right, the left wing lifts), scaled by sideways speed, eased in and out, settles level; slight pitch on forward / back; a lagging touch of yaw; a slow idle breath.
- The stones set into each aircraft are alive (one shader on the model's own painted stones): idle shimmer, sparkle with the roll, pulse with each volley, flicker when hit. No new lights or parts.
- The hit area is unchanged (only the cockpit core collides); the 3-D hull and side units are fitted every frame INSIDE the boxes the 2-D paintings cover (incl. the v0.17 x1.2), so a model can draw a little smaller than its painting, never bigger.
- Crash guard: the Pixel / PowerVR phone-guard scenario now also flies 6 aircraft in 3-D (fly3d step).

Honest note on the art:
- 3-D aircraft in flight below the 4.5 bar (blind J4: look 3-D 3 vs painted 2-D 3.5; feel 3-D 3.5 vs 2-D 2;... (below the art bar, carried)
- 989 art files still use the earlier look without a passing look check
- parts of the look are still below our own 4.5 bar; it keeps improving in the next versions