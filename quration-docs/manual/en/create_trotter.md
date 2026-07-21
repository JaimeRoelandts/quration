% CREATE_TROTTER(1) Quration User Manuals

# NAME

create_trotter - Generate a Quration IR JSON circuit that simulates the quantum state `exp(iHt)|𝜓_0⟩` for a given hamiltonian `H`, initial state `|𝜓_0⟩`, and simulated time `t`.

# SYNOPSIS

**create_trotter** `--input` *PATH* `--output` *PATH* `[--inline]` `[--help]`

# DESCRIPTION

**create_trotter** creates a circuit that simulates a quantum state given a Hamiltonian `H = ∑_i α_i P_i`, with `P_i` being multi-dimensional Pauli terms, a simulated time `t`, and an initial state `|𝜓_0⟩`. It makes use of the Trotter expansion to approximate the simulation with a large integer `M` called the Trotter number. Such that the dynamics are approximated as `exp(iHt) = exp(iHt/M)^M ≃ (∏_i exp(i t α_i P_i / M)^M`.
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

`time` (float)
: Simulated time `t`

`num_trotter_steps` (integer)
: Trotter number (trotter steps) `M`

`num_qubits` (integer)
: Number of qubits for the Hamiltonian

`pauli_terms` (List(Pauli Term))
: List to represent the Hamiltonian

## Pauli Term

Contains the following values.

`coeff` (float)
: The relative weight of that Pauli term

`pauli_string` (Dict("`[0-9]+`", "X"|"Y"|"Z"|"I"))
: A dictionary with the qubit index is run with by which Pauli operation.

# EXAMPLES

Given an input file `config.json`:

```json
{
  "time": 1.0,
  "num_trotter_steps": 1,
  "num_qubits": 5,
  "pauli_terms": [
    {
      "coeff": 1.0,
      "pauli_string": {
        "0": "X"
      }
    },
    {
      "coeff": 1.0,
      "pauli_string": {
        "0": "Z",
        "1": "Z"
      }
    },
    {
      "coeff": 1.0,
      "pauli_string": {
        "1": "X"
      }
    },
    {
      "coeff": 1.0,
      "pauli_string": {
        "1": "Z",
        "2": "Z"
      }
    },
    {
      "coeff": 1.0,
      "pauli_string": {
        "2": "X"
      }
    },
    {
      "coeff": 1.0,
      "pauli_string": {
        "2": "Z",
        "3": "Z"
      }
    },
    {
      "coeff": 1.0,
      "pauli_string": {
        "3": "X"
      }
    },
    {
      "coeff": 1.0,
      "pauli_string": {
        "3": "Z",
        "4": "Z"
      }
    },
    {
      "coeff": 1.0,
      "pauli_string": {
        "4": "X"
      }
    },
    {
      "coeff": 1.0,
      "pauli_string": {
        "4": "Z",
        "0": "Z"
      }
    }
  ]
}
```
