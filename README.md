# FPGA Timing and FM Tuning Interface — Design Archive

Documentation and schematic captures from a digital-electronics laboratory on counters, button conditioning and an FM-frequency tuning interface.

## Design scope

The project explores a 87.5–108.0 MHz displayed tuning range with 0.1 MHz steps. Its control logic distinguishes short button presses from longer presses that trigger repeated increment or decrement; pressing both controls requests initialisation.

The timing study describes a nominal two-second long-press threshold. Its realised duration depends on the clock divider and counter configuration.

## Digital building blocks

- BCD counting and frequency-bound detection.
- Digit decoding and multiplexed seven-segment display.
- Clock division and delay counting.
- Multi-flip-flop button sampling and conditioning.
- Finite-state control for increment, decrement and initialisation.

A sampled flip-flop chain should be distinguished from a fully specified mechanical-switch debounce filter: synchronisation alone does not establish a debounce interval.

## Available material

| Location | Content |
|---|---|
| [`documentation/`](documentation/) | Working digital-electronics report |
| [`assets/`](assets/) | Schematics, logic captures and supporting illustrations |
| [Related VHDL sources](https://github.com/tedjelmoulksn-dotcom/FPGA_VHDL/tree/main/Tuner_FM_FPGA) | Tuner state-machine source and integration notes in the FPGA portfolio |

This repository contains documentation rather than a complete HDL project. The related portfolio contains source fragments; neither archive should be presented as a ready-to-build RF receiver.

## Review workflow

```bash
git clone https://github.com/tedjelmoulksn-dotcom/Minuterie_FPGA.git
cd Minuterie_FPGA
```

Read the report alongside the schematic captures, trace button events through the state machine and verify divider-derived timing against the actual clock. Use the related VHDL repository for source inspection.

## Validation status

The report documents the original coursework. No new simulation, synthesis or board test was performed for this README update. Reconstructing the design requires identifying the original target, toolchain, top-level interconnections and constraints.

## Licence

No project-wide licence has been defined.
