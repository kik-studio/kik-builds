# Art-direction check · build 0.7+5975cb8

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Gameplay | 20.8 / 26.5 | 19.7 / 21.2 | 15.8 / 12.0 | 0.64 / 0.48 | 0.02 / 0.03 | – | [art_01.png](art_01.png) |
| 2 | Title | 27.4 / 21.1 | 20.6 / 24.5 | 10.7 / 7.1 | 0.48 / 0.67 | 0.03 / 0.05 | – | [art_02.png](art_02.png) |
| 3 | Campaign map | 22.3 / 22.3 | 21.6 / 26.0 | 14.3 / 10.2 | 0.66 / 0.67 | 0.04 / 0.05 | – | [art_03.png](art_03.png) |
| 4 | Briefing | 13.0 / 16.6 | 20.3 / 20.8 | 8.1 / 8.6 | 0.86 / 0.76 | 0.03 / 0.03 | – | [art_04.png](art_04.png) |
| 5 | Results (victory) | 18.2 / 22.0 | 22.6 / 24.4 | 8.4 / 9.3 | 0.71 / 0.66 | 0.04 / 0.05 | – | [art_05.png](art_05.png) |
| 6 | Store | 14.7 / 15.0 | 14.4 / 20.2 | 5.5 / 6.8 | 0.76 / 0.79 | 0.01 / 0.03 | – | [art_06.png](art_06.png) |
| 7 | Hangar | 14.9 / 25.6 | 15.7 / 22.2 | 6.1 / 8.5 | 0.75 / 0.52 | 0.01 / 0.03 | – | [art_07.png](art_07.png) |
| 8 | Results (defeat) | 13.4 / 14.8 | 20.5 / 18.9 | 7.0 / 7.2 | 0.84 / 0.75 | 0.03 / 0.02 | – | [art_08.png](art_08.png) |
| 9 | Settings | 10.1 / 8.9 | 17.6 / 12.5 | 7.0 / 7.9 | 0.89 / 0.93 | 0.01 / 0.01 | – | [art_09.png](art_09.png) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Gameplay | #101a31 #050e21 #18284a #584f56 #35343f #a48e7d | #131215 #504135 #765e4a #262220 #37291f #b9a080 |
| Title | #141721 #66636b #42434e #2a2b34 #1e2330 #baa481 | #2e2d2d #05070c #0b1017 #18181b #605c56 #bbb3a4 |
| Campaign map | #181a25 #322c33 #11141d #cba478 #5f4948 #281a1e | #030d16 #202e39 #0b161e #616d71 #03121e #c7bea7 |
| Briefing | #090e18 #11131b #070c14 #262426 #0c0f16 #9a896b | #040b12 #1b2128 #081119 #3d3f44 #111317 #9c927c |
| Results (victory) | #0b0f17 #101115 #242326 #504940 #070b14 #b8a173 | #2a2e31 #050e16 #0c141b #171718 #5e5e5d #c3b496 |
| Store | #0a0e16 #14151a #383735 #1b2028 #282726 #6a6459 | #171d22 #050f17 #0b1117 #030b12 #373839 #908e89 |
| Hangar | #0a1019 #252529 #3f3937 #14151a #080a0f #71685f | #0e0f10 #473f38 #2b2723 #706254 #1b1e20 #b8a48a |
| Results (defeat) | #070a10 #12161d #090e17 #242a32 #0c0f14 #9a8e75 | #04090e #0a0e13 #0c171f #3a3d3f #1c2128 #81827e |
| Settings | #070b13 #0a0f17 #151a23 #03050a #0c1119 #716754 | #08161e #0a1822 #030b13 #06111a #031018 #313f49 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Target: every role pair ≥ 25.0.

| Roles | Closest pair ΔE | Result |
|---|---|---|
| enemy vs background | 6 | ⚠️ too close |
| enemy_bullets vs background | 50 | ✅ |
| enemy_bullets vs player_bullets | 27 | ✅ |
| enemy_bullets vs enemy | 36 | ✅ |
| player_bullets vs background | 42 | ✅ |
