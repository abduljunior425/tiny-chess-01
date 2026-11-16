# Tests

This engine is a single-file program. It talks to the game server
over HTTP, reads a position and its legal moves, searches, and
replies with one move in UCI form.

## Search

The board uses the 0x88 layout, so an off-board square is caught by
a single bit test. The search is negamax with alpha-beta windows,
deepened one ply at a time until the fixed node budget for the move
is spent. Captures are followed further in quiescence, so no move
is judged while a trade is still hanging. A transposition table
keeps positions that were already searched, two killer moves per
ply plus a history table order the quiet moves, and null-move
pruning skips a turn to show a position is already good enough.
A position that gives check is searched one ply deeper. The
evaluation adds material values to piece-square tables. A small
helper answers whether the side to move is in check; both the
main search and quiescence call it instead of repeating the test.

## Trial

The packed entry played six practice games against the house
gauntlet and took three points out of six, which the scoring
script maps to a practice Elo of 1279. The bar to reach the
final is 1154, so the entry clears it, though it stays below
the house baseline near 1365.

## Running the trial

Pick a practice gauntlet folder from the kit and run the trial
script with that folder, a free port, and the packed entry file.
The script starts a local game server, plays all six games, and
prints the points and the Elo at the end. A full trial takes
about a quarter of an hour on this machine, because every move
is searched to the fixed node budget. Perft and strength checks
live beside the engine sources and can be run directly with
Python.
