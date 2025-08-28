# deMUX1to4 VHDL Project

## Project Overview
This project implements a **1-to-4 demultiplexer** in VHDL. The demux has:
This project is **synthesizable** and suitable for **Synopsys tools**, and simulation is done using **ModelSim**.
- **Inputs:**  
  - `D` : 1-bit data input  
  - `S` : 2-bit select lines  

- **Outputs:**  
  - `O1, O2, O3, O4` : 1-bit outputs, where only one is active based on `S`  

This project is part of my VHDL learning roadmap, aimed at building **100 VHDL projects** and preparing for Synopsys-oriented verification/design work.



## Files in this Project
| File | Description |
|------|-------------|
| `deMUX1to4.vhd` | VHDL implementation of the 1-to-4 demux |
| `deMUX1to4_tb.vhd` | Testbench to verify functionality |
| `deMUX1to4.mpf` | ModelSim project file |
| `vsim.wlf` | ModelSim waveform file |
| `.vscode/` | VS Code settings |



## How to Simulate in ModelSim

1. Open ModelSim.  
2. Navigate to the project folder.  
3. Compile the design and testbench:
   ```tcl
   vcom deMUX1to4.vhd
   vcom deMUX1to4_tb.vhd

4. Run the simulation:
   ```tcl
   vsim work.deMUX1to4_tb
   add wave *
   run 14ns
   ```
5. Observe the waveforms for `O1..O4` to ensure correct demux behavior.



## Test Results

| D | S  | O1 | O2 | O3 | O4 | Pass/Fail |
|---|----|----|----|----|----|-----------|
| 0 | 00 | 0  | 0  | 0  | 0  |  Pass ✅  |
| 0 | 01 | 0  | 0  | 0  | 0  |  Pass ✅  |
| 0 | 10 | 0  | 0  | 0  | 0  |  Pass ✅  |
| 0 | 11 | 0  | 0  | 0  | 0  |  Pass ✅  |
| 1 | 00 | 1  | 0  | 0  | 0  |  Pass ✅  |
| 1 | 01 | 0  | 1  | 0  | 0  |  Pass ✅  |
| 1 | 10 | 0  | 0  | 1  | 0  |  Pass ✅  |
| 1 | 11 | 0  | 0  | 0  | 1  |  Pass ✅  |



## Notes
- This project uses a **process with a `case` statement**, which is a Synopsys-friendly style for combinational logic.  
- Default output assignments are included to **avoid latches**.  
- This project is ready to push to GitHub and be reused as a **building block for larger VHDL projects**, including CPUs and SoCs.

---

## License
This project is released under the **MIT License**. See [`LICENSE`](LICENSE) for details.
