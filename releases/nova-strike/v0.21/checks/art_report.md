# Art-direction check · build 0.21+55f6690

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Gameplay | 21.9 / 26.5 | 14.4 / 21.2 | 14.0 / 12.0 | 0.52 / 0.48 | 0.01 / 0.03 | flatter | [art_01.jpg](art_01.jpg) |
| 2 | Title | 28.7 / 21.1 | 21.7 / 24.5 | 11.5 / 7.1 | 0.44 / 0.67 | 0.04 / 0.05 | more saturated | [art_02.jpg](art_02.jpg) |
| 3 | Campaign map | 22.6 / 22.3 | 17.6 / 26.0 | 20.3 / 10.2 | 0.55 / 0.67 | 0.02 / 0.05 | flatter, more saturated, missing highlights/glow | [art_03.jpg](art_03.jpg) |
| 4 | Briefing | 12.5 / 16.6 | 21.2 / 20.8 | 6.5 / 8.6 | 0.84 / 0.76 | 0.02 / 0.03 | – | [art_04.jpg](art_04.jpg) |
| 5 | Results (victory) | 23.3 / 22.0 | 26.1 / 24.4 | 10.2 / 9.3 | 0.62 / 0.66 | 0.05 / 0.05 | – | [art_05.jpg](art_05.jpg) |
| 6 | Store | 19.5 / 15.0 | 22.6 / 20.2 | 6.8 / 6.8 | 0.69 / 0.79 | 0.03 / 0.03 | – | [art_06.jpg](art_06.jpg) |
| 7 | Hangar | 12.6 / 25.6 | 22.1 / 22.2 | 6.9 / 8.5 | 0.83 / 0.52 | 0.03 / 0.03 | darker | [art_07.jpg](art_07.jpg) |
| 8 | Results (defeat) | 17.8 / 14.8 | 23.6 / 18.9 | 7.3 / 7.2 | 0.74 / 0.75 | 0.03 / 0.02 | – | [art_08.jpg](art_08.jpg) |
| 9 | Settings | 13.6 / 8.9 | 22.4 / 12.5 | 6.7 / 7.9 | 0.81 / 0.93 | 0.01 / 0.01 | – | [art_09.jpg](art_09.jpg) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Gameplay | #26374c #0c1b2f #354556 #15253a #222836 #697375 | #131215 #504135 #765e4a #262220 #37291f #b9a080 |
| Title | #13161e #4b4952 #312d34 #766962 #21242e #c5ab83 | #2e2d2d #05070c #0b1017 #18181b #605c56 #bbb3a4 |
| Campaign map | #1f0e0e #542d23 #321914 #7a4631 #451d17 #a87c5a | #030d16 #202e39 #0b161e #616d71 #03121e #c7bea7 |
| Briefing | #0e0e15 #07090f #0a0a0f #998664 #05080d #2b2626 | #040b12 #1b2128 #081119 #3d3f44 #111317 #9c927c |
| Results (victory) | #0b0e17 #3d3733 #16151a #7f6d54 #06070f #cbb683 | #2a2e31 #050e16 #0c141b #171718 #5e5e5d #c3b496 |
| Store | #080910 #2f2b29 #0e1016 #1a1719 #5b5046 #b09e85 | #171d22 #050f17 #0b1117 #030b12 #373839 #908e89 |
| Hangar | #0e1117 #010308 #08090e #04060b #ab9567 #2d2e2e | #0e0f10 #473f38 #2b2723 #706254 #1b1e20 #b8a48a |
| Results (defeat) | #0c0f17 #06070d #1c2027 #5b5753 #aea289 #0a0c13 | #04090e #0a0e13 #0c171f #3a3d3f #1c2128 #81827e |
| Settings | #070a12 #030408 #080b14 #0f1118 #a28e6c #38383a | #08161e #0a1822 #030b13 #06111a #031018 #313f49 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Target: every role pair ≥ 25.0.

| Roles | Closest pair ΔE | Result |
|---|---|---|
| enemy vs background | 6 | ⚠️ too close |
| enemy_bullets vs background | 50 | ✅ |
| enemy_bullets vs player_bullets | 27 | ✅ |
| enemy_bullets vs enemy | 36 | ✅ |
| player_bullets vs background | 42 | ✅ |
