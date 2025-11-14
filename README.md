<img align="right" src="https://visitor-badge.laobi.icu/badge?page_id=platima.boardtaxonomies" height="20" />

# 🔧 Board Taxonomy Definitions

This repository provides definitions and examples for different categories of embedded computing boards. The goal is to establish clear terminology for discussing and categorising various types of development boards, single-board computers, and embedded platforms.

## 📑 Table of Contents
- [Categories](#categories)
  - [Single Board Computer (SBC)](#-single-board-computer-sbc)
  - [Compute Module (CM)](#-compute-module-cm)
  - [System-on-Module (SoM)](#-system-on-module-som)
  - [Embedded Single Board Computer (eSBC)](#-embedded-single-board-computer-esbc)
  - [Embedded System Board (ESB)](#-embedded-system-board-esb)
  - [Development/Evaluation Board](#-developmentevaluation-board-devboardevalboard)
  - [FPGA Development Board](#-fpga-development-board)
  - [AI/ML Accelerator Board](#-aiml-accelerator-board)
- [Classification Guide](#-classification-guide)
  - [Decision Tree](#decision-tree)
  - [Technical Differentiators](#technical-differentiators)
  - [Edge Cases and Overlapping Categories](#edge-cases-and-overlapping-categories)
- [Common Form Factors](#-common-form-factors)
  - [Standard Sizes](#standard-sizes)
  - [Emerging Form Factors](#emerging-form-factors)
  - [Form Factor Associations by Category](#form-factor-associations-by-category)
- [Consumer Electronics Integration](#-consumer-electronics-integration)
  - [Common Examples](#common-examples)
  - [Recycling and Repurposing](#recycling-and-repurposing)
- [Contributing](#-contributing)
- [Notes](#-notes)

## Categories

### 🖥️ Single Board Computer (SBC)
A complete computer system implemented on a single board, capable of running a full operating system like Linux or Windows.

Key characteristics:
- Runs full multi-tasking operating systems (requires MMU-equipped processor)
- Has display output with GPU capabilities (HDMI, DisplayPort, DVI, etc.)
- Generally includes standard PC interfaces (USB, network, etc.)
- May be lower power than traditional PCs
- Complete system on a single board
- Typically credit card sized (85.6 × 53.98 mm) or up to Mini-ITX (170 × 170 mm)

Examples:
- Raspberry Pi 2/3/4/5
- BeagleBone Black
- Radxa Rock 4 SE
- Orange Pi 4 Pro
- Banana Pi BPi-M4
- Libre Competer Le Potato
- Milk-V Mars
- Pine64 ROCK64
- SpacemiT Muse Pi Pro

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
- NVIDIA Jetson modules (in some variants)
- Radxa CM3/CM4
- Orange Pi CM5
- Pine64 SOQuartz
- Milk-V Mars CM

### 🔧 System-on-Module (SoM)
A complete computing system in a compact, production-ready module designed for integration into end products. Unlike Compute Modules which are often development-focused with proprietary connectors, SoMs typically use standardized interfaces.

Key characteristics:
- Contains CPU, RAM, storage, and power management
- Uses standardized connectors (often castellated edges, LGA, or standard headers)
- Designed specifically for production deployment, not development
- May include additional peripherals (WiFi, Bluetooth, etc.)
- Often certified for specific regulations (FCC, CE, etc.)
- Carrier board provides application-specific I/O
- Usually comes with long-term availability guarantees

Examples:
- Variscite VAR-SOM series
- NVIDIA Jetson modules (in SoM variants)
- Toradex Colibri/Apalis modules
- Phytec phyCORE modules
- Boundary Devices Nitrogen SoMs
- Intel NUC compute elements

### 🌐 Embedded Single Board Computer (eSBC)
Similar to an SBC but designed for headless or embedded display operation. The key differentiator is the lack of GPU capabilities for general computing.

Key characteristics:
- Runs full multi-tasking operating systems (requires MMU-equipped processor)
- Either no display output, or only embedded display interfaces (MIPI DSI, LVDS) without GPU
- May have ISP (Image Signal Processor) for camera processing but not general-purpose graphics
- Accessed via SSH, UART, or similar for headless variants
- Often used in embedded applications (IoT gateways, industrial controllers, camera systems)
- May have reduced I/O compared to full SBCs
- Often in gumstick (~50-70 × 20 mm), cracker (~50 × 50 mm) or stamp (~25 × 25 mm) form factors

Examples:
- Pine64 Ox64
- Milk-V Duo S
- Luckfox Pico Pro
- LattePanda Alpha (headless version)
- BeagleBone AI-64 (when used headless)
- Many industrial Linux boards

### 🔌 Embedded System Board (ESB)
General-purpose boards built around an MCU (microcontroller) or simple SOC without MMU, designed for embedded applications.

Key characteristics:
- Based on microcontroller or simple system-on-chip (typically without MMU)
- Cannot run full multi-tasking operating systems like Linux
- Typically runs bare-metal firmware, Arduino, MicroPython, or RTOS (FreeRTOS, Zephyr, etc.)
- May have real-time capabilities due to simpler architecture
- Designed for both development and deployment
- Part of a broader development ecosystem
- Lower power consumption than SBC/eSBC counterparts

Examples:
- Raspberry Pi Pico 2
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
- ESP32-P4-Function-EV-Board
- Microchip PIC development boards
- NXP evaluation boards

### 🔲 FPGA Development Board
Boards built around Field-Programmable Gate Arrays, allowing hardware-level programmability and parallel processing.

Key characteristics:
- Centered around an FPGA chip (Xilinx, Intel/Altera, Lattice, etc.)
- Hardware is reconfigurable at the logic gate level
- Used for custom digital logic, hardware acceleration, and prototyping
- Often includes additional peripherals for interfacing
- May include ARM cores embedded in the FPGA (SoC FPGAs)
- Requires specialized development tools (Vivado, Quartus, etc.)
- Used in signal processing, hardware emulation, and custom computing

Examples:
- BeagleBone BeagleV-Fire
- Xilinx/AMD development boards (Zynq, Artix, Kintex series)
- Intel/Altera DE-series boards
- Lattice iCE40 boards
- Digilent Arty, Basys, Nexys boards
- Terasic DE10-Nano

### 🤖 AI/ML Accelerator Board
Specialized boards with dedicated AI/ML acceleration hardware, designed for inference or training workloads.

Key characteristics:
- Contains specialized AI/ML accelerators (NPU, TPU, or AI coprocessors)
- Optimized for neural network inference or training
- May be standalone boards or companion accelerators
- Often includes a host processor (ARM, x86) alongside accelerator
- Typically runs Linux with AI frameworks (TensorFlow, PyTorch, etc.)
- Focus on performance-per-watt for AI workloads
- May support specific model formats (ONNX, TensorFlow Lite, etc.)

Examples:
- Google Coral Dev Board
- NVIDIA Jetson Nano/Xavier/Orin (with emphasis on AI features)
- Intel Neural Compute Stick (USB accelerator)
- Hailo-8 AI accelerator boards
- Rockchip RK3588-based boards (with NPU)
- BeagleBone AI-64 (with C7x DSP for AI)

## 🗺️ Classification Guide

This section helps you determine which category a board belongs to, especially for edge cases.

### Decision Tree

Follow this flowchart to classify a board:

1. **Does it have an FPGA as the primary component?**
   - Yes → **FPGA Development Board**
   - No → Continue

2. **Is AI/ML acceleration the primary purpose?**
   - Yes → **AI/ML Accelerator Board**
   - No → Continue

3. **Is it designed primarily to evaluate a specific chip?**
   - Yes → **Development/Evaluation Board**
   - No → Continue

4. **Does it have an MMU-capable processor?**
   - No → **Embedded System Board (ESB)**
   - Yes → Continue

5. **Does it require a carrier/base board for basic I/O?**
   - Yes → Check if it's designed for production or development:
     - Production-focused with standardized connectors → **System-on-Module (SoM)**
     - Development-focused with proprietary connectors → **Compute Module (CM)**
   - No → Continue

6. **Does it have GPU capabilities for general-purpose graphics?**
   - Yes → **Single Board Computer (SBC)**
   - No → **Embedded Single Board Computer (eSBC)**

### Technical Differentiators

Key technical aspects that define categories:

| Feature | SBC | CM | SoM | eSBC | ESB | Dev/Eval | FPGA | AI/ML |
|---------|-----|----|----|------|-----|----------|------|-------|
| **MMU** | ✓ | ✓ | ✓ | ✓ | ✗ | Varies | N/A | ✓ |
| **GPU** | ✓ | ✓ | ✓ | ✗ | ✗ | Varies | N/A | Optional |
| **Full OS** | ✓ | ✓ | ✓ | ✓ | ✗ | Varies | Optional | ✓ |
| **Display Out** | ✓ | ✓ | ✓ | ✗/Embedded | ✗ | Varies | Optional | Optional |
| **Standalone** | ✓ | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ | ✓ |
| **Production Ready** | ✓ | Optional | ✓ | ✓ | ✓ | ✗ | ✗ | ✓ |

### Edge Cases and Overlapping Categories

Some boards span multiple categories or present classification challenges:

**Compute Module on Carrier Board:**
- CM4 on official I/O board with HDMI → Functions as **SBC**
- CM4 on headless carrier board → Functions as **eSBC**
- Classification depends on the carrier board implementation

**Boards with Multiple Purposes:**
- NVIDIA Jetson series can be classified as:
  - **AI/ML Accelerator** (when focus is on GPU/AI capabilities)
  - **SBC** (when used as general-purpose computer)
  - **SoM** (in production deployments)
- Use the primary intended use case for classification

**Development vs. Production:**
- Many ESBs (like Arduino or Pico) are used in both development and production
- DevBoards are primarily for evaluation, not deployment
- The distinction is about intent and features, not actual usage

**SBC vs. eSBC Ambiguity:**
- Boards with both HDMI and MIPI DSI outputs → Classify by GPU presence
- If it can render a desktop GUI → **SBC**
- If it only outputs framebuffer without 3D/2D acceleration → **eSBC**

**RTOS Capabilities:**
- Modern RTOSes (Zephyr, NuttX) are increasingly capable
- The key differentiator is MMU support, not OS sophistication
- If it lacks MMU → **ESB**, regardless of RTOS features

**Hybrid Boards:**
- STM32MP1 boards (MCU + MPU in one chip) → Classify by primary processor
- RP2040 with Linux (via emulation/PIO tricks) → Still **ESB** (no true MMU)
- BeagleBone AI-64 → **SBC** (has MMU/GPU) but can also be **AI/ML Accelerator**

## 📏 Common Form Factors

Different board categories typically align with certain form factors:

### Standard Sizes
- **Credit Card**: 85.6 × 53.98 mm (ISO/IEC 7810 ID-1 standard)
- **Mini-ITX**: 170 × 170 mm (PC industry standard)
- **SODIMM**: 67.6 × 30 mm (laptop memory module standard)
- **CM4 / CM5**: 55 × 40 mm (Raspberry Pi Compute Module standard)
- **Gumstick**: 51 × 21 mm base size, may extend to ~70 mm with Ethernet
- **Stamp**: ~25 × 25 mm (ultra-compact modules)
- **Cracker**: 43 × 43 mm to 50 × 50 mm (emerging square format)

### Emerging Form Factors

The "cracker" form factor emerged around 2019 (based on market research and Google Trends data) with ultra-compact eSBCs in a square format, starting at 43 × 43 mm. This became more standardized in 2024 with the Milk-V Duo S, which also established a common PoE HAT header pin positioning. A larger variant at 50 × 50 mm appeared with the Luckfox Pico Ultra _(PoE HAT compatibility untested)_.

These boards combine the capabilities of traditional eSBCs with an extremely compact footprint, positioning themselves between stamp-sized and traditional gumstick formats. This trend represents a push towards more compact yet fully-featured Linux-capable boards, particularly in the RISC-V space where new chips are enabling smaller form factors without sacrificing capabilities.

### Form Factor Associations by Category

While any category can theoretically use any form factor, certain patterns are common:

**SBCs** typically use:
- Credit card size (85.6 × 53.98 mm) - Most common
- Mini-ITX (170 × 170 mm) - For high-performance variants
- Custom sizes based on PC standards

**Compute Modules** are highly standardized:
- SODIMM (67.6 × 30 mm) - Older standard
- CM4/CM5 (55 × 40 mm) - Modern standard
- Proprietary sizes with standardized connectors

**System-on-Modules** vary widely:
- Often use standardized connectors rather than standardized sizes
- LGA, castellated edges, or board-to-board connectors
- Size depends on feature set and target application

**eSBCs** trend toward compact formats:
- Gumstick (51-70 × 20 mm) - Very common
- Cracker (43-50 × 50 mm) - Emerging standard
- Stamp (~25 × 25 mm) - Ultra-compact
- Custom compact sizes

**ESBs** have the widest variety:
- Arduino form factors (various standardized sizes)
- Feather/PICO formats (~51 × 21 mm)
- Custom sizes based on ecosystem (Teensy, etc.)
- From tiny (< 20 × 20 mm) to large (> 100 × 70 mm)

**Dev/Eval Boards** are rarely standardized:
- Sized to expose all chip functionality
- Often larger to include debugging features
- May include expansion headers and test points

**FPGA Boards** vary by application:
- Development boards: Often large (100+ mm) with many connectors
- SoM variants: Compact with high-density connectors

**AI/ML Accelerators** follow SBC patterns:
- Standalone: Credit card to Mini-ITX sizes
- Accelerator modules: PCIe cards, M.2, or USB dongles

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
- If it runs full Linux (has MMU) and has GPU with standard display outputs (HDMI/VGA/DP/DVI) → **SBC**
- If it runs full Linux (has MMU) but only has embedded display interfaces (MIPI DSI/LVDS) or no GPU → **eSBC**
- If it only runs a basic RTOS or firmware (no MMU) → **ESB**
- If it has specialized AI/ML hardware and that's the primary function → **AI/ML Accelerator**

This classification can help in understanding a board's capabilities and potential uses when repurposing hardware.

**Example Classifications:**
- Smart TV mainboard with HDMI and Android → **SBC**
- IP camera board with MIPI DSI and Linux → **eSBC**
- Washing machine control board → **ESB**
- Security camera with NPU for object detection → **AI/ML Accelerator** or **eSBC** (depending on emphasis)

## 🤝 Contributing

This taxonomy is a living document. We welcome contributions! If you have suggestions for:
- Additional board categories
- New example boards
- Clarifications to definitions
- Edge cases that don't fit well
- Form factor updates
- Classification corrections

Please see our [Contributing Guidelines](CONTRIBUTING.md) for detailed information on how to contribute. All contributors are expected to abide by our [Code of Conduct](CODE_OF_CONDUCT.md).

Quick links:
- [Report an issue](https://github.com/platima/Board-Taxonomies/issues/new/choose)
- [Submit a pull request](https://github.com/platima/Board-Taxonomies/pulls)
- [View changelog](CHANGELOG.md)

## 📝 Notes

1. **Overlapping Categories**: Some boards may blur the lines between categories or have features that span multiple categories. See the [Edge Cases and Overlapping Categories](#edge-cases-and-overlapping-categories) section for guidance. When in doubt, classify by the primary intended use case.

2. **Technical Differentiators**: The key technical factors for classification are:
   - **MMU presence** (can it run full Linux?)
   - **GPU capabilities** (can it render desktop GUI?)
   - **Standalone vs. modular** (does it need a carrier board?)
   - **Primary purpose** (evaluation, production, development, acceleration?)

3. **Form Factor Flexibility**: The presence or absence of specific features (like wireless connectivity or storage) is not a primary factor in categorisation, as these can appear across all categories. Form factors are guidelines, not strict rules.

4. **Compute Modules and Carrier Boards**: Compute Modules and System-on-Modules bridge multiple categories depending on their carrier board implementation - they can become SBCs, eSBCs, or specialized devices based on the carrier board design.

5. **Living Document**: This taxonomy evolves with the industry. Check the [CHANGELOG.md](CHANGELOG.md) for updates and revisions to definitions.

6. **License**: This taxonomy is available under the [MIT License](LICENSE), making it free to use, modify, and distribute.
