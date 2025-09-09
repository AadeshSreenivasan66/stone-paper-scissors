

# Stone-Paper-Scissors Game Logic
A TinyTapeout-compliant digital game module that implements a two-player Stone-Paper-Scissors match with move evaluation, winner detection, reset functionality, and debug output.

## Features
Supports two players selecting from Stone, Paper, or Scissors.
Detects ties, invalid moves, and winners.
Operates through three states: Idle, Evaluate, Result.
Outputs winner, game state, and debug information in real-time.

## I/O Mapping
## Inputs (ui_in)
| Bit | Name         | Description                       |
| --- | ------------ | --------------------------------- |
| 0   | `p1_move[1]` | Player 1’s move, bit 1 (MSB)      |
| 1   | `p1_move[0]` | Player 1’s move, bit 0 (LSB)      |
| 2   | `p2_move[1]` | Player 2’s move, bit 1 (MSB)      |
| 3   | `p2_move[0]` | Player 2’s move, bit 0 (LSB)      |
| 4   | `start`      | Start signal to evaluate the game |
| 5   | `mode`       | Reserved for future use           |
| 6   | `reset`      | Active-high reset signal          |
| 7   | —            | Unused                            |

## Outputs (uo_out)
| Bit | Name        | Description                    |
| --- | ----------- | ------------------------------ |
| 0   | `winner[1]` | Match result, bit 1 (MSB)      |
| 1   | `winner[0]` | Match result, bit 0 (LSB)      |
| 2   | `state[2]`  | Current state, bit 2 (MSB)     |
| 3   | `state[1]`  | Current state, bit 1           |
| 4   | `state[0]`  | Current state, bit 0 (LSB)     |
| 5   | `debug[2]`  | Debug information, bit 2 (MSB) |
| 6   | `debug[1]`  | Debug information, bit 1       |
| 7   | `debug[0]`  | Debug information, bit 0 (LSB) |
