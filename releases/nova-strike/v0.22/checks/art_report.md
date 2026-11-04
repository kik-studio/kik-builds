# Art-direction check · build 0.22+148813e

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Gameplay | 28.0 / 26.5 | 15.4 / 21.2 | 16.3 / 12.0 | 0.31 / 0.48 | 0.01 / 0.03 | – | [art_01.jpg](art_01.jpg) |
| 2 | Title | 28.8 / 21.1 | 22.9 / 24.5 | 11.0 / 7.1 | 0.47 / 0.67 | 0.03 / 0.05 | – | [art_02.jpg](art_02.jpg) |
| 3 | Campaign map | 24.7 / 22.3 | 21.4 / 26.0 | 20.8 / 10.2 | 0.55 / 0.67 | 0.02 / 0.05 | more saturated, missing highlights/glow | [art_03.jpg](art_03.jpg) |
| 4 | Briefing | 12.1 / 16.6 | 21.7 / 20.8 | 6.9 / 8.6 | 0.86 / 0.76 | 0.01 / 0.03 | – | [art_04.jpg](art_04.jpg) |
| 5 | Results (victory) | 22.6 / 22.0 | 25.7 / 24.4 | 10.0 / 9.3 | 0.63 / 0.66 | 0.05 / 0.05 | – | [art_05.jpg](art_05.jpg) |
| 6 | Store | 16.2 / 15.0 | 20.2 / 20.2 | 5.6 / 6.8 | 0.76 / 0.79 | 0.03 / 0.03 | – | [art_06.jpg](art_06.jpg) |
| 7 | Hangar | 19.4 / 25.6 | 24.1 / 22.2 | 7.5 / 8.5 | 0.67 / 0.52 | 0.03 / 0.03 | – | [art_07.jpg](art_07.jpg) |
| 8 | Results (defeat) | 17.3 / 14.8 | 23.6 / 18.9 | 7.1 / 7.2 | 0.75 / 0.75 | 0.03 / 0.02 | – | [art_08.jpg](art_08.jpg) |
| 9 | Settings | 7.6 / 8.9 | 15.7 / 12.5 | 4.7 / 7.9 | 0.89 / 0.93 | 0.01 / 0.01 | less colourful | [art_09.jpg](art_09.jpg) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Gameplay | #304862 #12233a #465a6d #1e2d42 #2f3443 #74868c | #131215 #504135 #765e4a #262220 #37291f #b9a080 |
| Title | #14151b #47464e #2e2c30 #20242f #756c6a #d6b582 | #2e2d2d #05070c #0b1017 #18181b #605c56 #bbb3a4 |
| Campaign map | #1c0e0e #573025 #411d17 #2f1714 #865038 #cc9e64 | #030d16 #202e39 #0b161e #616d71 #03121e #c7bea7 |
| Briefing | #07090f #0e0e13 #0a0a0f #262020 #a98c62 #05080e | #040b12 #1b2128 #081119 #3d3f44 #111317 #9c927c |
| Results (victory) | #0b0e17 #3a3432 #15141a #7b6a52 #060810 #c7b180 | #2a2e31 #050e16 #0c141b #171718 #5e5e5d #c3b496 |
| Store | #06080e #121216 #171d26 #3f3b37 #2a2625 #968978 | #171d22 #050f17 #0b1117 #030b12 #373839 #908e89 |
| Hangar | #030408 #2c2b2d #121114 #09090d #5e5952 #bca577 | #0e0f10 #473f38 #2b2723 #706254 #1b1e20 #b8a48a |
| Results (defeat) | #0b0e16 #05070c #1a1e26 #5b5754 #ab9e85 #080b12 | #04090e #0a0e13 #0c171f #3a3d3f #1c2128 #81827e |
| Settings | #03050a #101621 #010103 #020306 #06080e #53565b | #08161e #0a1822 #030b13 #06111a #031018 #313f49 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Target: every role pair ≥ 25.0.

| Roles | Closest pair ΔE | Result |
|---|---|---|
| enemy vs background | 6 | ⚠️ too close |
| enemy_bullets vs background | 50 | ✅ |
| enemy_bullets vs player_bullets | 27 | ✅ |
| enemy_bullets vs enemy | 36 | ✅ |
| player_bullets vs background | 42 | ✅ |
