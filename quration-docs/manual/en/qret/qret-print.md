% QRET-PRINT(1) Quration User Manuals

# NAME

qret-print - Display information and structure of an input circuit

# SYNOPSIS

**qret print** `{-i | --input}` *PATH* `[-s | --summary]` `[-f | --function *NAME*]` `[-d | --depth *ARG*]`
           `[--quiet | --verbose | --debug]` `[--color]` `[--print_debug_info]`
           `[-h | --help]`

# DESCRIPTION

**qret print** displays various information and structural details about an input circuit representation.

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

`-s`, `--summary`
: Print a summary only of the circuit. This is the default behavior when `--function` is omitted.

`-f`, `--function` *NAME*
: Provide the function name to be printed. When combined with `--summary`, prints the function summary only.

`-d`, `--depth` *ARG*
: Print only up to *ARG* levels of call instructions.

`--print_debug_info`
: Enable debug prints when running the command by forcing the print of instructions with optimization hints or displaying additional metadata about instructions. (This differs from `--quiet`, `--verbose`, and `--debug`, which only target the Logger).

# EXAMPLES

Print the general summary of an input circuit:

```bash
qret print --input circuit.json --summary
```
