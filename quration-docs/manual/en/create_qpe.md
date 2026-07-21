% CREATE_QPE(1) Quration User Manuals

# NAME

create_qpe - Generate a Quration IR JSON circuit that calculates the phase estimation (eigenvalues) of a Hamiltonian

# SYNOPSIS

**create_qpe** `--input` *PATH* `--output` *PATH* `[--inline]` `[--help]`

# DESCRIPTION

**create_qpe** creates a circuit that generates the eigenvalues of a Hamiltonian represented by `H = ∑_i α_i P_i`. (The circuit is based on [R. Babbush et al., "Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity"](https://arxiv.org/abs/1805.03662).) The `α_i` value is a Pauli coefficient for the Pauli term `P_i` which can be multi-dimensional. This circuit makes use of the prepare and select circuit repeatedly.
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

`lcu_coefficients` (List(floats))
: `α_i` values that composes the Hamiltonian.

`system_size` (integer)
: Number of qubits of the Hamiltonian

`hadamard_size` (integer)
: Fixed-point binary precision of the desired eigenvalue

`sub_bit_precision` (*integer*)
: Binary fixed-point precision when handling the coefficient `α_i`.

# EXAMPLES

Given an input file `config.json`:

```json
{
  "pauli_strings": [
        ["Z", "I"],
        ["Z", "Z"],
        ["X", "X"]
  ],
  "lcu_coefficients": [0.25, 0.25, 0.5],
  "system_size": 2,
  "hadamard_size": 3,
  "sub_bit_precision": 3
}
```
