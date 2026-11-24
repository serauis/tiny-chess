# How to verify V6

Checks anyone can run to confirm the numbers in README.md, using only the files in this repository.

## Size and shape

Confirm main.py is exactly 4096 bytes, standard library only, with no network requests and no model calls during play.

## Reproducing the practice numbers

Run the practice suite from the competition kit and record spare plies and Elo per pass.

Three passes should come out close to 917, 883, and 881 spare plies (average about 893.7), Elo 2112, 18 wins out of 18 games.

## Reproducing the custom scenarios

Run the custom scenario set from the kit: expect Elo 2112, eight wins, no losses, 1172 spare plies.

## Determinism

Run the practice suite twice and compare move for move; both passes must be identical.

## Instance suite

The instance check should return 1669, twice in a row.
