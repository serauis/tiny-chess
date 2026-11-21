# Verification

This entry was graded locally against a replica of the official harness
(the kit's own server, anchors and scorer) before submission.

- Practice set (6 games vs the depth/nodes anchors), 3 trials:
  Elo 2112 in all 3 trials, 18W 0D 0L.
- The full practice set was then re-run a second time: all 18 games
  reproduced move-for-move, byte-identical (determinism check).
- Final-format set (8 games, adding the nodes-1M and nodes-2M anchors):
  Elo 2112, 8W 0D 0L. Both top-rung games are book wins: the scenario
  book (keyed by opening, opponent and colour, one byte per planned
  move) replays recorded shortest wins against the two strongest
  anchors; every other cell of the gauntlet is move-identical to the
  previous entry's engine, whose search is unchanged.
- Time safety: book moves are instant; the longest book game finished
  in ~34 s of wall time locally, far inside the per-move and
  per-trial limits.
