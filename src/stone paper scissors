module stone_paper_scissors (
    input wire [1:0] p1_move,  // Player 1 move
    input wire [1:0] p2_move,  // Player 2 move
    output reg [1:0] winner   // 00 = Tie, 01 = P1 wins, 10 = P2 wins, 11 = Invalid
);

always @(*) begin
    case ({p1_move, p2_move})
        // Tie conditions
        4'b0000,  // Stone vs Stone
        4'b0101,  // Paper vs Paper
        4'b1010:  // Scissors vs Scissors
            winner = 2'b00; // Tie

        // Player 1 wins
        4'b0001,  // Stone vs Paper -> P2 wins
        4'b0010,  // Stone vs Scissors -> P1 wins
        4'b0100,  // Paper vs Stone -> P1 wins
        4'b0110,  // Paper vs Scissors -> P2 wins
        4'b1000,  // Scissors vs Stone -> P2 wins
        4'b1001:  // Scissors vs Paper -> P1 wins
            begin
                if ((p1_move == 2'b00 && p2_move == 2'b10) || // Stone beats Scissors
                    (p1_move == 2'b01 && p2_move == 2'b00) || // Paper beats Stone
                    (p1_move == 2'b10 && p2_move == 2'b01))   // Scissors beats Paper
                    winner = 2'b01; // Player 1 wins
                else
                    winner = 2'b10; // Player 2 wins
            end

        // Invalid or not covered
        default: winner = 2'b11;
    endcase
end

endmodule
