# tiny-chess

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/serauis/tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/serauis/tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in under 4 KB of Python, entered in make.fun's
[“Build the strongest chess engine in 4 KB of Python”](https://make.fun/bounty/tiny-chess-01)
bounty. A deterministic negamax engine (alpha-beta + quiescence) packed into a
4,083-byte `main.py` (LZMA payload + tiny unpacker, stdlib only).

Design:
- Flipped-board mailbox representation (position always from the side to move).
- Iterative deepening under a fixed, score-aware node budget (never a clock).
- Transposition table, killer moves, MVV-LVA ordering, check extensions.
- Tapered PeSTO piece-square tables (per-table mixed-radix blob encoding),
  pawn-structure terms (conditioned doubled / isolated), repetition contempt,
  and an endgame mop-up gradient (phase-gated king-centrality + approach).

Measured locally against the kit gauntlet (practice trials): trial 0 swept
6/6; trials 1 and 2 at 5 wins + 1 draw each, no losses.

## Run it

```sh
MAKEFUN_ENV_URL=<env-url> MAKEFUN_PROMPT_FILE=<prompt-file> python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
