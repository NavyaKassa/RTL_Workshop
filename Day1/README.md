# **Introduction to iVerilog, Design and Test Bench**

## 1. What is Simulator, Design & Test Becnch?

### Simulator:
A simulator is a software tool that models the behavior of a digital circuit described in HDL (Hardware Description Language) like Verilog or VHDL, and allows designers to verify if the logic works as intended.

### Design:
The design is the Verilog code (or group of Verilog files) that captures the intended behavior of the digital system, created to fulfill the defined requirements.

### TestBench:
A testbench in Verilog is a simulation environment used to verify the correctness of a digital design (also called the DUT – Design Under Test).
The main goal of a testbench is to stimulate the design and observe its output.
Unlike the actual design code, a testbench:

- Is not synthesized (i.e., it will never become hardware)

- Is only used for simulation and verification

