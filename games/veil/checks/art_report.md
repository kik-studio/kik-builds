# Art-direction check · build 0.1+61b9f89

Automated: each capture from this build beside its visual-bible target (sheets below), with measured differences. The numbers flag drift; they don't judge quality. Look at the sheets.

| # | Screen | Lightness (build / target) | Contrast | Colourfulness | Dark share | Highlights | Drift flags | Sheet |
|---|---|---|---|---|---|---|---|---|
| 1 | Flying (chase cam) vs board 01 'storm world' | 39.7 / 54.2 | 26.7 / 20.0 | 12.7 / 15.1 | 0.3 / 0.04 | 0.08 / 0.13 | darker | [art_01.png](art_01.png) |
| 2 | Home (live 3D) vs board 06 'home / launch' | 47.2 / 62.0 | 25.1 / 17.6 | 15.3 / 19.2 | 0.27 / 0.0 | 0.03 / 0.18 | darker, missing highlights/glow | [art_02.png](art_02.png) |

## Main colours (6, most used first)

| Screen | Build | Target |
|---|---|---|
| Flying (chase cam) vs board 01 'storm world' | #0c0f23 #91899e #5f5a6e #7b7589 #d2cedf #3a394d | #8c8ca7 #616683 #3e4461 #72718c #b8b3c7 #e3dae0 |
| Home (live 3D) vs board 06 'home / launch' | #a197af #817a92 #111731 #0d122e #afa7bd #9990a8 | #8381a5 #565c85 #9798bd #c9c0d8 #b1a6c5 #eadfe8 |

## Colour-role separation (ΔE, CIE76; higher = easier to tell apart)

Pending: the game hasn't declared its colour roles (`art.palette` in config/build_checks.json).
