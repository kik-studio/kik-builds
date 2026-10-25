# Art-direction check · build 0.20+6c5f495

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Gameplay | 22.1 / 26.5 | 14.2 / 21.2 | 14.2 / 12.0 | 0.5 / 0.48 | 0.01 / 0.03 | flatter | [art_01.png](art_01.png) |
| 2 | Title | 29.7 / 21.1 | 22.0 / 24.5 | 11.3 / 7.1 | 0.43 / 0.67 | 0.04 / 0.05 | – | [art_02.png](art_02.png) |
| 3 | Campaign map | missing capture | | | | | | |
| 4 | Briefing | 15.0 / 16.6 | 23.5 / 20.8 | 7.4 / 8.6 | 0.79 / 0.76 | 0.03 / 0.03 | – | [art_04.png](art_04.png) |
| 5 | Results (victory) | 23.3 / 22.0 | 26.3 / 24.4 | 10.2 / 9.3 | 0.62 / 0.66 | 0.05 / 0.05 | – | [art_05.png](art_05.png) |
| 6 | Store | 19.6 / 15.0 | 22.6 / 20.2 | 6.7 / 6.8 | 0.68 / 0.79 | 0.03 / 0.03 | – | [art_06.png](art_06.png) |
| 7 | Hangar | 12.4 / 25.6 | 21.9 / 22.2 | 6.8 / 8.5 | 0.83 / 0.52 | 0.03 / 0.03 | darker | [art_07.png](art_07.png) |
| 8 | Results (defeat) | 17.8 / 14.8 | 23.7 / 18.9 | 7.2 / 7.2 | 0.74 / 0.75 | 0.03 / 0.02 | – | [art_08.png](art_08.png) |
| 9 | Settings | 13.6 / 8.9 | 22.4 / 12.5 | 6.6 / 7.9 | 0.81 / 0.93 | 0.01 / 0.01 | – | [art_09.png](art_09.png) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Gameplay | #25374d #354656 #0c1b2f #15253a #222836 #667173 | #131215 #504135 #765e4a #262220 #37291f #b9a080 |
| Title | #14171f #4f4c52 #322f34 #7b6e67 #23252f #c4ac86 | #2e2d2d #05070c #0b1017 #18181b #605c56 #bbb3a4 |
| Briefing | #0d0b10 #06080e #080a10 #131318 #b39d76 #52453a | #040b12 #1b2128 #081119 #3d3f44 #111317 #9c927c |
| Results (victory) | #0c0e17 #3e3733 #16151b #06070f #806e54 #ccb785 | #2a2e31 #050e16 #0c141b #171718 #5e5e5d #c3b496 |
| Store | #080a10 #2f2b29 #191719 #5a5047 #0e1016 #b09e85 | #171d22 #050f17 #0b1117 #030b12 #373839 #908e89 |
| Hangar | #0e1117 #010308 #080a0e #04060b #ab9466 #2a2d2f | #0e0f10 #473f38 #2b2723 #706254 #1b1e20 #b8a48a |
| Results (defeat) | #0c0f17 #06070c #1c2027 #5c5753 #afa38a #090c14 | #04090e #0a0e13 #0c171f #3a3d3f #1c2128 #81827e |
| Settings | #070a12 #030408 #080b14 #0f1118 #a28e6c #38383b | #08161e #0a1822 #030b13 #06111a #031018 #313f49 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Target: every role pair ≥ 25.0.

| Roles | Closest pair ΔE | Result |
|---|---|---|
| enemy vs background | 6 | ⚠️ too close |
| enemy_bullets vs background | 50 | ✅ |
| enemy_bullets vs player_bullets | 27 | ✅ |
| enemy_bullets vs enemy | 36 | ✅ |
| player_bullets vs background | 42 | ✅ |
