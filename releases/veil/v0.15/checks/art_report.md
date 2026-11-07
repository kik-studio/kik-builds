# Art-direction check · build 0.15+184f23b

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Flying (chase cam) vs board 01 'storm world' | 47.8 / 54.2 | 24.9 / 20.0 | 22.0 / 15.1 | 0.15 / 0.04 | 0.1 / 0.13 | – | [art_01.jpg](art_01.jpg) |
| 2 | Home (live 3D) vs board 06 'home / launch' | 38.5 / 62.0 | 21.3 / 17.6 | 15.3 / 19.2 | 0.16 / 0.0 | 0.04 / 0.18 | darker, missing highlights/glow | [art_02.jpg](art_02.jpg) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Flying (chase cam) vs board 01 'storm world' | #8887b3 #212240 #b6acc6 #484a79 #655d7b #e0d4df | #8c8ca7 #616683 #3e4461 #72718c #b8b3c7 #e3dae0 |
| Home (live 3D) vs board 06 'home / launch' | #403e57 #8b839c #665e7a #2a1e21 #524760 #c3bbd1 | #8381a5 #565c85 #9798bd #c9c0d8 #b1a6c5 #eadfe8 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Target: every role pair ≥ 25.0.

| Roles | Closest pair ΔE | Result |
|---|---|---|
| enemy vs background | 82 | ✅ |
| player_bullets vs background | 77 | ✅ |
