# Art-direction check · build 0.6+3da11e3

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Flying (chase cam) vs board 01 'storm world' | 58.5 / 54.2 | 26.3 / 20.0 | 20.3 / 15.1 | 0.13 / 0.04 | 0.29 / 0.13 | – | [art_01.jpg](art_01.jpg) |
| 2 | Home (live 3D) vs board 06 'home / launch' | 38.4 / 62.0 | 21.6 / 17.6 | 17.0 / 19.2 | 0.23 / 0.0 | 0.04 / 0.18 | darker, missing highlights/glow | [art_02.jpg](art_02.jpg) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Flying (chase cam) vs board 01 'storm world' | #302e54 #7a75a2 #a9a2c4 #dbd3eb #e9e3f4 #c7b9d4 | #8c8ca7 #616683 #3e4461 #72718c #b8b3c7 #e3dae0 |
| Home (live 3D) vs board 06 'home / launch' | #1f1d3c #6d6880 #8d8698 #383956 #4c4864 #c0b9cd | #8381a5 #565c85 #9798bd #c9c0d8 #b1a6c5 #eadfe8 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Pending: the game hasn't declared its colour roles (`art.palette` in config/build_checks.json).
