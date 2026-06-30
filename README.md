Max-Pooling Hardware
 AcceleratorA high-performance, synthesizable 2x2 Max-Pooling accelerator designed for FPGAs, utilizing Q8.8 fixed-point arithmetic for efficient real-time data processing.
 Key Features
 Hierarchical RTL Design: Implements a 4-input comparator tree for low-latency parallel processing.Moore FSM Controller: Robust 3-state control logic (LOAD $\rightarrow$ COMPARE $\rightarrow$ OUTPUT) for deterministic operation.
 Q8.8 Fixed-Point Arithmetic: Optimized for area and throughput, suitable for digital signal processing (DSP) applications.
 Automated Verification: File-driven testbench with automated test-vector injection and error-checking.
 Tech Stack
 Language: Verilog (IEEE 1364)
 Design Methodology: RTL, FSM, Datapath-Controller
  partitioningSimulation: Icarus Verilog / ModelSim (compatible)
  Project Structur
  emaxpool.v: Top-level module wrapper.
  maxpool_controller.v: Moore state machine for cycle scheduling.
  maxpool_datapath.v: Data registers, comparator tree, and output truncation logic.
  cmp_tree.v: Hierarchical comparator tree.cmp2.v: Base 2-input magnitude comparator.
  tb_maxpool.v: Automated testbench with external input.txt support.
  Getting Started
  Clone the repository: git clone https://github.com/sachinranga378-svg/engineering-task-log.git
  Setup: Ensure your FPGA synthesis tool (Vivado/Quartus/Yosys) is installed.
  Simulation:Create an input.txt file with four values per line (decimal format).
  Run the testbench: iverilog -o sim tb_maxpool.v maxpool.v maxpool_controller.v maxpool_datapath.v cmp_tree.v cmp2.v
  Execute: vvp sim
  Synthesis: Import the top-level maxpool.v into your design environment to generate the netlist.