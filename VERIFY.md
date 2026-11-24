# How to verify V6

This file describes the checks anyone can run to confirm the numbers claimed in README.md, using only the files in this repository.

## Size and shape

Confirm main.py is exactly 4096 bytes long, standard library only. It makes no network requests and calls no model during play.

## Reproducing the practice numbers

Run the practice suite from the competition kit and record the spare plies and the Elo for each pass.

Three passes should come out close to 917, 883, and 881 spare plies, averaging about 893.7, with Elo 2112 and 18 wins out of 18 games.

## Reproducing the custom scenarios

Run the custom scenario set from the kit. Expect Elo 2112, eight wins and no losses, with 1172 spare plies.

## Determinism

Run the practice suite twice and compare move for move. Both passes must be identical: the engine is fully deterministic.

## Instance suite

The instance check should return 1669, and repeating it should return 1669 again.
