# riscv-rv32i-cpu

A RISC-V RV32I CPU written in SystemVerilog that evolves from a simple single-cycle core into a pipelined, speculative, and eventually out-of-order microarchitecture.

This project is intended to be a clean, modular sandbox for experimenting with modern CPU architecture concepts.

---

## Goals

- Educational, readable SystemVerilog
- Clear separation of stages (single-cycle -> in-order pipeline -> OoO)
- Modular components (ALU, register file, branch unit, ROB, RS, etc.)
- Easy to simulate and extend

## Non-goals (for now)

- Maximum clock frequency / timing closure on advanced nodes
- Full RISC-V privilege modes and MMU
- Full RISC-V ISA extensions beyond RV32I (may be added later)

---

## Planned Evolution

The core will evolve in several stages:

1. **Single-cycle RV32I core**
   - Simple memory interface
   - Pass basic RISC-V ISA tests

2. **In-order pipelined core**
   - 5-stage pipeline (IF/ID/EX/MEM/WB)
   - Hazard detection and forwarding
   - Basic branch handling (flush on mispredict)

3. **Speculative in-order core**
   - Branch prediction
   - Simple instruction and data caches (or cache-like interfaces)

4. **Out-of-order core**
   - Scoreboarding and Tomasulo’s algorithm
   - Register renaming
   - Reservation stations
   - Reorder Buffer (ROB) for in-order commit
   - Multi-issue / superscalar dispatch
   - More advanced speculative execution

Additional features may be added as the architecture evolves.

## Status

- [ ] Single-cycle core
- [ ] In-order pipeline
- [ ] Hazard detection and forwarding
- [ ] Branch prediction
- [ ] Caches
- [ ] OoO backend (ROB + RS + renaming)
- [ ] Multi-issue
