# Art-direction check · build 0.7+1975f2e

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Gameplay | 20.2 / 26.5 | 18.4 / 21.2 | 16.0 / 12.0 | 0.64 / 0.48 | 0.02 / 0.03 | – | [art_01.png](art_01.png) |
| 2 | Title | 28.2 / 21.1 | 20.3 / 24.5 | 10.8 / 7.1 | 0.44 / 0.67 | 0.03 / 0.05 | – | [art_02.png](art_02.png) |
| 3 | Campaign map | 22.2 / 22.3 | 21.7 / 26.0 | 14.3 / 10.2 | 0.66 / 0.67 | 0.04 / 0.05 | – | [art_03.png](art_03.png) |
| 4 | Briefing | 13.4 / 16.6 | 20.8 / 20.8 | 7.9 / 8.6 | 0.84 / 0.76 | 0.03 / 0.03 | – | [art_04.png](art_04.png) |
| 5 | Results (victory) | 15.8 / 22.0 | 21.8 / 24.4 | 7.9 / 9.3 | 0.77 / 0.66 | 0.03 / 0.05 | – | [art_05.png](art_05.png) |
| 6 | Store | 15.2 / 15.0 | 14.4 / 20.2 | 5.6 / 6.8 | 0.75 / 0.79 | 0.01 / 0.03 | – | [art_06.png](art_06.png) |
| 7 | Hangar | 17.7 / 25.6 | 18.5 / 22.2 | 7.2 / 8.5 | 0.67 / 0.52 | 0.02 / 0.03 | – | [art_07.png](art_07.png) |
| 8 | Results (defeat) | 13.3 / 14.8 | 21.1 / 18.9 | 7.1 / 7.2 | 0.85 / 0.75 | 0.03 / 0.02 | – | [art_08.png](art_08.png) |
| 9 | Settings | 9.9 / 8.9 | 17.2 / 12.5 | 6.9 / 7.9 | 0.89 / 0.93 | 0.01 / 0.01 | – | [art_09.png](art_09.png) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Gameplay | #0b1935 #262e46 #060e21 #4f4c5a #151c2e #98857a | #131215 #504135 #765e4a #262220 #37291f #b9a080 |
| Title | #131823 #272a35 #67646c #393c49 #4f4d55 #bba681 | #2e2d2d #05070c #0b1017 #18181b #605c56 #bbb3a4 |
| Campaign map | #181a25 #302a32 #11141d #c8a176 #5b4646 #281a1d | #030d16 #202e39 #0b161e #616d71 #03121e #c7bea7 |
| Briefing | #11141b #0b0f16 #070b12 #090d16 #2d292a #a08f6e | #040b12 #1b2128 #081119 #3d3f44 #111317 #9c927c |
| Results (victory) | #0d1015 #171a20 #3e3c38 #070b14 #0b0d14 #ab976d | #2a2e31 #050e16 #0c141b #171718 #5e5e5d #c3b496 |
| Store | #0a0e16 #15171c #3a3836 #1d2229 #2b2928 #6b655b | #171d22 #050f17 #0b1117 #030b12 #373839 #908e89 |
| Hangar | #2d2c30 #090c12 #47403f #0c111c #18191c #908068 | #0e0f10 #473f38 #2b2723 #706254 #1b1e20 #b8a48a |
| Results (defeat) | #090d16 #10131a #06090f #21262d #9a8e74 #0b0e14 | #04090e #0a0e13 #0c171f #3a3d3f #1c2128 #81827e |
| Settings | #070b13 #0b1018 #131821 #03050a #090e17 #686050 | #08161e #0a1822 #030b13 #06111a #031018 #313f49 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Target: every role pair ≥ 25.0.

| Roles | Closest pair ΔE | Result |
|---|---|---|
| enemy vs background | 6 | ⚠️ too close |
| enemy_bullets vs background | 50 | ✅ |
| enemy_bullets vs player_bullets | 27 | ✅ |
| enemy_bullets vs enemy | 36 | ✅ |
| player_bullets vs background | 42 | ✅ |
