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

<h2>Example Output</h2>
<p align="center">
  <img src="Screenshot%202025-07-31%20093933.png" alt="Waveform Screenshot" width="800">
</p>



