% QRET-PROFILE(1) Quration User Manuals

# NAME

qret profile - Profile and analyze structural information of an input circuit

# SYNOPSIS

**qret profile** {`-i` | `--input`} *PATH* [`-s` | `--source` *PATH*] [`-f` | `--format` `json`|`markdown`] [`-o` | `--output` *PATH*]
             [`--quiet` | `--verbose` | `--debug`] [`--color`]
             [`-h` | `--help`]

# DESCRIPTION

**qret profile** analyzes an input circuit representation and displays profiling information, performance characteristics, and structural metrics.

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

`-s`, `--source` *PATH*
: Path to the input circuit and layout. (Default: `"SC_LS_FIXED_V0"`).

`-f`, `--format` `json`|`markdown`
: Format in which the analysis results will be generated. (Default: `"json"`).

`-o`, `--output` *PATH*
: Path where the output results will be written. (Default: `"compile_info.json"`).

# EXAMPLES

Profile a circuit using default settings:

```bash
qret profile -i circuit.ir
```
