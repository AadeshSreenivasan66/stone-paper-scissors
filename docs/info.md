<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->
## How it works
This module simulates the Stone-Paper-Scissors game by interpreting moves from two players and determining the winner based on game rules:
Input Interpretation:
The module reads ui_in to extract the moves of Player 1 and Player 2.
Each move is encoded in 2 bits:
00: Stone
01: Paper
10: Scissors
11: Invalid

Finite State Machine (FSM):
Idle State: Waits for the start signal.
Evaluate State: Compares the moves and determines the outcome.
Result State: Holds the result until the next start or reset.

Game Rules Application:
If either player selects an invalid option (11), the result is marked invalid.
If both players choose the same option, the result is a tie.
Otherwise, the winner is determined by the standard rules:
Stone beats Scissors.
Paper beats Stone.
Scissors beats Paper.
Output Encoding:
The result is sent through uo_out, where:
3 bits represent the current state.
2 bits represent the winner.
3 bits represent debug information (partial move data).
Reset and Enable Logic:
A reset initializes the game state and clears outputs.

## How to test
Initialize signals:
rst_n = 0, ena = 1, ui_in = 0.

Reset the module:
Hold rst_n = 0 for a few cycles.
Then set rst_n = 1.

Test Case 1 – Player 1 wins:
Set ui_in = 8'b00001000
→ p1_move = 00 (Stone)
→ p2_move = 10 (Scissors)
→ start = 1
Run for a few cycles and check that uo_out shows winner = 01 (Player 1 wins).

Test Case 2 – Tie:
Set ui_in = 8'b00000000
→ p1_move = 00 (Stone)
→ p2_move = 00 (Stone)
→ start = 1
Check that winner = 00 (Tie).

Test Case 3 – Invalid move:
Set ui_in = 8'b00111000
→ p1_move = 11 (Invalid)
→ p2_move = 10 (Scissors)
→ start = 1
Check that winner = 11 (Invalid).
