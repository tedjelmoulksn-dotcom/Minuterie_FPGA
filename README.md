# FPGA Timing and FM Tuning Interface — Design Archive

Design archive for FPGA timing, button control and an FM-frequency display interface.

![State-machine design for the FM-frequency selection interface.](assets/machine_etats_stmp.png)

*State-machine design for the FM-frequency selection interface.*

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

This repository focuses on the design report and schematics. The linked VHDL portfolio provides the associated digital-control sources; the scope is frequency selection and display logic.

## Review workflow

```bash
git clone https://github.com/tedjelmoulksn-dotcom/Minuterie_FPGA.git
cd Minuterie_FPGA
```

Read the report alongside the schematic captures, trace button events through the state machine and verify divider-derived timing against the actual clock. Use the related VHDL repository for source inspection.

## Validation status

The report and schematic captures let the design be traced from a button event to the displayed BCD value. Check one-step operation, sustained stepping and upper/lower boundary handling independently, then calculate the long-press interval from the divider and counter values.

The report explains the intended state transitions, while the schematic captures expose their implementation. Reproduction uses the original target/toolchain and reconstructed interconnections, followed by boundary and timing checks.

## Licence

No project-wide licence has been defined.
