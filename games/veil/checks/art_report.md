# Art-direction check · build 0.9+787c1a2

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Flying (chase cam) vs board 01 'storm world' | 58.1 / 54.2 | 26.9 / 20.0 | 20.6 / 15.1 | 0.14 / 0.04 | 0.28 / 0.13 | – | [art_01.png](art_01.png) |
| 2 | Home (live 3D) vs board 06 'home / launch' | 39.2 / 62.0 | 21.7 / 17.6 | 17.0 / 19.2 | 0.23 / 0.0 | 0.04 / 0.18 | darker, missing highlights/glow | [art_02.png](art_02.png) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Flying (chase cam) vs board 01 'storm world' | #2c2b52 #b8aecc #dbd2ea #8e85ad #676697 #e9e3f4 | #8c8ca7 #616683 #3e4461 #72718c #b8b3c7 #e3dae0 |
| Home (live 3D) vs board 06 'home / launch' | #6e6982 #211f3f #90899c #373855 #4c4864 #c4bcd1 | #8381a5 #565c85 #9798bd #c9c0d8 #b1a6c5 #eadfe8 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Target: every role pair ≥ 25.0.

| Roles | Closest pair ΔE | Result |
|---|---|---|
| enemy vs background | 82 | ✅ |
| player_bullets vs background | 77 | ✅ |
