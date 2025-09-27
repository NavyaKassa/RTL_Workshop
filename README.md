# 🏗️ RISC-V Reference SoC Tapeout Program – Week 1  
Welcome to the RTL Workshop, a hands-on learning series focused on Verilog RTL design, simulation, synthesis, and digital circuit optimization. This repository also serves as a record of my Week-1 learnings from the RISC-V Reference SoC Tapeout Program.

---

## 📚 About This Repository
This repository is intended for students, hobbyists, and engineers who want to learn about:

- Verilog RTL design and simulation
- Logic synthesis and optimization techniques
- Gate-level simulation (GLS) and Synthesis-Simulation Mismatch (SSM)
- Efficient flip-flop coding styles and combinational/sequential optimizations
- Using open-source tools like **Icarus Verilog**, **GTKWave**, **Yosys**, and **Sky130 PDK**

---

## 🛠 Tools Used
- **iverilog** – RTL simulation
- **GTKWave** – Waveform visualization
- **Yosys** – Logic synthesis
- **Sky130 PDK** – Open-source process design kit

---

## 📝 Prerequisites
- Basic understanding of digital logic (gates, flip-flops, multiplexers)
- Familiarity with Linux shell commands
- A Linux environment (or WSL on Windows/macOS)
- Tools: git, iverilog, gtkwave, yosys, and a text editor

---

## 📅 Workshop / Week-1 Structure


### Week-1 / Day-wise Topics

| Day | Topic |
|-----|-------|
| Day 1 | [Introduction to Verilog RTL Design and Synthesis](./Day_1) |
| Day 2 | [Timing Libraries and Efficient Flop Coding Styles](./Day_2) |
| Day 3 | [Combinational and Sequential Optimizations](./Day_3) |
| Day 4 | [Gate Level Simulation & Synthesis-Simulation Mismatch](./Day_4) |
| Day 5 | [Advanced Synthesis and Optimization](./Day_5) |


Each day folder contains:
- `README.md` – Summary of concepts learned along with lab exercises.
- `Images/` – All images files of Simulation and Synthesis for designs.

---

## 💡 Key Concepts (Week-1 Highlights)

- **Timing Libraries**: PVT variations ensure reliable operation; guide synthesis & timing analysis.  
- **Hierarchical vs Flat Synthesis**: Hierarchical → modular, reusable; Flat → optimized for speed/area.  
- **Flip-Flop Coding Styles**: Use synchronous resets by default; async resets for exceptional cases.  
- **Combinational Optimization**: Logic squeezing, constant propagation, Boolean simplification (K-map, Quine-McCluskey).  
- **Sequential Optimization**: Sequential constant propagation, state optimization, cloning, retiming.  
- **GLS & SSM**: Gate-level simulation validates netlist functionality; avoid synthesis-simulation mismatches with synthesizable RTL.  
- **Verilog Constructs**: Correct use of if-else, case, for loops, generate blocks; avoid inferred latches.  
- **RCA (Ripple Carry Adder)**: Full adders chained; carry ripples through stages.

---

## 📌 Setup Instructions
For detailed installation steps of tools (iverilog, GTKWave, Yosys, Sky130 PDK), refer to the [Tools Installation Guide]([tools/INSTALL.md](https://github.com/NavyaKassa/RISC-V-SoC-Tapeout-Program_VSD/blob/main/Week0/Task2_Tools%20Installation.md)).

---

