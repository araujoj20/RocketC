# RocketC

RocketC is a C-to-VeSPA toolchain project.

It compiles C code into VeSPA assembly, includes a dedicated assembler, and provides supporting tooling (instruction scheduling and simulation) to validate generated programs.

## Project Scope

Based on the project report in `RocketC.pdf`, RocketC covers:

- Frontend: lexical, syntactic, and semantic analysis
- Middle/Backend: code generation for VeSPA ISA
- Optimizations: high-level and low-level strategies
- Assembler: assembly to machine/memory-ready formats
- Simulation support: execution validation with the VeSPA simulator

## Repository Layout

- `Compiler/`: C compiler (lexer, parser, semantic analysis, optimizations, codegen)
- `Assembler/`: assembler for VeSPA assembly
- `Instruction Scheduler/`: low-level instruction scheduling utilities
- `Simulator/`: execution/simulation environment for VeSPA code
- `RocketC.pdf`: full project documentation

## Quick Start

### 1) Build the C compiler

```bash
cd Compiler && make all
./Output/RocketC TestCodeGen.c --parse
```

Compiler output includes VeSPA assembly in `Compiler/Output/Rocket.asm`.

### 2) Build the assembler

```bash
cd Assembler && make all
./Output/VASM test.asm --parse
```

Assembler output is generated under `Assembler/Output/`.

## Typical Flow

1. Compile C source to VeSPA assembly (RocketC compiler).
2. Assemble VeSPA assembly to machine-oriented output.
3. Optionally apply instruction scheduling.
4. Validate behavior with the simulator.

## Notes

- The most complete technical explanation is in `RocketC.pdf`.
- Subproject-specific details are also available in:
  - `Compiler/README.md`
  - `Assembler/README.md`
