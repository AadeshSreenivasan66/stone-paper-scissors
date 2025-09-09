<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works
This project implements the Stone-Paper-Scissors game using Verilog. Each player selects a move using two input bits (00 = Stone, 01 = Paper, 10 = Scissors). The circuit compares the moves and outputs the winner:
00: Tie
01: Player 1 wins
10: Player 2 wins
11: Invalid input
The output updates instantly when inputs change.

## How to test
Run the simulation in Wokwi.
Use switches ui[0–1] for Player 1 and ui[2–3] for Player 2 to set moves.
Check uo[0–1] for the result: Tie, Player 1 wins, Player 2 wins, or invalid input.
Try different combinations to verify the game logic.
