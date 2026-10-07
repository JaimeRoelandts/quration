% CREATE_UNCOMPUTE_QROM(1) Quration User Manuals

# NAME

create_uncompute_qrom - Generate a Quration IR JSON circuit when accessing quantum read-only memory.

# SYNOPSIS

**create_uncompute_qrom** `--input` *PATH* `--output` *PATH* `[--inline]` `[--help]`

# DESCRIPTION

**create_uncompute_qrom** creates a circuit that performs the uncomputation of the `create_qrom` circuit, to clean up/unentangle ancilla qubits.
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

`address_size` (integer)
: Number of bits for address `x`

`value_size` (integer)
: Number of bits for data `D_x`

`multiplier` (integer)
: multiplier `a`

`offset` (integer)
: offset `b`

# EXAMPLES

Given an input file `config.json`:

```json
{
  "address_size": 5,
  "value_size": 6,
  "multiplier": "12323474",
  "offset": "234956789"
}
```
```
