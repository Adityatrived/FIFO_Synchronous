# 🔄 Synchronous FIFO Design in Verilog

A fully parameterized **Synchronous FIFO (First-In First-Out)** memory buffer built using Verilog, featuring a robust and self-checking testbench for functional simulation and waveform analysis.

---

## 🔧 Overview

This project demonstrates a hardware-accurate FIFO design, ideal for FPGA/ASIC workflows. The design supports:

- **Circular buffer implementation**
- **Pointer-based full/empty flag generation**
- **Synchronous read/write operations**
- **Self-verifying testbench logic**

Both the core module and the testbench are written with synthesis and simulation best practices in mind.

---

## 📐 FIFO Features

| Feature       | Description                                      |
|---------------|--------------------------------------------------|
| `DEPTH`       | FIFO depth — configurable via parameter          |
| `DATA_WIDTH`  | Data bit-width — configurable via parameter      |
| Full/Empty    | Determined using pointer MSBs                    |
| Clock Domain  | Operates on a single synchronous clock           |
| Reset Logic   | Asynchronous reset support                       |

---

## 🧪 Testbench Highlights

- Generates randomized `data_in` using `$random`
- Alternates write/read operations under valid conditions
- Compares each `data_out` with expected reference values
- Dumps all signals to `dump.vcd` for waveform analysis
- Uses **EPWave** for clean visual debugging

---

## ✅ Simulation Results

The design passes all functional checks with:

- ✔️ Matching `data_in` and `data_out`
- ✔️ Accurate full and empty flag transitions
- ✔️ Consistent operation under edge conditions

Waveforms can be visualized using [EPWave Viewer](https://epwave.org/) or via GTKWave locally.

---

## ▶️ How to Simulate

You can simulate the project online via [EDAPlayground](https://www.edaplayground.com/):

1. Paste the Verilog source and testbench
2. Choose `Icarus Verilog` as the simulator
3. Run simulation and open `dump.vcd` in EPWave

Or simulate locally using:

```bash
iverilog -o fifo_tb fifo.v fifo_tb.v
vvp fifo_tb
gtkwave dump.vcd

