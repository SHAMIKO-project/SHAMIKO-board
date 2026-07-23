# SHAMIKO

![SHAMIKO Rev Alpha](docs/images/RevAlphaPhoto.png)

**SHAMIKO: an open-source side-channel analysis board with dual Xilinx Spartan-7 FPGAs**

SHAMIKO is an experimental FPGA board for power analysis (side-channel) attacks, developed with the goal of providing functionality equivalent to SAKURA-G. It carries Xilinx Spartan-7 FPGAs, enabling development with the latest Vivado toolchain instead of the legacy ISE.

All design data — schematics, PCB layout, and project-specific libraries — is published in KiCad format and is freely modifiable. Customizations such as replacing the Main FPGA with your own taped-out IC for power analysis are also possible.

## Features

- **Dual FPGA architecture** — a Control FPGA for control and PC communication, and a Main FPGA for implementing the circuit under analysis (both Xilinx Spartan-7)
- **Vivado support** — development with the latest Vivado / Vitis
- **Power measurement circuit** — a shunt resistor inserted in the Main FPGA core power rail. Power consumption can be observed on an oscilloscope either through the on-board amplifier (equivalent to SAKURA-G) or directly via BNC connectors across the shunt resistor
- **Low-noise power design** — two-stage DC-DC + LDO regulation, with independent 1.0 V rails for the Control and Main FPGAs
- **Selectable measurement target** — 0 Ω jumper resistors select measurement of VCC_INT only, or VCC_INT + VCC_BRAM
- **High-speed PC interface** — FT600 (parallel bus) and FT2232H (UART / FIFO)
- **Fully open source** — the complete KiCad project (schematics, PCB, libraries) is published

## Revision Status

| Revision | Status |
|---|---|
| Rev Alpha | Manufactured, under evaluation |
| Rev Beta | In design (not yet manufactured) |
| Rev 1.0 | To be released after Rev Beta verification |

## Repository Structure

```
SHAMIKO-board/
├── hardware/       # KiCad project (schematics, PCB, libraries)
├── docs/
│   ├── manual/     # Manual (LaTeX source, Markdown)
│   ├── schematic.pdf
│   └── images/
└── LICENSE
```

## Getting Started

### Design Data

The KiCad project under `hardware/` contains the schematics and PCB layout.

Gerber files and the BOM will be published once manufacturing and verification are complete. Until then, please export them from KiCad yourself if you wish to manufacture the board.

### Development Environment

- **FPGA development**: AMD (Xilinx) Vivado
- **PCB design**: KiCad

### Power Supply

The board is powered by an external 12 V AC adapter. The power-up sequence is controlled automatically on the board.

## Documentation

For detailed specifications (power system, clocking, configuration, pin assignments, etc.), see the manual.

- Manual PDF: attached to [Releases](https://github.com/SHAMIKO-project/SHAMIKO-board/releases)
- Markdown version: `docs/manual/`

## Sample Designs / Host Software

Sample HDL (cryptographic implementations) and host-side communication software are in preparation. Coming soon.

## Contact

- Bug reports and questions: [GitHub Issues](https://github.com/SHAMIKO-project/SHAMIKO-board/issues)
- Discord community: Coming soon

## Developers

- Hirata Haruka
- Ohara Ryotaro

## License

This project is released under the [MIT License](LICENSE).

## Acknowledgements

- [SAKURA-G](http://satoh.cs.uec.ac.jp/SAKURA/hardware/SAKURA-G.html) — a pioneering FPGA board project for side-channel attack evaluation. SHAMIKO is an independent project with no affiliation to the SAKURA project, but we hold its groundbreaking work in the deepest respect, and it serves as the benchmark for our design goals.

---

*日本語版: [README.md](README.md)*