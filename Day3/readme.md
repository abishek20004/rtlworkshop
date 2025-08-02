# Day 3: Combinational and Sequential Optimization Labs

This repository demonstrates key Verilog lab experiments focused on FSM optimization, logic simplification, and power-saving techniques.

---

```verilog
// -----------------------------------------------------
// Day 3: Combinational and Sequential Optimization Labs
// FSM Optimization | Logic Simplification | Power Saving
// -----------------------------------------------------

// ----------------------------------------------
// Lab 1: Conditional assignment with zero output
// Description: Outputs 'b' when a=1; else outputs 0
// ----------------------------------------------
module opt_check1(input a, input b, output y);
    assign y = a ? b : 0;
endmodule

// -------------------------------------------------
// Lab 2: Conditional assignment with constant 1
// Description: Outputs 1 when a=1; else outputs 'b'
// -------------------------------------------------
module opt_check2(input a, input b, output y);
    assign y = a ? 1 : b;
endmodule

// --------------------------------------------------------------------
// Lab 4: Nested conditional (ternary) logic using three inputs
// Description: Complex combinational decision using ternary operator
// --------------------------------------------------------------------
module opt_check4(input a, input b, input c, output y);
    assign y = a ? (b ? (a & c) : c) : (!c);
endmodule

// -----------------------------------------------------
// Lab 5: D Flip-Flop with asynchronous reset to 0
// Description: On reset, output goes to 0; else always 1
// -----------------------------------------------------
module dff_const1(input clk, input reset, output reg q);
    always @(posedge clk or posedge reset)
    begin
        if (reset)
            q <= 1'b0;
        else
            q <= 1'b1;
    end
endmodule

// ---------------------------------------------------------
// Lab 6: D Flip-Flop with constant output 1
// Description: Output is always 1, regardless of reset/clock
// ---------------------------------------------------------
module dft_const2(input clk, input reset, output reg q);
    always @(posedge clk or posedge reset)
    begin
        if (reset)
            q <= 1'b1;
        else
            q <= 1'b1;
    end
endmodule

