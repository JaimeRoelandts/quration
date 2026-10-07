% QRET-COMPILE(1) Quration User Manuals

# NAME

qret-compile - Compiles a circuit in the intermediate representation to a target chip.

# SYNOPSIS

**qret compile** {`-i`, `--input`} *PATH* [`-h`, `--help` | `--help-hidden` | `--help-really-hidden`] [`--quiet` | `--verbose` | `--debug`] [`--color`] [`--pipeline` *PATH*]
             [`-f`, `--function` *NAME*] [`-o`, `--output` *PATH*] [`-s`, `--source` <IR|OpenQASM2|SC_LS_FIXED_V0>] [`-t`, `--target` *KIND*]
             [`--sc_ls_fixed_v0_topology` *PATH*] [`--sc_ls_fixed_v0_topology_type` <Dim2|Dim3|DistributedDim2|DistributedDim3|auto>] [`--sc_ls_fixed_v0_enable_pbc_mode`] [`--sc_ls_fixed_v0_use_magic_state_cultivation` [`--sc_ls_fixed_v0_magic_factory_seed_offset` *ARG*] [`--sc_ls_fixed_v0_magic_generation_success_probability` *ARG*]] [`--sc_ls_fixed_v0_magic_generation_period` *ARG*] [`--sc_ls_fixed_v0_magic_generation_maximum_stock` *ARG*] [`--sc_ls_fixed_v0_entanglement_generation_period` *ARG*] [`--sc_ls_fixed_v0_entanglement_generation_maximum_stock` *ARG*] [`--sc_ls_fixed_v0_reaction_time` *ARG*] [`--sc_ls_fixed_v0_logical_error_rate_base` *ARG*] [`--sc_ls_fixed_v0_logical_error_rate_drop_rate` *ARG*] [`--sc_ls_fixed_v0_code_cycle_time_sec` *ARG*] [`--sc_ls_fixed_v0_allowed_failure_probability` *ARG*] [`--sc_ls_fixed_v0_magic_factory_cell_count` *ARG*] [`--sc_ls_fixed_v0_pass` *PASS*] [`--sc_ls_fixed_v0_dump_compile_info_to_json` *ARG*] [`--sc_ls_fixed_v0_dump_compile_info_to_markdown` *ARG*]
             [`--ir-static-condition-pruning-seed` *ARG*] [`--sc_ls_fixed_v0-find-place-algorithm` *ARG*] [`--sc_ls_fixed_v0-inst-queue-peek-size` *ARG*] [`--sc_ls_fixed_v0-inst-queue-weight-algorithm` *ARG*] [`--sc_ls_fixed_v0-mapping-algorithm` *ARG*] [`--sc_ls_fixed_v0-partition-algorithm` *ARG*] [`--sc_ls_fixed_v0-partition-seed` *ARG*] [`--sc_ls_fixed_v0-print-inst-metadata` *ARG*] [`--sc_ls_fixed_v0-route-searcher-type` *ARG*] [`--sc_ls_fixed_v0-state-buffer-width` *ARG*] [`--sc_ls_fixed_v0_dump_pbc_string` *ARG*] [`--sc_ls_fixed_v0_runtime_simulation_pruning_seed` *ARG*] 

# DESCRIPTION

**qret compile** takes an input circuit in the intermediate representation, and target architecture. Then compiles the intermediate representation to the target low-level instructions of that architecture.

# OPTIONS

`-h`, `--help`
: Show this help and exit.

`--help-hidden`
: Show help including hidden options.

`--quiet`
: Suppress non-error output.

`--verbose`
: Enable verbose logging (more detail than default).

`--debug`
: Enable debug logging (most detailed; implies --verbose).

`--color`
: Enable colored output.

`--pipeline` *PATH*
: Path to a pipeline specification file.

`-i`, `--input` *PATH*
: **Required**, path to the input file.

`-f`, `--function` *NAME*
: The source needs to be in the IR (intermediate representation), it compiles that function name.

`-o`, `--output` *PATH*
: Path to the output SC_LS_FIXED_V0 file. (Default: `a.json`)

`-s`, `--source` <IR|OpenQASM2|SC_LS_FIXED_V0>
: Source representation: 'IR', 'OpenQASM2', or 'SC_LS_FIXED_V0'. (Default `IR`)

`-t`, `--target` *KIND*
: Target machine name. (Default: `SC_LS_FIXED_V0`)

`--sc_ls_fixed_v0_topology` *PATH*
: Path to the SC_LS_FIXED_V0 topology file.

`--sc_ls_fixed_v0_topology_type` <Dim2|Dim3|DistributedDim2|DistributedDim3|auto>
: SC_LS_FIXED_V0 machine type: 'Dim2', 'Dim3', 'DistributedDim2', or 'DistributedDim3' (currently unsupported). When 'auto', the type is inferred from --sc_ls_fixed_v0_topology as the minimum required. (Default: `auto`)

`--sc_ls_fixed_v0_enable_pbc_mode`
: Enable Pauli Based Computing lowering mode.

`--sc_ls_fixed_v0_use_magic_state_cultivation`
: Simulate magic-state factories using the cultivation method (requires `--sc_ls_fixed_v0_magic_factory_seed_offset`, and `--sc_ls_fixed_v0_magic_generation_success_probability`).

`--sc_ls_fixed_v0_magic_factory_seed_offset` *ARG*
: Base seed offset for RNG initialization of each magic-state factory. Required only if --sc_ls_fixed_v0_use_magic_state_cultivation=true. (Default: `0`)

`--sc_ls_fixed_v0_magic_generation_period` *ARG*
: Beats required to produce one magic state. (Default: `15`)

`--sc_ls_fixed_v0_magic_generation_success_probability` *ARG*
: Per-attempt success probability for magic-state creation. Required only if `--sc_ls_fixed_v0_use_magic_state_cultivation=true`. (Default: `1`)

`--sc_ls_fixed_v0_magic_generation_maximum_stock` *ARG*
: Maximum number of magic states storable in a factory. (Default: `10000`)

`--sc_ls_fixed_v0_entanglement_generation_period` *ARG*
: Beats required to generate one entangled pair. (Default: `100`)

`--sc_ls_fixed_v0_entanglement_generation_maximum_stock` *ARG*
: Maximum number of entangled pairs storable in a factory. (Default: `10`)

`--sc_ls_fixed_v0_reaction_time` *ARG*
: Feed-forward latency in beats from measurement to error-corrected value. (Default: `1`)

`--sc_ls_fixed_v0_logical_error_rate_base` *ARG*
: Physical error rate p for logical error estimation. (Default: `0`)

`--sc_ls_fixed_v0_logical_error_rate_drop_rate` *ARG*
: Drop rate Lambda for logical error estimation. (Default: `0`)

`--sc_ls_fixed_v0_code_cycle_time_sec` *ARG*
: Code cycle time in seconds (t_cycle) for execution time estimation. (Default: `0`)

`--sc_ls_fixed_v0_allowed_failure_probability` *ARG*
: Allowed failure probability (eps) for logical error estimation. (Default: `0`)

`--sc_ls_fixed_v0_magic_factory_cell_count` *ARG*
: Number of surface code cells per magic state factory for resource estimation. Qubit plane always uses 1 cell per factory regardless of this value. (Default: `1`)

`--sc_ls_fixed_v0_pass` *PASS*
: SC_LS_FIXED_V0 compile pass to run. Accepts a single pass or a comma-separated list.

`--sc_ls_fixed_v0_dump_compile_info_to_json` *ARG*
: Dump compile information to json

`--sc_ls_fixed_v0_dump_compile_info_to_markdown` *ARG*
: Dump compile information to markdown

# Hidden options

`--help-really-hidden`
: Display available options including really hidden ones

`--ir-static-condition-pruning-seed` *ARG*
: Seed of StaticConditionPruningPass (Default: `0`)

`--sc_ls_fixed_v0-find-place-algorithm` *ARG*
: Find place algorithm of mapping (0: EnoughSpaceSoft, 1: EnoughSpaceHard) (Default: `0`)

`--sc_ls_fixed_v0-inst-queue-peek-size` *ARG*
: Peek size of instruction queue (Default: `1000`)

`--sc_ls_fixed_v0-inst-queue-weight-algorithm` *ARG*
: Weight algorithm of instruction queue (0: index, 1: type, 2: InvDepth) (Default: `2`)

`--sc_ls_fixed_v0-mapping-algorithm` *ARG*
: Mapping algorithm (0: Map based on topology file, 1: Auto) (Default: `1`)

`--sc_ls_fixed_v0-partition-algorithm` *ARG*
: Partition algorithm of mapping (0: Greedy, 1: Random, 2: METIS) (Default: `0`)

`--sc_ls_fixed_v0-partition-seed` *ARG*
: Random seed of mapping partition when partition algorithm is Random. (Default: `314`)

`--sc_ls_fixed_v0-print-inst-metadata` *ARG*
: Print metadata of instructions (beat and z coordinate). (Default: `0`)

`--sc_ls_fixed_v0-route-searcher-type` *ARG*
: Route searcher strategy (Default: `0`)

`--sc_ls_fixed_v0-state-buffer-width` *ARG*
: Buffer width of quantum states (Default: `20`)

`--sc_ls_fixed_v0_dump_pbc_string` *ARG*
: Dump pauli string if PBC mode is enabled

`--sc_ls_fixed_v0_runtime_simulation_pruning_seed` *ARG*
: Seed (Default `0`)

# Really hidden options

None for now (TODO: check code)

# EXAMPLES

TODO

[`-h`, `--help` | `--help-hidden` | `--help-really-hidden`] [`--quiet` | `--verbose` | `--debug`] [`--color`] [`--pipeline` *PATH*] {`-i`, `--input`} *PATH*
[`-f`, `--function` *NAME*] [`-o`, `--output` *PATH*] [`-s`, `--source` <IR|OpenQASM2|SC_LS_FIXED_V0>] [`-t`, `--target` *KIND*]
[`--sc_ls_fixed_v0_topology` *PATH*] [`--sc_ls_fixed_v0_topology_type` <Dim2|Dim3|DistributedDim2|DistributedDim3|auto>] [`--sc_ls_fixed_v0_enable_pbc_mode`] [`--sc_ls_fixed_v0_use_magic_state_cultivation` [`--sc_ls_fixed_v0_magic_factory_seed_offset` *ARG*] [`--sc_ls_fixed_v0_magic_generation_success_probability` *ARG*]] [`--sc_ls_fixed_v0_magic_generation_period` *ARG*] [`--sc_ls_fixed_v0_magic_generation_maximum_stock` *ARG*] [`--sc_ls_fixed_v0_entanglement_generation_period` *ARG*] [`--sc_ls_fixed_v0_entanglement_generation_maximum_stock` *ARG*] [`--sc_ls_fixed_v0_reaction_time` *ARG*] [`--sc_ls_fixed_v0_logical_error_rate_base` *ARG*] [`--sc_ls_fixed_v0_logical_error_rate_drop_rate` *ARG*] [`--sc_ls_fixed_v0_code_cycle_time_sec` *ARG*] [`--sc_ls_fixed_v0_allowed_failure_probability` *ARG*] [`--sc_ls_fixed_v0_magic_factory_cell_count` *ARG*] [`--sc_ls_fixed_v0_pass` *PASS*] [`--sc_ls_fixed_v0_dump_compile_info_to_json` *ARG*] [`--sc_ls_fixed_v0_dump_compile_info_to_markdown` *ARG*]
[`--ir-static-condition-pruning-seed` *ARG*] [`--sc_ls_fixed_v0-find-place-algorithm` *ARG*] [`--sc_ls_fixed_v0-inst-queue-peek-size` *ARG*] [`--sc_ls_fixed_v0-inst-queue-weight-algorithm` *ARG*] [`--sc_ls_fixed_v0-mapping-algorithm` *ARG*] [`--sc_ls_fixed_v0-partition-algorithm` *ARG*] [`--sc_ls_fixed_v0-partition-seed` *ARG*] [`--sc_ls_fixed_v0-print-inst-metadata` *ARG*] [`--sc_ls_fixed_v0-route-searcher-type` *ARG*] [`--sc_ls_fixed_v0-state-buffer-width` *ARG*] [`--sc_ls_fixed_v0_dump_pbc_string` *ARG*] [`--sc_ls_fixed_v0_runtime_simulation_pruning_seed` *ARG*] 

