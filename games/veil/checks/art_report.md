# Art-direction check · build 0.14+24c2cee

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Flying (chase cam) vs board 01 'storm world' | 47.6 / 54.2 | 25.1 / 20.0 | 21.9 / 15.1 | 0.15 / 0.04 | 0.1 / 0.13 | – | [art_01.png](art_01.png) |
| 2 | Home (live 3D) vs board 06 'home / launch' | 38.0 / 62.0 | 21.1 / 17.6 | 14.5 / 19.2 | 0.16 / 0.0 | 0.04 / 0.18 | darker, missing highlights/glow | [art_02.png](art_02.png) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Flying (chase cam) vs board 01 'storm world' | #8887b2 #20213f #b6acc6 #474a78 #655d7c #e0d4df | #8c8ca7 #616683 #3e4461 #72718c #b8b3c7 #e3dae0 |
| Home (live 3D) vs board 06 'home / launch' | #474156 #2c1f23 #8b829b #5b556c #716885 #c3bacf | #8381a5 #565c85 #9798bd #c9c0d8 #b1a6c5 #eadfe8 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Target: every role pair ≥ 25.0.

| Roles | Closest pair ΔE | Result |
|---|---|---|
| enemy vs background | 82 | ✅ |
| player_bullets vs background | 77 | ✅ |
