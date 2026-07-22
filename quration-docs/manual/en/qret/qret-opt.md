% QRET-OPT(1) Quration User Manuals

# NAME

qret opt - Optimizes the intermediate representation circuit by applying the desired optimization passes.

# SYNOPSIS

**qret opt** {`-i` | `--input`} *PATH* {`-o` | `--output`} *PATH* [`--pipeline` *ARG*] [`--ir-static-condition-pruning-seed` *ARG*] [`--pass` *ARG*]
             [`--quiet` | `--verbose` | `--debug`] [`--color`]
             [`-h` | `--help`]

# DESCRIPTION

**qret opt** Optimizes the intermediate representation circuit by applying the desired optimization passes.

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

`--pipeline` *ARG*
: Pipeline file, wich can contain multiple optimization passes

`-f`, `--function` *ARG*
: Function name to apply the optimization pass to.

`-i`, `--input` *PATH*
: **Required.** Path to the input circuit in the intermediate representation.

`-o`, `--output` *PATH*
: **Required**, Path where the output results will be written.

`--ir-static-condition-pruning-seed` *ARG*
: Seed for the of ir::static_condition_pruning optimization pass.

`--pass` *ARG*
: Optimization pass

# EXAMPLES

TODO
