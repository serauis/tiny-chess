# tiny-chess — a chess engine in under 4 KB of Python

A deterministic negamax engine (alpha-beta + quiescence) packed into a
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
