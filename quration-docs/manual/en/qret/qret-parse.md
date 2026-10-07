% QRET-PARSE(1) Quration User Manuals

# NAME

qret parse - Parses the intermediate representation of Quration into OpenQASM2 or OpenQASM3 format.

# SYNOPSIS

**qret parse** {`-i` | `--input`} *PATH* [`-o` | `--output` *PATH*] [`-f` | `--format` <OpenQASM2|OpenQASM3>]
             [`--quiet` | `--verbose` | `--debug`] [`--color`]
             [`-h` | `--help`]

# DESCRIPTION

**qret parse** parses the intermediate representation of Quration. It will output the same commands in the OpenQASM2 and OpenQASM3 format for compatibility with other software.

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

`-o`, `--output` *PATH*
: Path where the output results will be written. (Default: `ir.json`).

`-f`, `--format` <OpenQASM2|OpenQASM3>
: Format in which the output will be converted to. (Default: `OpenQASM2`)

# EXAMPLES

TODO
