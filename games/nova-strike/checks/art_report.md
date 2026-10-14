# Art-direction check · build 0.10+eb75b6d

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Gameplay | 30.2 / 26.5 | 16.2 / 21.2 | 16.1 / 12.0 | 0.25 / 0.48 | 0.01 / 0.03 | – | [art_01.png](art_01.png) |
| 2 | Title | 29.3 / 21.1 | 21.6 / 24.5 | 10.9 / 7.1 | 0.44 / 0.67 | 0.03 / 0.05 | – | [art_02.png](art_02.png) |
| 3 | Campaign map | missing capture | | | | | | |
| 4 | Briefing | 15.7 / 16.6 | 23.5 / 20.8 | 7.7 / 8.6 | 0.77 / 0.76 | 0.03 / 0.03 | – | [art_04.png](art_04.png) |
| 5 | Results (victory) | 23.3 / 22.0 | 26.2 / 24.4 | 10.3 / 9.3 | 0.62 / 0.66 | 0.05 / 0.05 | – | [art_05.png](art_05.png) |
| 6 | Store | 18.9 / 15.0 | 21.7 / 20.2 | 6.6 / 6.8 | 0.69 / 0.79 | 0.03 / 0.03 | – | [art_06.png](art_06.png) |
| 7 | Hangar | 12.3 / 25.6 | 22.3 / 22.2 | 6.7 / 8.5 | 0.83 / 0.52 | 0.03 / 0.03 | darker | [art_07.png](art_07.png) |
| 8 | Results (defeat) | 17.8 / 14.8 | 23.6 / 18.9 | 7.2 / 7.2 | 0.74 / 0.75 | 0.03 / 0.02 | – | [art_08.png](art_08.png) |
| 9 | Settings | 13.3 / 8.9 | 22.1 / 12.5 | 6.7 / 7.9 | 0.81 / 0.93 | 0.0 / 0.01 | – | [art_09.png](art_09.png) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Gameplay | #334f6a #11243a #4b6173 #1f344d #313b4a #809399 | #131215 #504135 #765e4a #262220 #37291f #b9a080 |
| Title | #14171f #4f4b51 #796d66 #322d31 #23252d #bfa884 | #2e2d2d #05070c #0b1017 #18181b #605c56 #bbb3a4 |
| Briefing | #0c0c12 #070a10 #181619 #05070d #56473d #b29c74 | #040b12 #1b2128 #081119 #3d3f44 #111317 #9c927c |
| Results (victory) | #0c0e17 #3d3733 #17151b #060810 #7d6c53 #cab482 | #2a2e31 #050e16 #0c141b #171718 #5e5e5d #c3b496 |
| Store | #080a10 #2e2a29 #191719 #0e1016 #574d45 #a9987f | #171d22 #050f17 #0b1117 #030b12 #373839 #908e89 |
| Hangar | #0d1016 #000308 #07090d #03050a #262a2d #ab966a | #0e0f10 #473f38 #2b2723 #706254 #1b1e20 #b8a48a |
| Results (defeat) | #0c0f16 #05070c #1c1f27 #090c15 #5a5553 #aea188 | #04090e #0a0e13 #0c171f #3a3d3f #1c2128 #81827e |
| Settings | #080a13 #030408 #080b14 #a28e6c #111218 #3a3a3c | #08161e #0a1822 #030b13 #06111a #031018 #313f49 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Target: every role pair ≥ 25.0.

| Roles | Closest pair ΔE | Result |
|---|---|---|
| enemy vs background | 6 | ⚠️ too close |
| enemy_bullets vs background | 50 | ✅ |
| enemy_bullets vs player_bullets | 27 | ✅ |
| enemy_bullets vs enemy | 36 | ✅ |
| player_bullets vs background | 42 | ✅ |
