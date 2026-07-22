% CREATE_SELECT(1) Quration User Manuals

# NAME

create_select - Generate a Quration IR JSON circuit that generates a (diagonal block-matrix) unitary operation, used as a subroutine in the Quantum Phase Estimation circuit.

# SYNOPSIS

**create_select** `--input` *PATH* `--output` *PATH* `[--inline]` `[--help]`

# DESCRIPTION

**create_select** creates a circuit that implements the unitary operation `U = ∑_i |i⟩⟨i| ⊗ P_i`, with `P_i ∈ ±{I,X,Y,Z}^{⊗ n}` being a multi-dimensional Pauli term. With the `P_i` corresponding to the Hamiltonian `H = ∑_i α_i P_i`.
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

`pauli_strings` (List(List("X"|"Y"|"Z"|"I")))
: List of Pauli terms `P_i` of the Hamiltonian

# EXAMPLES

Given an input file `config.json`:

```json
{
  "pauli_strings": [
        ["Z", "I"],
        ["Z", "Z"],
        ["X", "X"]
  ]
}
```
```
