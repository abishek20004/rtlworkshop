# rtlworkshop

## RTL Design and Synthesis Workshop using sky130

### Day-1: Introduction to Verilog Design & Synthesis

---

## 🛠️ Simulator

A **simulator** is an EDA tool used to check the functionality of digital circuits. It applies test inputs to a design and verifies the output before hardware implementation.

---

## 🧠 Design

The logic is described using **Verilog code**, capturing the functional behavior of the circuit.

### 2:1 Multiplexer Verilog Code

```verilog
module good_mux (input i0, input i1, input sel, output reg y);
    always @(*) begin
        if (sel)
            y <= i1;
        else
            y <= i0;
    end
endmodule

---

### Testbench
````timescale 1ns / 1ps

module tb_good_mux;
    // Inputs
    reg i0, i1, sel;
    // Outputs
    wire y;

    // Instantiate the Unit Under Test (UUT)
    good_mux uut (
        .sel(sel),
        .i0(i0),
        .i1(i1),
        .y(y)
    );

    initial begin
        $dumpfile("tb_good_mux.vcd");
        $dumpvars(0, tb_good_mux);

        // Initialize Inputs
        sel = 0; i0 = 0; i1 = 0;
        #300 $finish;
    end

    always #75 sel = ~sel;
    always #10 i0 = ~i0;
    always #55 i1 = ~i1;
endmodule

---
Design Flow

[ Verilog Design ]        [ Testbench ]
        ↓                      ↓
      Icarus Verilog (iverilog)
        ↓
    Simulation Output (vvp)
        ↓
   Waveform File (tb_good_mux.vcd)
        ↓
        GTKWave (Waveform Viewer)







