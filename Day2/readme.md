# 📅 Day 2 Summary

## 🧠 Topics Covered

---

### 🕒 Timing Library
- A **Timing Library** provides information on **delay, power, and functionality** of standard cells.
- Used for **Static Timing Analysis (STA)** and synthesis processes in IC design.

---

### 🏗️ SKY130PDK
- **SKY130PDK** is an **open-source Process Design Kit (PDK)**.
- Based on **SkyWater Technologies' 130 nm CMOS** node.
- Supports IC design tasks including:
  - Timing
  - Power estimation
  - Process-aware layout and verification

> ✅ **Summary**: SKY130PDK plays a crucial role in enabling open-source IC design with reliable timing and process support.

---

### 🧱 Hierarchical vs Flattened Synthesis

| Feature           | Hierarchical                        | Flattened                      |
|-------------------|--------------------------------------|--------------------------------|
| Structure         | Maintains RTL module hierarchy       | Combines all into one netlist  |
| Readability       | Easier to debug                      | Harder to trace                |
| Compilation Time  | Faster (per module)                  | Slower                         |
| Optimization      | Limited across modules               | Global optimization possible   |

> ✅ **Summary**: Hierarchical design is easier to manage, while flattened synthesis allows for aggressive optimizations at the cost of readability.

---

### 🔁 Flip-Flop Coding Styles

- **Asynchronous Reset**:  
  - Reset signal has **priority over the clock**.  
  - Design resets the output **immediately** when reset is asserted.
  
- **Edge Triggering (Clocked Logic)**:  
  - Sensitive to **rising/falling edge** of the clock signal.
  - Used for **sequential logic** and flip-flops.

```verilog
always @(posedge clk or posedge reset) begin
  if (reset)
    q <= 1'b0;
  else
    q <= d;
end

