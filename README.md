

# Stone-Paper-Scissors Game Logic
A TinyTapeout-compliant digital game module that implements a two-player Stone-Paper-Scissors match with move evaluation, winner detection, reset functionality, and debug output.

## Features
Supports two players selecting from Stone, Paper, or Scissors.
Detects ties, invalid moves, and winners.
Operates through three states: Idle, Evaluate, Result.
Outputs winner, game state, and debug information in real-time.

## I/O Mapping
## Inputs (ui_in)
| Bits   | Name     | Description                                                           |
| ------ | -------- | --------------------------------------------------------------------- |
| \[1:0] | p1\_move | Player 1’s move (00 = Stone, 01 = Paper, 10 = Scissors, 11 = Invalid) |
| \[3:2] | p2\_move | Player 2’s move (same encoding)                                       |
| \[4]   | start    | Start signal to evaluate the match                                    |
| \[5]   | mode     | Reserved for future use                                               |
| \[7:6] | –        | Unused                                                                |

## Outputs (uo_out)
| Bits   | Name   | Description                                                       |
| ------ | ------ | ----------------------------------------------------------------- |
| \[2:0] | state  | Current state of the FSM                                          |
| \[4:3] | winner | Match result (00 = Tie, 01 = P1 wins, 10 = P2 wins, 11 = Invalid) |
| \[7:5] | debug  | Debug information based on player moves                           |
