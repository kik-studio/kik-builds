# Art-direction check · build 0.11+292d685

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Flying (chase cam) vs board 01 'storm world' | 49.4 / 54.2 | 23.4 / 20.0 | 24.0 / 15.1 | 0.13 / 0.04 | 0.1 / 0.13 | – | [art_01.png](art_01.png) |
| 2 | Home (live 3D) vs board 06 'home / launch' | 39.1 / 62.0 | 21.7 / 17.6 | 16.9 / 19.2 | 0.23 / 0.0 | 0.04 / 0.18 | darker, missing highlights/glow | [art_02.png](art_02.png) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Flying (chase cam) vs board 01 'storm world' | #262a58 #8a89b1 #b5acc6 #6a6591 #464a7f #e0d4df | #8c8ca7 #616683 #3e4461 #72718c #b8b3c7 #e3dae0 |
| Home (live 3D) vs board 06 'home / launch' | #211f3f #42405d #8d8698 #63607b #7a7388 #c5bdd0 | #8381a5 #565c85 #9798bd #c9c0d8 #b1a6c5 #eadfe8 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Target: every role pair ≥ 25.0.

| Roles | Closest pair ΔE | Result |
|---|---|---|
| enemy vs background | 82 | ✅ |
| player_bullets vs background | 77 | ✅ |
