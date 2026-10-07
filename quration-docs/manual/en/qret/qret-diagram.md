% QRET-DIAGRAM(1) Quration User Manuals

# NAME

qret diagram - Visualize the circuit in different graph formats.

# SYNOPSIS

**qret diagram** {`-i` | `--input`} *PATH* [`--function` *ARG*] [`-o` | `--output` *PATH*] [`-g` | `--graph-format` <CFG|CallGraph [`--display_num_calls`] |LaTeX|ComputeGraph>]
             [`--quiet` | `--verbose` | `--debug`] [`--color`]
             [`-h` | `--help`]

# DESCRIPTION

**qret diagram** creates a visual representation in a diagram of the circuit. The possiblites are control flow graphs (CFG), call graphs, computer graphs, and a latex output.

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

`--function` *ARG*
: Function name to draw

`-o`, `--output` *PATH*
: Path where the output results will be written. (Default: `"out.dot"` or `"out.tex"`).

`-g`, `--graph-format` <CFG|CallGraph|LaTeX|ComputeGraph>
: Type of diagram to generate 

`--display_num_calls`
: When the format is `Callgraph`, it displays how many times a function is called

# EXAMPLES

TODO
