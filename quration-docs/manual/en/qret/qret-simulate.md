% QRET-SIMULATE(1) Quration User Manuals

# NAME

qret simulate - Simulate a function in an IR file.

# SYNOPSIS

**qret simulate** {`-i` | `--input`} *PATH* [`-f`, `--function` *ARG*] [`-s`, `--state` *ARG*] [`--init_state arg`] [`--seed` *ARG*] [`-n`, `--num_samples` *ARG*] [`--sample_summary`] [`--print_raw`] [`--use_qulacs`] [`--max_superpositions` *ARG*]
             [`--quiet` | `--verbose` | `--debug`] [`--color`]
             [`-h` | `--help`]

# DESCRIPTION

**qret simulate** Runs the instruction of the input circuit to verify its correctness. As, this is simulating a quantum circuit on a classical computer, the number of qubits and circuit size will be limited to the host computer.

# OPTIONS

`-h`, `--help`
: Print a brief summary of command line arguments.

`--quiet`
: Suppress non-error output.

`--verbose`
: Enable verbose logging (prints more details than the default behavior).

`--debug`
: Enable debug logging (prints more details than verbose; implies `--verbose`).

`--color`
: Enable colored output.

`-i`, `--input` *PATH*
: **Required.** Path to the input circuit in the intermediate representation.

`-f`, `--function` *ARG*
: Function name to simulate.

`-s`, `--state` *ARG*
: Simulation model. Allowed values: FullQuantum, Toffoli. Aliases: full|fullquantum for FullQuantum, tof for Toffoli. (Default: `FullQuantum`)

`--init_state arg`
: Initial state as binary string for all circuit qubits. The first char is q0, second is q1, ... (LSB-first). E.g. `--init_state 0101`` means q0=0, q1=1, q2=0, q3=1. Whitespace and '_' are ignored; 0b prefix is accepted. Empty means all zeros.

`--seed` *ARG*
: Seed for the first run. For repeated runs, this value is incremented by 1 each time. (Default: `1`)

`-n`, `--num_samples` *ARG*
: Number of simulation runs. Seeds are changed for each run using `seed + run_index`. If omitted and --print_raw is not set for FullQuantum, defaults to 10. (Default: `0`)

`--sample_summary`
: Output only sampling summary (FullQuantum only).

`--print_raw`
: For FullQuantum: print expanded state vector. For Toffoli, raw state is shown.

`--use_qulacs`
: When using `FullQuantum`, uses Qulacs backend if available.

`--max_superpositions` *ARG*
: When `Toffoli` simulation. The maximum number of superpositions allowed during simulation. (Default: `1`)

# EXAMPLES

Profile a circuit using default settings:

```bash
qret simulate --input <ir-file> --function <name>
qret simulate --input <ir-file> --function <name> --state Toffoli --max_superpositions 16 --init_state 0101 --num_samples 8
qret simulate --input <ir-file> --function <name> --state FullQuantum --print_raw
```
