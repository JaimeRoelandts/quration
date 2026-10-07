% CREATE_MULTI_CONTROLLED_MOD_BI_MUL_IMM(1) Quration User Manuals

# NAME

create_multi_controlled_mod_bi_mul_imm - Generate a Quration IR JSON circuit for a modular bimultiply of two input values, provided a multiplier and modulus. 

# SYNOPSIS

**create_multi_controlled_mod_bi_mul_imm** `--input` *PATH* `--output` *PATH* `[--inline]` `[--help]`

# DESCRIPTION

**create_multi_controlled_mod_bi_mul_imm** creates a circuit to calculate the modular bimultiply for two values. This takes `(x,y)`, a multiplier `K`, and modulus `N` as input, and calculates `(xK, yK^-1) (mod N)` using several control qubits. Both `N` and `K` need to be specified as constants to the circuit.
The resulting output is written as a JSON file in the Quration Intermediate Representation (IR).

# OPTIONS

`--help`
: Print a brief summary of command line arguments.

`--input` *PATH*
: **Required.** Path to an input JSON file containing parameters to generate the circuit.

`--output` *PATH*
: **Required.** Path where the output circuit JSON file will be written.

`--inline`
: *Optional.* Perform an optimization pass to recursively inline call instructions.

# INPUT SCHEMA

The input JSON file must specify the following parameter:

`modulus` (*integer*)
: The modulus `N`

`multiplier` (*integer*)
: The multiplier `k`

`num_control_qubits` (*integer*)
: The number of control qubits

`num_system_qubits` (*integer*)
: Number of qubits to represent binary digits during calculations

# EXAMPLES

Given an input file `config.json`:

```json
{
  "modulus": "15",
  "multiplier": "2",
  "num_control_qubits": 1,
  "num_system_qubits": 4
}
```
