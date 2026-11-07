# Art-direction check · build 0.25+86c374e

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Gameplay | 21.8 / 26.5 | 12.9 / 21.2 | 14.6 / 12.0 | 0.5 / 0.48 | 0.01 / 0.03 | flatter | [art_01.png](art_01.png) |
| 2 | Title | 29.0 / 21.1 | 23.0 / 24.5 | 11.2 / 7.1 | 0.47 / 0.67 | 0.03 / 0.05 | – | [art_02.png](art_02.png) |
| 3 | Campaign map | 24.6 / 22.3 | 21.3 / 26.0 | 20.7 / 10.2 | 0.56 / 0.67 | 0.02 / 0.05 | more saturated, missing highlights/glow | [art_03.png](art_03.png) |
| 4 | Briefing | 10.7 / 16.6 | 20.1 / 20.8 | 7.0 / 8.6 | 0.88 / 0.76 | 0.01 / 0.03 | – | [art_04.png](art_04.png) |
| 5 | Results (victory) | 16.5 / 22.0 | 20.7 / 24.4 | 8.8 / 9.3 | 0.76 / 0.66 | 0.02 / 0.05 | missing highlights/glow | [art_05.png](art_05.png) |
| 6 | Store | 16.3 / 15.0 | 20.1 / 20.2 | 5.8 / 6.8 | 0.76 / 0.79 | 0.03 / 0.03 | – | [art_06.png](art_06.png) |
| 7 | Hangar | 19.7 / 25.6 | 24.7 / 22.2 | 7.4 / 8.5 | 0.66 / 0.52 | 0.04 / 0.03 | – | [art_07.png](art_07.png) |
| 8 | Results (defeat) | 12.7 / 14.8 | 19.9 / 18.9 | 6.9 / 7.2 | 0.84 / 0.75 | 0.02 / 0.02 | – | [art_08.png](art_08.png) |
| 9 | Settings | 7.2 / 8.9 | 15.5 / 12.5 | 4.8 / 7.9 | 0.9 / 0.93 | 0.01 / 0.01 | – | [art_09.png](art_09.png) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Gameplay | #0e1c2f #1b3754 #1e2535 #35485c #303a48 #5b6a72 | #131215 #504135 #765e4a #262220 #37291f #b9a080 |
| Title | #12151c #48464e #2c2d35 #222125 #766c69 #d6b582 | #2e2d2d #05070c #0b1017 #18181b #605c56 #bbb3a4 |
| Campaign map | #1c0e0e #371915 #452a22 #844e37 #643426 #cb9d63 | #030d16 #202e39 #0b161e #616d71 #03121e #c7bea7 |
| Briefing | #07090f #0f0e13 #0a0a0f #20181a #05080e #9a7d52 | #040b12 #1b2128 #081119 #3d3f44 #111317 #9c927c |
| Results (victory) | #0f101a #060710 #28252a #191a24 #44403e #a58f67 | #2a2e31 #050e16 #0c141b #171718 #5e5e5d #c3b496 |
| Store | #06080e #181d26 #403c37 #111216 #2b2726 #978977 | #171d22 #050f17 #0b1117 #030b12 #373839 #908e89 |
| Hangar | #302c2b #030409 #07080b #0f0e11 #635a50 #c2ac82 | #0e0f10 #473f38 #2b2723 #706254 #1b1e20 #b8a48a |
| Results (defeat) | #0f131b #080b11 #04060a #252c34 #06080e #948364 | #04090e #0a0e13 #0c171f #3a3d3f #1c2128 #81827e |
| Settings | #020308 #05070d #0f1420 #020204 #010103 #535557 | #08161e #0a1822 #030b13 #06111a #031018 #313f49 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Target: every role pair ≥ 25.0.

| Roles | Closest pair ΔE | Result |
|---|---|---|
| enemy vs background | 6 | ⚠️ too close |
| enemy_bullets vs background | 50 | ✅ |
| enemy_bullets vs player_bullets | 27 | ✅ |
| enemy_bullets vs enemy | 36 | ✅ |
| player_bullets vs background | 42 | ✅ |
