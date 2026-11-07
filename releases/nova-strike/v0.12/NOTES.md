# Nova Strike v0.12: what changed (short)
After-send fix of v0.11 (0.11+8c4b99a), ONE build, ship on build.
- F1b / FN-53 part 2: core/hd_pack.gd follows 301/302/303/307/308 redirects (absolute or host-relative Location, Range kept, max 5 hops) on the native HTTPClient transport; the hosted pack URL always redirects to files.karibros.studio since NO POSTPAY, so every phone failed 'server: HTTP 302' in v0.10/v0.11. Test: hd_pack_tests _test_client_redirect_loopback (real loopback HTTP server), PASS 129/0 (job 1015014303-8f60).
- X-blend: [filesystem] import/blender/enabled=false.

Honest note on the art:
- 4907 art files still use the earlier look without a passing look check
- the game's look settings are not locked yet
- parts of the look are still below our own 4.5 bar; it keeps improving in the next versions