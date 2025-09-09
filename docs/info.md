<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works
The design uses four main states to control the game:
State Name	Binary Code	Description
S_IDLE	000	Waiting for the start signal.
S_EVALUATE	001	Evaluates the moves of both players.
S_RESULT	010	Displays the result (Winner, Tie, or Invalid).
S_RESET	011	Resets the game back to the idle state.
The module continuously monitors player inputs.
When start = 1, the FSM moves from S_IDLE → S_EVALUATE → S_RESULT.
The output winner shows the game result.
The FSM stays in S_RESULT until start = 0, which returns it to S_IDLE.

## How to test
Setup
Load the Verilog design into a simulator such as:
Icarus Verilog, ModelSim, or Vivado.
Connect appropriate clock and reset signals.
Steps
Apply reset = 1 for at least one clock cycle to initialize the FSM.
Set reset = 0.
Provide valid moves to p1_move and p2_move.
Set start = 1 to evaluate moves.
Observe winner and debug outputs.
Set start = 0 to return to S_IDLE.

