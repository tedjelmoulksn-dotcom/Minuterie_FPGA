# FPGA FM Tuning Controller

A VHDL study of an FM tuning interface, combining button handling, a control state machine, BCD counting and multiplexed display logic. The repository retains its historical name, `Minuterie_FPGA`; the supplied report and sources describe an FM tuner.

## Architecture

Up/down inputs drive the controller's increment, decrement and hold-repeat states. Supporting logic provides decimal counting, display selection and hexadecimal-to-seven-segment decoding. The laboratory specification describes a **87.5–108 MHz** tuning range in **0.1 MHz** steps.

## Repository guide

| Path | Contents |
| --- | --- |
| [src/FWSTMP.vhd](src/FWSTMP.vhd) | Tuning controller state machine |
| [src/tp0_prise_en_main_ise](src/tp0_prise_en_main_ise/) | Introductory design, schematics, testbenches and board constraints |
| [src/tp1_affichage_multiplexe](src/tp1_affichage_multiplexe/) | Display multiplexer, decoder and clock-divider schematic |
| [src/tp2_tuner_fm](src/tp2_tuner_fm/) | BCD counter, initialization logic and draft controller |
| [documentation](documentation/) | Laboratory report |
| [assets](assets/) | State diagram, debounce diagrams and implementation captures |

## Use

Inspect the VHDL modules and testbenches with a compatible simulator. The original work uses Xilinx ISE project conventions; check the constraints and target device before attempting synthesis in another toolchain.

The sources are exercise modules and variants, not a freshly verified complete bitstream. Repeat timing depends on the selected clock and divider. Historical ISE projects remain archived in [FPGA_VHDL](https://github.com/tedjelmoulksn-dotcom/FPGA_VHDL).
