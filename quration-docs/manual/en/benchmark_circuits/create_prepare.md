% CREATE_PREPARE(1) Quration User Manuals

# NAME

create_prepare - Generate a Quration IR JSON circuit to prepare the state for quantum phase estimation.

# SYNOPSIS

**create_prepare** `--input` *PATH* `--output` *PATH* `[--inline]` `[--help]`

# DESCRIPTION

**create_prepare** creates a circuit that generate a quantum state `∑_i α_i |i⟩`, with the `α_i` representing the weights corresponding to the Hamiltonian `H = ∑_i α_i P_i` (and `P_i` being multi-dimensional Pauli terms).
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

`lcu_coefficients` (List(floats))
: `α_i` values that composes the Hamiltonian.

`sub_bit_precision` (*integer*)
: Binary fixed-point precision when handling the coefficient `α_i`.

# EXAMPLES

Given an input file `config.json`:

```json
{
  "lcu_coefficients": [0.25, 0.25, 0.5],
  "sub_bit_precision": 3
}
```
