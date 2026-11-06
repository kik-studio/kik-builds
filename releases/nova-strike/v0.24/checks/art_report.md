# Art-direction check · build 0.24+be8290f

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Gameplay | 21.8 / 26.5 | 12.9 / 21.2 | 14.6 / 12.0 | 0.5 / 0.48 | 0.01 / 0.03 | flatter | [art_01.jpg](art_01.jpg) |
| 2 | Title | 27.9 / 21.1 | 23.1 / 24.5 | 11.3 / 7.1 | 0.49 / 0.67 | 0.03 / 0.05 | – | [art_02.jpg](art_02.jpg) |
| 3 | Campaign map | 24.6 / 22.3 | 21.3 / 26.0 | 20.7 / 10.2 | 0.55 / 0.67 | 0.02 / 0.05 | more saturated, missing highlights/glow | [art_03.jpg](art_03.jpg) |
| 4 | Briefing | 10.5 / 16.6 | 20.0 / 20.8 | 7.0 / 8.6 | 0.89 / 0.76 | 0.01 / 0.03 | – | [art_04.jpg](art_04.jpg) |
| 5 | Results (victory) | 16.6 / 22.0 | 20.7 / 24.4 | 8.8 / 9.3 | 0.76 / 0.66 | 0.02 / 0.05 | missing highlights/glow | [art_05.jpg](art_05.jpg) |
| 6 | Store | 16.3 / 15.0 | 20.1 / 20.2 | 5.8 / 6.8 | 0.76 / 0.79 | 0.03 / 0.03 | – | [art_06.jpg](art_06.jpg) |
| 7 | Hangar | 19.7 / 25.6 | 23.9 / 22.2 | 7.2 / 8.5 | 0.64 / 0.52 | 0.04 / 0.03 | – | [art_07.jpg](art_07.jpg) |
| 8 | Results (defeat) | 12.8 / 14.8 | 19.8 / 18.9 | 6.8 / 7.2 | 0.84 / 0.75 | 0.02 / 0.02 | – | [art_08.jpg](art_08.jpg) |
| 9 | Settings | 7.5 / 8.9 | 15.8 / 12.5 | 4.8 / 7.9 | 0.89 / 0.93 | 0.01 / 0.01 | – | [art_09.jpg](art_09.jpg) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Gameplay | #0e1c2f #1b3754 #1e2534 #35485c #303a48 #5b6a72 | #131215 #504135 #765e4a #262220 #37291f #b9a080 |
| Title | #11131b #45444c #2a2a33 #201f24 #736a66 #d5b581 | #2e2d2d #05070c #0b1017 #18181b #605c56 #bbb3a4 |
| Campaign map | #1c0e0e #573025 #421d17 #2f1714 #865038 #cc9f64 | #030d16 #202e39 #0b161e #616d71 #03121e #c7bea7 |
| Briefing | #08090f #06080e #090c13 #110d12 #1d1518 #93764e | #040b12 #1b2128 #081119 #3d3f44 #111317 #9c927c |
| Results (victory) | #222128 #060710 #12121c #0b0e19 #48433e #a69169 | #2a2e31 #050e16 #0c141b #171718 #5e5e5d #c3b496 |
| Store | #07080f #181d26 #111216 #3f3b37 #2b2725 #968976 | #171d22 #050f17 #0b1117 #030b12 #373839 #908e89 |
| Hangar | #030409 #312e2d #08090d #60584e #121113 #b8a47e | #0e0f10 #473f38 #2b2723 #706254 #1b1e20 #b8a48a |
| Results (defeat) | #090c13 #11151d #07090f #05060b #2a3138 #9a8766 | #04090e #0a0e13 #0c171f #3a3d3f #1c2128 #81827e |
| Settings | #020306 #05070d #101621 #010103 #57585a #010205 | #08161e #0a1822 #030b13 #06111a #031018 #313f49 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Target: every role pair ≥ 25.0.

| Roles | Closest pair ΔE | Result |
|---|---|---|
| enemy vs background | 6 | ⚠️ too close |
| enemy_bullets vs background | 50 | ✅ |
| enemy_bullets vs player_bullets | 27 | ✅ |
| enemy_bullets vs enemy | 36 | ✅ |
| player_bullets vs background | 42 | ✅ |
