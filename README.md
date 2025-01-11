# Embedded Board Taxonomy 🔧

This repository provides definitions and examples for different categories of embedded computing boards. The goal is to establish clear terminology for discussing and categorising various types of development boards, single-board computers, and embedded platforms.

## Categories

### 🖥️ Single Board Computer (SBC)
A complete computer system implemented on a single board, capable of running a full operating system like Linux or Windows.

Key characteristics:
- Runs full multi-tasking operating systems
- Has display output (HDMI, DisplayPort, DVI, etc.)
- Generally includes standard PC interfaces (USB, network, etc.)
- May be lower power than traditional PCs
- Complete system on a single board
- Typically credit card sized (85.6 × 53.98 mm) or up to Mini-ITX (170 × 170 mm)

Examples:
- Raspberry Pi (3, 4, 5)
- BeagleBone Black
- ROCK Pi
- Orange Pi
- Banana Pi

### 💻 Compute Module (CM)
The core computing system of an SBC without fixed I/O, designed for integration into custom carrier boards.

Key characteristics:
- Contains the essential computing elements (CPU, RAM, storage)
- Requires a carrier board for I/O and power
- Highly flexible in terms of final implementation
- Often used in commercial products
- Same software capabilities as full SBCs
- Two common form factors:
  - SODIMM form factor (67.6 × 30 mm), as used in CM1-3
  - Custom Raspberry Pi CM4 and CM5 form factor (55 × 40 mm) with standardised connectors (2× B2B 100-pin for 'CM4', 3× for 'CM5')

Examples:
- Raspberry Pi Compute Module (CM3, CM4, CM5)
- NVIDIA Jetson modules
- Intel NUC compute elements
- Radxa CM3
- Pine64 SOQuartz

### 🌐 Embedded Single Board Computer (eSBC)
Similar to an SBC but designed for headless operation without display output.

Key characteristics:
- Runs full multi-tasking operating systems
- No display output
- Accessed via SSH, UART, or similar
- Often used in embedded applications
- May have reduced I/O compared to full SBCs
- Often in gumstick (~ 70 × 20 mm) or stamp (~ 25 × 25 mm) form factors

Examples:
- Milk-V Duo
- Luckfox Pico Pro
- LattePanda Alpha (headless version)
- Many industrial Linux boards

### 🔌 Embedded System Board (ESB)
General-purpose boards built around an MCU or simple SOC, designed for embedded applications.

Key characteristics:
- Based on microcontroller or simple system-on-chip
- Cannot run full multi-tasking operating systems
- Typically runs Arduino, MicroPython, or RTOS
- Designed for both development and deployment
- Part of a broader development ecosystem

Examples:
- Raspberry Pi Pico
- Arduino boards (Uno, Mega, etc.)
- ESP32 development boards
- Teensy boards
- Adafruit Feather boards

### 🛠️ Development/Evaluation Board (DevBoard/EvalBoard)
Boards specifically designed to demonstrate and evaluate the capabilities of a particular chip.

Key characteristics:
- Focused on showcasing specific chip features
- Primary purpose is prototyping and evaluation
- Often includes additional debugging features
- May expose all chip pins for testing
- Usually comes with manufacturer-specific tools and documentation

Examples:
- STM32 Nucleo boards
- Nordic nRF52 Development Kit
- Texas Instruments LaunchPad
- Microchip PIC development boards
- NXP evaluation boards

## Contributing 🤝

This taxonomy is a living document. If you have suggestions for:
- Additional board categories
- New example boards
- Clarifications to definitions
- Edge cases that don't fit well

Please open an issue or submit a pull request!

## Notes 📝

1. Some boards may blur the lines between categories or have features that span multiple categories. In these cases, consider the primary intended use case and main features.

2. This taxonomy focuses on general-purpose and development boards. Specialised boards (like AI accelerators or FPGA development boards) may need different categorisation.

3. The presence or absence of specific features (like wireless connectivity or storage) is not a primary factor in categorisation, as these can appear across all categories.

4. Compute Modules often bridge multiple categories depending on their carrier board implementation - they can become either full SBCs or eSBCs based on the carrier board design.

## Common Form Factors 📏

Different board categories typically align with certain form factors:

### Standard Sizes
- Credit Card: 85.6 × 53.98 mm (typical for SBCs)
- Mini-ITX: 170 × 170 mm (larger SBCs)
- SODIMM: 67.6 × 30 mm (common for older Compute Modules)
- RPi CM: 55 × 40 mm (standard for newer Compute Modules)
- Gumstick: ~70 × 20 mm (common for eSBCs)
- Stamp: ~25 × 25 mm (common for eSBCs and some ESBs)

### Notes on Form Factors
- SBCs typically stick to credit card size or larger standardised PC form factors
- Compute Modules are highly standardised in both size and connector placement
- eSBCs tend toward smaller form factors due to their headless nature
- ESBs and DevBoards can vary widely in size depending on their purpose
- Some manufacturers create their own custom form factors for specific use cases
