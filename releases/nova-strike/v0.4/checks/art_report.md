# Art-direction check · build 0.4+0a00b06

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Gameplay | 16.9 / 26.5 | 16.1 / 21.2 | 12.9 / 12.0 | 0.71 / 0.48 | 0.01 / 0.03 | – | [art_01.png](art_01.png) |
| 2 | Title | 27.4 / 21.1 | 20.5 / 24.5 | 10.7 / 7.1 | 0.48 / 0.67 | 0.03 / 0.05 | – | [art_02.png](art_02.png) |
| 3 | Campaign map | 25.4 / 22.3 | 23.2 / 26.0 | 15.7 / 10.2 | 0.56 / 0.67 | 0.02 / 0.05 | missing highlights/glow | [art_03.png](art_03.png) |
| 4 | Briefing | 12.1 / 16.6 | 19.1 / 20.8 | 7.9 / 8.6 | 0.87 / 0.76 | 0.02 / 0.03 | – | [art_04.png](art_04.png) |
| 5 | Results (victory) | 18.1 / 22.0 | 21.4 / 24.4 | 8.3 / 9.3 | 0.68 / 0.66 | 0.03 / 0.05 | – | [art_05.png](art_05.png) |
| 6 | Store | 14.6 / 15.0 | 14.3 / 20.2 | 5.4 / 6.8 | 0.76 / 0.79 | 0.01 / 0.03 | – | [art_06.png](art_06.png) |
| 7 | Hangar | 14.9 / 25.6 | 15.7 / 22.2 | 6.1 / 8.5 | 0.75 / 0.52 | 0.01 / 0.03 | – | [art_07.png](art_07.png) |
| 8 | Results (defeat) | 13.2 / 14.8 | 20.0 / 18.9 | 7.0 / 7.2 | 0.84 / 0.75 | 0.03 / 0.02 | – | [art_08.png](art_08.png) |
| 9 | Settings | 9.6 / 8.9 | 16.0 / 12.5 | 6.8 / 7.9 | 0.89 / 0.93 | 0.0 / 0.01 | – | [art_09.png](art_09.png) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Gameplay | #212738 #0a1528 #050c1b #484148 #131824 #8b7062 | #131215 #504135 #765e4a #262220 #37291f #b9a080 |
| Title | #141721 #242732 #66636b #363a48 #4e4b54 #baa480 | #2e2d2d #05070c #0b1017 #18181b #605c56 #bbb3a4 |
| Campaign map | #0b101c #313b51 #1f1f2b #121928 #5f6e84 #afb29e | #030d16 #202e39 #0b161e #616d71 #03121e #c7bea7 |
| Briefing | #0b111b #070c15 #0b0e16 #1d1c21 #111319 #84755e | #040b12 #1b2128 #081119 #3d3f44 #111317 #9c927c |
| Results (victory) | #0d1016 #070b14 #4d473d #2a2829 #121217 #ae986e | #2a2e31 #050e16 #0c141b #171718 #5e5e5d #c3b496 |
| Store | #0a0e15 #13151a #383736 #1c2028 #282726 #6a645a | #171d22 #050f17 #0b1117 #030b12 #373839 #908e89 |
| Hangar | #0a1019 #252529 #3f3937 #14151a #080a0f #70675e | #0e0f10 #473f38 #2b2723 #706254 #1b1e20 #b8a48a |
| Results (defeat) | #0b0e15 #070a10 #232931 #15181f #0e131c #948973 | #04090e #0a0e13 #0c171f #3a3d3f #1c2128 #81827e |
| Settings | #0c1119 #04060c #090e15 #181e27 #070c13 #656055 | #08161e #0a1822 #030b13 #06111a #031018 #313f49 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Target: every role pair ≥ 25.0.

| Roles | Closest pair ΔE | Result |
|---|---|---|
| enemy vs background | 6 | ⚠️ too close |
| enemy_bullets vs background | 50 | ✅ |
| enemy_bullets vs player_bullets | 27 | ✅ |
| enemy_bullets vs enemy | 36 | ✅ |
| player_bullets vs background | 42 | ✅ |
