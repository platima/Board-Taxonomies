# Embedded Board Taxonomy 🔧

This repository provides definitions and examples for different categories of embedded computing boards. The goal is to establish clear terminology for discussing and categorising various types of development boards, single-board computers, and embedded platforms.

## Table of Contents 📑
- [Categories](#categories)
  - [Single Board Computer (SBC)](#-single-board-computer-sbc)
  - [Compute Module (CM)](#%EF%B8%8F-compute-module-cm)
  - [Embedded Single Board Computer (eSBC)](#-embedded-single-board-computer-esbc)
  - [Embedded System Board (ESB)](#-embedded-system-board-esb)
  - [Development/Evaluation Board](#developmentevaluation-board-devboardevalboard)
- [Common Form Factors](#common-form-factors-)
  - [Standard Sizes](#standard-sizes)
  - [Notes on Form Factors](#notes-on-form-factors)
  - [Emerging Form Factors](#emerging-form-factors)
- [Consumer Electronics Integration](#consumer-electronics-integration-)
  - [Common Examples](#common-examples)
  - [Recycling and Repurposing](#recycling-and-repurposing)
- [Contributing](#contributing-)
- [Notes](#notes-)

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

### 🖥️ Compute Module (CM)
The core computing system of an SBC without fixed I/O, designed for integration into custom carrier boards.

Key characteristics:
- Contains the essential computing elements (CPU, RAM, storage)
- Requires a carrier board for I/O and power
- Highly flexible in terms of final implementation
- Often used in commercial products
- Same software capabilities as full SBCs
- Two common form factors:
  - SODIMM form factor (67.6 × 30 mm), as used in CM1-3
  - Custom Raspberry Pi form factor (55 × 40 mm) with standardised connectors (2× B2B 100-pin for CM4, 3× for CM5)

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
- Often in gumstick (~ 50-70 × 20 mm), cracker (~ 50 x 50mm) or stamp (~ 25 × 25 mm) form factors

Examples:
- Raspberry Pi Compute Module (on carrier board)
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

## 📏 Common Form Factors

Different board categories typically align with certain form factors:

### Standard Sizes
- Credit Card: ~85 × 56 mm (typical for SBCs like Raspberry Pi)
- Mini-ITX: 170 × 170 mm (larger SBCs)
- SODIMM: 67.6 × 30 mm (common for older Compute Modules)
- RPi CM: 55 × 40 mm (standard for newer Compute Modules)
- Gumstick: 51 × 21 mm base size, may extend to ~70 mm with Ethernet
- Stamp: ~25 × 25 mm (common for eSBCs and some ESBs)
- Cracker: 43 × 43 mm to 50 × 50 mm (emerging form factor for compact eSBCs)

### Emerging Form Factors
In 2024, a new trend emerged with ultra-compact eSBCs in a roughly square "cracker" form factor, ranging from 43 × 43 mm (Milk-V Duo S) to 50 × 50 mm (Luckfox Pico Ultra). These boards combine the capabilities of traditional eSBCs with an extremely compact footprint, positioning themselves between stamp-sized and traditional gumstick formats.

This trend represents a push towards more compact yet fully-featured Linux-capable boards, particularly in the RISC-V space where new chips are enabling smaller form factors without sacrificing capabilities.

### Notes on Form Factors
- SBCs typically stick to credit card size or larger standardised PC form factors
- Compute Modules are highly standardised in both size and connector placement
- eSBCs tend toward smaller form factors due to their headless nature
- ESBs and DevBoards can vary widely in size depending on their purpose
- Some manufacturers create their own custom form factors for specific use cases

## 📺 Consumer Electronics Integration

Many modern consumer electronics devices contain boards that align with our taxonomy categories, even though they're not marketed as such:

### Common Examples
- Smart TV mainboards are often SBCs or eSBCs, containing powerful SOCs to handle video processing, apps, and networking
- Set-top boxes and streaming devices typically use eSBC designs
- Digital signage systems often use Compute Modules or eSBCs
- Modern appliances may contain ESBs for control and connectivity
- Gaming consoles use custom-designed SBCs

### Recycling and Repurposing
Consumer electronics boards can often be repurposed. When identifying a board from a consumer device:
- If it runs full Linux and has standard display outputs (HDMI/VGA/DP/DVI) → SBC
- If it runs full Linux but only has embedded display interfaces (MIPI DSI/LVDS) → eSBC
- If it only runs a basic RTOS or firmware → ESB

This classification can help in understanding a board's capabilities and potential uses when repurposing hardware.

## 🤝 Contributing

This taxonomy is a living document. If you have suggestions for:
- Additional board categories
- New example boards
- Clarifications to definitions
- Edge cases that don't fit well

Please open an issue or submit a pull request!

## 📝 Notes

1. Some boards may blur the lines between categories or have features that span multiple categories. In these cases, consider the primary intended use case and main features.

2. This taxonomy focuses on general-purpose and development boards. Specialised boards (like AI accelerators or FPGA development boards) may need different categorisation.

3. The presence or absence of specific features (like wireless connectivity or storage) is not a primary factor in categorisation, as these can appear across all categories.

4. Compute Modules often bridge multiple categories depending on their carrier board implementation - they can become either full SBCs or eSBCs based on the carrier board design.
