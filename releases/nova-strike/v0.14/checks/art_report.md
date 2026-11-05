# Art-direction check · build 0.13+a195cb4

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Gameplay | 31.0 / 26.5 | 17.7 / 21.2 | 17.1 / 12.0 | 0.25 / 0.48 | 0.03 / 0.03 | – | [art_01.jpg](art_01.jpg) |
| 2 | Title | 28.4 / 21.1 | 21.7 / 24.5 | 11.2 / 7.1 | 0.46 / 0.67 | 0.03 / 0.05 | – | [art_02.jpg](art_02.jpg) |
| 3 | Campaign map | missing capture | | | | | | |
| 4 | Briefing | 15.8 / 16.6 | 23.6 / 20.8 | 7.7 / 8.6 | 0.77 / 0.76 | 0.03 / 0.03 | – | [art_04.jpg](art_04.jpg) |
| 5 | Results (victory) | 23.4 / 22.0 | 26.2 / 24.4 | 10.2 / 9.3 | 0.62 / 0.66 | 0.05 / 0.05 | – | [art_05.jpg](art_05.jpg) |
| 6 | Store | 18.8 / 15.0 | 21.9 / 20.2 | 6.5 / 6.8 | 0.7 / 0.79 | 0.03 / 0.03 | – | [art_06.jpg](art_06.jpg) |
| 7 | Hangar | 12.1 / 25.6 | 21.7 / 22.2 | 6.8 / 8.5 | 0.83 / 0.52 | 0.03 / 0.03 | darker | [art_07.jpg](art_07.jpg) |
| 8 | Results (defeat) | 17.7 / 14.8 | 23.5 / 18.9 | 7.3 / 7.2 | 0.74 / 0.75 | 0.03 / 0.02 | – | [art_08.jpg](art_08.jpg) |
| 9 | Settings | 13.6 / 8.9 | 22.4 / 12.5 | 6.6 / 7.9 | 0.81 / 0.93 | 0.01 / 0.01 | – | [art_09.jpg](art_09.jpg) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Gameplay | #162030 #4b6277 #173d66 #344f6b #2f3c50 #909ea2 | #131215 #504135 #765e4a #262220 #37291f #b9a080 |
| Title | #13151d #4b474e #766a65 #2e2b30 #20222b #c0a881 | #2e2d2d #05070c #0b1017 #18181b #605c56 #bbb3a4 |
| Briefing | #06080e #0b0b11 #0e1017 #201a1b #b29c75 #55473d | #040b12 #1b2128 #081119 #3d3f44 #111317 #9c927c |
| Results (victory) | #0c0e17 #3d3733 #17151b #7f6d54 #060810 #cbb684 | #2a2e31 #050e16 #0c141b #171718 #5e5e5d #c3b496 |
| Store | #2d2928 #07090f #171619 #0d0f15 #564d45 #a9987f | #171d22 #050f17 #0b1117 #030b12 #373839 #908e89 |
| Hangar | #0d1016 #000308 #07090d #03050a #a79166 #252a2e | #0e0f10 #473f38 #2b2723 #706254 #1b1e20 #b8a48a |
| Results (defeat) | #06070c #0c0f17 #1c2027 #090c15 #5c5753 #ada189 | #04090e #0a0e13 #0c171f #3a3d3f #1c2128 #81827e |
| Settings | #080a13 #030408 #080b14 #a28f6d #101218 #39393c | #08161e #0a1822 #030b13 #06111a #031018 #313f49 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Target: every role pair ≥ 25.0.

| Roles | Closest pair ΔE | Result |
|---|---|---|
| enemy vs background | 6 | ⚠️ too close |
| enemy_bullets vs background | 50 | ✅ |
| enemy_bullets vs player_bullets | 27 | ✅ |
| enemy_bullets vs enemy | 36 | ✅ |
| player_bullets vs background | 42 | ✅ |
