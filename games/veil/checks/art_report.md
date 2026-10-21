# Art-direction check · build 0.5+d97bfc2

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Flying (chase cam) vs board 01 'storm world' | 57.0 / 54.2 | 27.2 / 20.0 | 21.3 / 15.1 | 0.14 / 0.04 | 0.26 / 0.13 | – | [art_01.png](art_01.png) |
| 2 | Home (live 3D) vs board 06 'home / launch' | 39.5 / 62.0 | 20.3 / 17.6 | 18.1 / 19.2 | 0.21 / 0.0 | 0.04 / 0.18 | darker, missing highlights/glow | [art_02.png](art_02.png) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Flying (chase cam) vs board 01 'storm world' | #292850 #b3abce #8988b2 #d5cee9 #e7e3f5 #5a5a88 | #8c8ca7 #616683 #3e4461 #72718c #b8b3c7 #e3dae0 |
| Home (live 3D) vs board 06 'home / launch' | #252342 #484661 #605e79 #89839d #746d89 #beb7d4 | #8381a5 #565c85 #9798bd #c9c0d8 #b1a6c5 #eadfe8 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Pending: the game hasn't declared its colour roles (`art.palette` in config/build_checks.json).
