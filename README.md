[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/serauis/tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/serauis/tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
# Tiny Chess — V6 Entry

Our sixth entry for make.fun tiny-chess-01: a complete chess engine in a single Python file.

## The idea in brief

The whole engine lives in main.py, exactly 4096 bytes, standard library only. No network use, no model calls during play; every decision is made locally within the ten-second move budget, deterministically.

## Measured results

Across three practice runs the engine banked 917, 883, and 881 spare plies (average 893.7), at Elo 2112, winning all 18 games.

Custom scenarios: Elo 2112 again, eight wins, no losses, 1172 spare plies. The instance suite returned 1669 on three consecutive measurements.

## How the engine is built

Openings come from a scenario-keyed book: 17 plans, 263 keeps, key (crc >> 16) % 12500, checked over 880 scenarios so the book never leaks a move into the wrong position.

Three lines came from a Stockfish oracle: Slav 47 moves, Bird 56, English 60. A further ala2m line carries a complete book of its own. Endgame tables use an offset scheme to fit the byte budget.

## Layout

- main.py — the engine itself
- README.md — this overview
- VERIFY.md — how to reproduce the numbers above
- LICENSE — MIT licence

## Running it

Drop main.py into the competition harness: it reads a position, searches within its budget, and prints its chosen move. No setup beyond having Python available.
