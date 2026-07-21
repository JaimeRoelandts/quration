% CREATE_ADD_CUCCARO(1) Quration User Manuals

# NAME

create_add_cuccaro - Generate a Quration IR JSON circuit based on the Cuccaro adder

# SYNOPSIS

**create_add_cuccaro** `--input` *PATH* `--output` *PATH* `[--inline]` `[--help]`

# DESCRIPTION

**create_add_cuccaro** creates a circuit based on the Cuccaro adder algorithm. The Cuccaro adder takes two integers `(x,y)` and computes the sum, in-place on the second integer, with the final output looking like `(x,x+y)`. More details can be found in the following paper [C. Gidney, Halving the cost of quantum addition](https://arxiv.org/abs/1709.06648).
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

`size` (*integer*)
: The qubit length the adder should perform.

# EXAMPLES

Given an input file `config.json`:

```json
{
  "size": 5
}
```
