% CREATE_PERIOD_FINDING(1) Quration User Manuals

# NAME

create_period_finding - Generate a Quration IR JSON circuit for finding the order of a given input value, provided a modulus.

# SYNOPSIS

**create_period_finding** `--input` *PATH* `--output` *PATH* `[--inline]` `[--help]`

# DESCRIPTION

**create_period_finding** creates a circuit that calculates the order `r` of an input value `x`, such that `x^r = 1 (mod N)`. Where it is assumed that `x` and `N` are coprime.
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

`coprime_integer` (*integer*)
: x (coprime to N)

`depth` (*integer*)
: bit precision of the solution `r`

# EXAMPLES

Given an input file `config.json`:

```json
{
  "modulus": "15",
  "coprime_integer": "2",
  "depth": 4
}
```
