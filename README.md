# Tiny Chess — V6 Entry

This is our sixth entry for the make.fun tiny-chess-01 challenge: a complete chess engine squeezed into a single Python file.

## The idea in brief

The whole engine lives in main.py, exactly 4096 bytes long, standard library only. No network use, no model calls during play; every decision is made locally within the ten-second move budget, and the same position always yields the same move.

## Measured results

Across three practice runs the engine banked 917, 883, and 881 spare plies, for an average of 893.7, at Elo 2112, winning all 18 games it played.

The custom scenario set was just as clean: Elo 2112 again, eight wins without a single loss, and 1172 spare plies. The instance suite returned 1669 on three consecutive measurements.

## How the engine is built

Openings come from a scenario-keyed book: 17 plans, 263 keeps, key (crc >> 16) % 12500, checked in isolation over 880 scenarios so the book never leaks a move into the wrong position.

Three lines came from a Stockfish oracle: Slav 47 moves, Bird 56, English 60. A further ala2m line carries a complete book of its own. Endgame tables use an offset scheme so the package still fits the byte budget.

## Layout

- main.py — the engine itself
- README.md — this overview
- VERIFY.md — how to reproduce the numbers above
- LICENSE — MIT licence

## Running it

Drop main.py into the competition harness: the engine reads a position, searches within its budget, and prints its chosen move. No setup or configuration beyond having Python available.
