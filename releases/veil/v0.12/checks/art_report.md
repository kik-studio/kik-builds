# Art-direction check · build 0.12+ee24599

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Flying (chase cam) vs board 01 'storm world' | 48.1 / 54.2 | 24.2 / 20.0 | 23.8 / 15.1 | 0.14 / 0.04 | 0.1 / 0.13 | – | [art_01.jpg](art_01.jpg) |
| 2 | Home (live 3D) vs board 06 'home / launch' | 38.8 / 62.0 | 19.8 / 17.6 | 17.4 / 19.2 | 0.14 / 0.0 | 0.04 / 0.18 | darker, missing highlights/glow | [art_02.jpg](art_02.jpg) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Flying (chase cam) vs board 01 'storm world' | #242654 #54527d #b6adc7 #737cae #9a91b8 #e0d4df | #8c8ca7 #616683 #3e4461 #72718c #b8b3c7 #e3dae0 |
| Home (live 3D) vs board 06 'home / launch' | #3d3b59 #8a829b #2e2945 #4a4360 #645d78 #c3bacf | #8381a5 #565c85 #9798bd #c9c0d8 #b1a6c5 #eadfe8 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Target: every role pair ≥ 25.0.

| Roles | Closest pair ΔE | Result |
|---|---|---|
| enemy vs background | 82 | ✅ |
| player_bullets vs background | 77 | ✅ |
