% QRET(1) Quration User Manuals

# NAME

qret - The quration tool

# SYNOPSIS

**qret** `[-h | --help]` `[-v | --version]` `<command>` `[<args>]`

# DESCRIPTION

**qret** Quration is a quantum circuit resource estimation tool. It can also compile, simulate, and visualize quantum circuits.

# OPTIONS

`-h`, `--help`
: Print a brief summary of command line arguments.

`-v`, `--version`
: Print the release version of Quration.

# Commands

**qret-help**(1)
: Alias for `--help`

**qret-version**(1)
: Alias for `--version`

**qret-asm**(1)
: TODO

**qret-compile**(1)
: Takes a circuit in the intermediate representation, along with a description of the target system, and compiles it down to low-level instructions for that target chip.

**qret-diagram**(1)
: Visualize the input circuit in a multiple diagram

**qret-opt**(1)
: Optimize the input circuit by providing various optimization passes.

**qret-parse**(1)
: Converts the Quration intermediate representation into either OpenQASM2 or (a subset of) OpenQASM3.

**qret-print**(1)
: Displays information and instruction of an input circuit.

**qret-profile**(1)
: Estimation tool for fault-tolerant quantum computing (FTQC), which reports the code distance required to run under a certain logical error level.

**qret-simulate**(1)
: Runs the instruction of the input circuit to verify its correctness.
