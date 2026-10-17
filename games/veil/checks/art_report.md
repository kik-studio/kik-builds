# Art-direction check · build 0.2+bd667e7

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Flying (chase cam) vs board 01 'storm world' | 46.1 / 54.2 | 19.8 / 20.0 | 15.1 / 15.1 | 0.01 / 0.04 | 0.09 / 0.13 | – | [art_01.png](art_01.png) |
| 2 | Home (live 3D) vs board 06 'home / launch' | 46.1 / 62.0 | 19.8 / 17.6 | 15.1 / 19.2 | 0.01 / 0.0 | 0.09 / 0.18 | darker | [art_02.png](art_02.png) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Flying (chase cam) vs board 01 'storm world' | #3e415a #51526a #656985 #474e6c #9090a6 #dedbea | #8c8ca7 #616683 #3e4461 #72718c #b8b3c7 #e3dae0 |
| Home (live 3D) vs board 06 'home / launch' | #3e415a #51526a #656985 #474e6c #9090a6 #dedbea | #8381a5 #565c85 #9798bd #c9c0d8 #b1a6c5 #eadfe8 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Pending: the game hasn't declared its colour roles (`art.palette` in config/build_checks.json).
