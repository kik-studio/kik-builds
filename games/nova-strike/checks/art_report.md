# Art-direction check · build 0.9+da2ee65

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Gameplay | 31.8 / 26.5 | 25.6 / 21.2 | 17.0 / 12.0 | 0.46 / 0.48 | 0.05 / 0.03 | – | [art_01.png](art_01.png) |
| 2 | Title | 28.5 / 21.1 | 21.5 / 24.5 | 11.2 / 7.1 | 0.45 / 0.67 | 0.03 / 0.05 | – | [art_02.png](art_02.png) |
| 3 | Campaign map | missing capture | | | | | | |
| 4 | Briefing | 15.4 / 16.6 | 23.2 / 20.8 | 7.6 / 8.6 | 0.78 / 0.76 | 0.03 / 0.03 | – | [art_04.png](art_04.png) |
| 5 | Results (victory) | 21.9 / 22.0 | 25.1 / 24.4 | 9.6 / 9.3 | 0.64 / 0.66 | 0.04 / 0.05 | – | [art_05.png](art_05.png) |
| 6 | Store | 18.9 / 15.0 | 21.6 / 20.2 | 6.6 / 6.8 | 0.68 / 0.79 | 0.03 / 0.03 | – | [art_06.png](art_06.png) |
| 7 | Hangar | 16.3 / 25.6 | 25.4 / 22.2 | 8.7 / 8.5 | 0.78 / 0.52 | 0.04 / 0.03 | – | [art_07.png](art_07.png) |
| 8 | Results (defeat) | 17.5 / 14.8 | 23.3 / 18.9 | 7.2 / 7.2 | 0.75 / 0.75 | 0.02 / 0.02 | – | [art_08.png](art_08.png) |
| 9 | Settings | 13.2 / 8.9 | 21.6 / 12.5 | 6.1 / 7.9 | 0.81 / 0.93 | 0.01 / 0.01 | – | [art_09.png](art_09.png) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Gameplay | #071229 #141f38 #a48668 #61534d #2f2a31 #ddbe94 | #131215 #504135 #765e4a #262220 #37291f #b9a080 |
| Title | #13151e #4b4850 #756a65 #302c31 #20232d #bfa77f | #2e2d2d #05070c #0b1017 #18181b #605c56 #bbb3a4 |
| Briefing | #06080e #0b0b11 #0e1017 #b19b73 #1f191a #52433a | #040b12 #1b2128 #081119 #3d3f44 #111317 #9c927c |
| Results (victory) | #0d0f18 #070911 #373231 #756652 #151419 #c3ac7c | #2a2e31 #050e16 #0c141b #171718 #5e5e5d #c3b496 |
| Store | #080a10 #2f2b29 #0e1016 #564c44 #191719 #a9977e | #171d22 #050f17 #0b1117 #030b12 #373839 #908e89 |
| Hangar | #10131a #000308 #c3a871 #08090f #48413a #0a111f | #0e0f10 #473f38 #2b2723 #706254 #1b1e20 #b8a48a |
| Results (defeat) | #05070c #0c0f17 #1c1f27 #090c15 #5a5654 #ab9f86 | #04090e #0a0e13 #0c171f #3a3d3f #1c2128 #81827e |
| Settings | #070a13 #030408 #080c14 #3d3c3e #9b8a6e #13141a | #08161e #0a1822 #030b13 #06111a #031018 #313f49 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Target: every role pair ≥ 25.0.

| Roles | Closest pair ΔE | Result |
|---|---|---|
| enemy vs background | 6 | ⚠️ too close |
| enemy_bullets vs background | 50 | ✅ |
| enemy_bullets vs player_bullets | 27 | ✅ |
| enemy_bullets vs enemy | 36 | ✅ |
| player_bullets vs background | 42 | ✅ |
