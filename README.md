Max-Pooling Hardware <br>
 AcceleratorA high-performance, synthesizable 2x2 Max-Pooling accelerator designed for FPGAs, utilizing Q8.8 fixed-point arithmetic for efficient real-time data processing. <br>
 Key Features <br>
 Hierarchical RTL Design: Implements a 4-input comparator tree for low-latency parallel processing.Moore FSM Controller: Robust 3-state control logic (LOAD $\rightarrow$ COMPARE $\rightarrow$ OUTPUT) for deterministic operation.v  <br>
 Q8.8 Fixed-Point Arithmetic: Optimized for area and throughput, suitable for digital signal processing (DSP) applications. <br>
 Automated Verification: File-driven testbench with automated test-vector injection and error-checking. <br>
 Tech Stack <br>
 Language: Verilog (IEEE 1364) <br>
 Design Methodology: RTL, FSM, Datapath-Controller <br>
  partitioningSimulation: Icarus Verilog / ModelSim (compatible) <br>
  Project Structure <br>
  emaxpool.v: Top-level module wrapper. <br>
  maxpool_controller.v: Moore state machine for cycle scheduling. <br>
  maxpool_datapath.v: Data registers, comparator tree, and output truncation logic. <br>
  cmp_tree.v: Hierarchical comparator tree.cmp2.v: Base 2-input magnitude comparator. <br>
  tb_maxpool.v: Automated testbench with external input.txt support. <br>
  Getting Started <br>
  Clone the repository: git clone https://github.com/sachinranga378-svg/engineering-task-log.git <br>
  Setup: Ensure your FPGA synthesis tool (Vivado/Quartus/Yosys) is installed. <br>
  Simulation:Create an input.txt file with four values per line (decimal format). <br>
  Run the testbench: iverilog -o sim tb_maxpool.v maxpool.v maxpool_controller.v maxpool_datapath.v cmp_tree.v cmp2.v <br>
  Execute: vvp sim <br>
  Synthesis: Import the top-level maxpool.v into your design environment to generate the netlist.