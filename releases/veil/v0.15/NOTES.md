# VEIL v0.15 release notes

- The glass floor is lighter for the phone to draw, with the same picture: its main effect needs about a third of the work on the graphics chip of phones like the Galaxy A54 (381 down to 116 steps, counted the way Arm, the chip maker, counts it), and its reflection no longer draws things that are too far away or under the glass to show in it.
- Home and the screens before a flight are smooth again: the 13 effects that only the flight uses load before Home appears, as in 0.14, instead of while Home is on screen (that made Home feel heavy). The first open takes about as long as in 0.14; the open time on phones is measured after this version is sent (see below).
- A touch now reaches the game in the same frame instead of waiting for the next one (checked in the game itself; the phone timing follows).
- The Welcome card, the Pause sheet, the Start again card (shown after an account is deleted), the Data and Account pages and the one-time terms card on Home are now light see-through glass over VEIL's sky, like Settings, Home and Results.
- Bigger buttons at every text size: the ranking tabs, the Settings rows, the name field, the pilot choices, the Google sign-in, the Settings button and the buttons on the account and data screens are now at least a comfortable finger tap.
- From the High view the openings between the Storm Sails are easier to see before you reach them.
- In the ranking, the menu that opens when you tap another pilot's row now sits below the top card and no longer touches it on short phones.
- Pearls: 38.19 percent of pearls sit on the safe line (118 of 309), the same as in 0.14; this work is closed at that share.
- There are no ads in this test version, and nothing to buy. This week's ad timing and store page fixes are only in the store copy.

Not finished yet (10):
- Smooth play and the first open on phones: this version's changes are not measured on phones yet. The last phone numbers (an earlier copy of 0.14): slowest frames on a Galaxy A54 63.4 ms (aim: 50 ms), first open 43.9 seconds; a high-end Google phone 33.3 ms (aim: 25 ms) and 29.7 seconds (aim: 10 seconds).
- Touch delay on phones: the faster touch above is not measured on a phone yet (last Galaxy A54 run: 166 ms from touch to screen, aim: 40 ms).
- A full real-phone check of the phone keyboard, cancelling sign-in, offline scores, larger text and WhatsApp sharing runs on this exact copy after it is sent.
- A 15-minute run on real phones (Overdrive and the four places: smoothness and memory) runs on this copy after it is sent; the same 15-minute run passed on a test phone on our computers.
- The music and sound of the whole game, the Overdrive music included, get one more listening pass before the store version.
- TalkBack cannot read the flight buttons on Android yet: the game engine has no screen-reader support there. The camera and Overdrive buttons already carry their names in English and Arabic for when it does.
- App protection for the ranking is not on yet: it needs a store step and a store-version piece. This test copy works without it.
- The ranking's health alert is not set up yet. Nothing in the app changes for it.
- From the High view, when a moving shutter breaks apart as it should, its pieces can still look like thin slivers; the small cloud islands on the horizon can look like flat discs at phone size, and one pillar edge can show a thin seam.
- iPhone: the iPhone copy comes through TestFlight; we have not yet seen it open on a real iPhone ourselves. Tell us if it opens and plays.