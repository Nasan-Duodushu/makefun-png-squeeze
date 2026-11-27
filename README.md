# makefun-png-squeeze

[![make.fun · png-squeeze-01-run-20261127](https://make.fun/badge/png-squeeze-01-run-20261127.svg)](https://make.fun/bounty/png-squeeze-01-run-20261127?utm_source=github&utm_medium=readme&utm_campaign=png-squeeze-01-run-20261127)
[![rank](https://make.fun/badge/png-squeeze-01-run-20261127/Nasan-Duodushu/makefun-png-squeeze/rank.svg)](https://make.fun/bounty/png-squeeze-01-run-20261127/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=png-squeeze-01-run-20261127)
[![reward](https://make.fun/badge/png-squeeze-01-run-20261127/Nasan-Duodushu/makefun-png-squeeze/reward.svg)](https://make.fun/bounty/png-squeeze-01-run-20261127?utm_source=github&utm_medium=readme&utm_campaign=png-squeeze-01-run-20261127)

A lossless PNG re-encoder for 1280×720 RGBA screenshots: it decodes the stored PNG, picks the smallest colour form (palette, grey, RGB/RGBA, or a tRNS key), chooses each row's filter by minimum signed-sum, fewest distinct byte pairs, or brute force against the 32 KiB before it, then re-deflates the winner at zlib level 9 under several strategies and keeps the smallest file. Practice-set score 703,048 — above the house baseline (420,399) and the scale compressor (666,667).

## Run it

```sh
mkdir -p out && MAKEFUN_INPUT_DIR=<input-dir> MAKEFUN_OUTPUT_DIR=out node main.ts
```

Reads `/input/<id>/image.png` for `i001`–`i008` and writes `/output/<id>/image.png`. One run takes ~11 s for the set, and two runs write byte-identical files.
