# MIPS Pipeline Simulator

A C++ simulation of a five-stage MIPS processor pipeline. The program reads a file of MIPS assembly instructions, converts them to binary, and executes them through a simulated pipeline. Three versions are included, each building on the previous with additional architectural features.

---

## How It Works

1. The simulator reads a MIPS assembly input file
2. Instructions are parsed and converted to binary representation
3. Each instruction is passed through a five-stage pipeline: **IF → ID → EX → MEM → WB**
4. The simulator outputs log files tracking:
   - Each instruction and its clock cycle at every pipeline stage
   - Memory contents in binary
   - Register values after execution

---

## Pipeline Versions

| Version | Features |
|---|---|
| **Version 1** | Basic pipeline — no cache, no hazards, single EX stage, no branching |
| **Version 2** | Adds branching, hazard detection, and data forwarding |
| **Version 3** | Adds multi-stage EX (for instructions requiring multiple execution cycles) |

Each version is contained in its own folder and can be built and run independently.

---

## Prerequisites

- A C++ compiler supporting C++11 or later (e.g. `g++`)
- `make` (for building via the provided Makefile)

---

## Building & Running

Navigate into the version folder you want to run:

```bash
cd MIP_Simulator_Version1   # or Version2 / Version3
```

**Build with make:**

```bash
make
```

**Or compile manually:**

```bash
g++ -o simulator simulator.cpp
```

**Run the simulator:**

```bash
./simulator <input_file>
```

Where `<input_file>` is a text file containing MIPS assembly instructions, one per line.

---

## Output Files

After execution, the simulator produces output files including:

- **Pipeline log** — lists each instruction and the clock cycle it occupied at each stage (IF, ID, EX, MEM, WB)
- **Memory dump** — the contents of memory in binary format
- **Register dump** — the final state of all registers after the program completes

---

## Supported Instructions

The simulator supports a reduced 32-bit MIPS ISA subset typical of CMSC 411, including R-type, I-type, and branch/jump instructions, as well as a `HALT` instruction that terminates the simulation.

---

## Tech Stack

| Component | Detail |
|---|---|
| Language | C++ |
| Build Tool | Makefile |
| Architecture | 32-bit MIPS ISA |
| Pipeline | 5-stage (IF, ID, EX, MEM, WB) |
