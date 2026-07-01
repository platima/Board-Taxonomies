<img align="right" src="https://visitor-badge.laobi.icu/badge?page_id=platima.boardtaxonomies" height="20" />

# 🔧 Board Taxonomy Definitions

This repository provides definitions and examples for different categories of embedded computing boards. The goal is to establish clear terminology for discussing and categorising various types of development boards, single-board computers, and embedded platforms.

_**Last Updated:** 2026-07-02_

## 📑 Table of Contents
- [Categories](#categories)
  - [Single Board Computer (SBC)](#%EF%B8%8F-single-board-computer-sbc)
  - [Compute Module / System-on-Module (CM/SoM)](#%EF%B8%8F-compute-module--system-on-module-cmsom)
  - [Embedded Single Board Computer (eSBC)](#-embedded-single-board-computer-esbc)
  - [Embedded System Board (ESB)](#-embedded-system-board-esb)
  - [Development/Evaluation Board](#%EF%B8%8F-developmentevaluation-board-devboardevalboard)
  - [AI/ML Accelerator Board](#-aiml-accelerator-board)
- [Classification Guide](#%EF%B8%8F-classification-guide)
  - [Decision Tree](#decision-tree)
  - [Worked Example: Classifying the Milk-V Duo S](#worked-example-classifying-the-milk-v-duo-s)
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
- Has standard display output (HDMI, DisplayPort, DVI) backed by a 3D-capable GPU for desktop graphics
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
- Libre Computer Le Potato
- Milk-V Mars
- Pine64 ROCK64
- SpacemiT Muse Pi Pro
- Milk-V Oasis (RISC-V, Mini-ITX)

### 🖥️ Compute Module / System-on-Module (CM/SoM)
The core computing system without fixed I/O, designed for integration into custom carrier boards. The terms "Compute Module" and "System-on-Module" are used interchangeably in the industry with no meaningful technical distinction.

Key characteristics:
- Contains the essential computing elements (CPU, RAM, storage, often power management)
- Requires a carrier board for I/O and power delivery
- Highly flexible in terms of final implementation
- Used in both prototyping and production deployments
- Same software capabilities as full SBCs
- May include additional peripherals (WiFi, Bluetooth, etc.)
- Organised by connector/form factor standards

**CM4/CM5 Connector Standard** (emerging de facto standard):
- **CM4 format**: 2× 100-pin B2B connectors, 55 × 40 mm
- **CM5 format**: 3× 100-pin B2B connectors, 55 × 40 mm (backward compatible with CM4 carriers for basic I/O)
- Broad ecosystem support with many compatible carrier boards available
- Examples: Raspberry Pi CM4/CM5, Radxa CM3/CM4/CM5, Orange Pi CM5, Milk-V Mars CM, Pine64 SOQuartz

**SODIMM Form Factor** (67.6 × 30 mm, laptop memory connector):
- Established standard with wide industrial adoption
- Examples: Raspberry Pi CM1-3/CM4S, Pine64 SOPINE, Toradex Colibri/Apalis, many industrial modules

**Custom Connector Implementations**:
- Proprietary or manufacturer-specific connector designs
- Examples: NVIDIA Jetson modules, Variscite VAR-SOM, Phytec phyCORE, Boundary Devices Nitrogen, Debix SOM, Intel NUC compute elements

### 🌐 Embedded Single Board Computer (eSBC)
Similar to an SBC but designed for headless or embedded display operation. The key differentiator is the lack of GPU capabilities for general computing.

Key characteristics:
- Runs full multi-tasking operating systems (requires MMU-equipped processor)
- Either no display output, only embedded display interfaces (MIPI DSI, LVDS), or display output driven by a VPU or 2D hardware engine — but no 3D-capable GPU
- _A VPU or hardware 2D engine driving HDMI for HMI applications does not qualify as a GPU for SBC classification_
- May have ISP (Image Signal Processor) for camera processing but not general-purpose graphics
- Accessed via SSH, UART, or similar for headless variants
- Often used in embedded applications (IoT gateways, industrial controllers, camera systems)
- May have reduced I/O compared to full SBCs
- Often in gumstick (~50-70 × 20 mm), cracker (~50 × 50 mm) or stamp (~25 × 25 mm) form factors

Examples:
- Pine64 Ox64
- Milk-V Duo S
- Luckfox Pico Pro
- Luckfox Lyra (RV3506G2 — HDMI via VPU for HMI, no 3D GPU)
- Many industrial Linux boards (headless variants without GPU)

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

**FPGA Development Boards** _(special case — see [Notes](#-notes))_:
- BeagleBone BeagleV-Fire
- Xilinx/AMD development boards (Zynq, Artix, Kintex series)
- Intel/Altera DE-series boards
- Lattice iCE40 boards
- Digilent Arty, Basys, Nexys boards
- Terasic DE10-Nano

### 🤖 AI/ML Accelerator Board
Specialised boards with dedicated AI/ML acceleration hardware, designed for inference or training workloads.

Key characteristics:
- Contains specialised AI/ML accelerators (NPU, TPU, or AI coprocessors)
- Optimised for neural network inference or training
- May be standalone boards or companion accelerators
- Often includes a host processor (ARM, x86) alongside accelerator
- Typically runs Linux with AI frameworks (TensorFlow, PyTorch, etc.)
- Focus on performance-per-watt for AI workloads
- May support specific model formats (ONNX, TensorFlow Lite, etc.)

Examples:
- Google Coral Dev Board (Edge TPU)
- NVIDIA Jetson Nano/Xavier/Orin (GPU + tensor core AI acceleration)
- BeagleBone AI-64 (TDA4VM with C7x DSP + MMA for AI)
- Canaan CanMV-K230 (RISC-V with KPU neural network accelerator)

## 🗺️ Classification Guide

This section helps you determine which category a board belongs to, especially for edge cases.

### Decision Tree

Follow this flowchart to classify a board:

1. **Is AI/ML acceleration the primary purpose?**
   - Yes → **AI/ML Accelerator Board**
   - No → Continue

2. **Is it designed primarily to evaluate a specific chip?**
   - Yes → **Development/Evaluation Board** _(includes FPGA development boards — see [Notes](#-notes))_
   - No → Continue

3. **Does it have an MMU-capable processor?**
   - No → **Embedded System Board (ESB)**
   - Yes → Continue

4. **Does it require a carrier/base board for basic I/O?**
   - Yes → **Compute Module / System-on-Module (CM/SoM)**
   - No → Continue

5. **Does it have a 3D-capable GPU for desktop graphics?**
   - Yes → **Single Board Computer (SBC)**
   - No → **Embedded Single Board Computer (eSBC)**

### Worked Example: Classifying the Milk-V Duo S

Step-by-step classification of the Milk-V Duo S (SG2000 SoC, Linux-capable, MIPI CSI, no HDMI):

1. **AI/ML acceleration primary purpose?** No — it is a general Linux board. Continue.
2. **Chip evaluation / demonstration?** No — it is a production-ready eSBC. Continue.
3. **MMU-capable processor?** Yes — the SG2000 runs Linux with full MMU. Continue.
4. **Requires carrier board?** No — it is standalone. Continue.
5. **3D-capable GPU?** No — the SG2000 has no 3D GPU; display is via MIPI DSI only, driven by a 2D engine. → **eSBC**

Result: **Embedded Single Board Computer (eSBC)** — cracker form factor (43 × 43 mm).

### Technical Differentiators

Key technical aspects that define categories:

| Feature | SBC | CM/SoM | eSBC | ESB | Dev/Eval | AI/ML |
|---------|-----|--------|------|-----|----------|-------|
| **MMU** | ✓ | ✓ | ✓ | ✗ | Varies | ✓ |
| **3D GPU** | ✓ | ✓ | ✗ | ✗ | Varies | Optional |
| **Full OS** | ✓ | ✓ | ✓ | ✗ | Varies | ✓ |
| **Display Out** | ✓ | Via carrier | ✗/Embedded | ✗ | Varies | Optional |
| **Standalone** | ✓ | ✗ | ✓ | ✓ | ✓ | ✓ |
| **Production Ready** | ✓ | ✓ | ✓ | ✓ | ✗ | ✓ |

### Edge Cases and Overlapping Categories

Some boards span multiple categories or present classification challenges:

**Compute Module/SoM on Carrier Board:**
- The module itself is classified as **CM/SoM**
- However, the complete system (module + carrier) can be described as:
  - **SBC** if the carrier provides GPU-equipped display outputs (e.g., CM4 on official I/O board with HDMI)
  - **eSBC** if the carrier is headless or only has embedded display outputs
- Classification depends on the complete system configuration

**Boards with Multiple Purposes:**
- NVIDIA Jetson series can be classified as:
  - **CM/SoM** (when referring to the module alone)
  - **AI/ML Accelerator** (when emphasis is on GPU/AI capabilities of the complete system)
  - **SBC** (when the complete system is used as a general-purpose computer)
- Use the context and primary intended use case for classification

**Development vs. Production:**
- Many ESBs (like Arduino or Pico) are used in both development and production
- DevBoards are primarily for evaluation, not deployment
- The distinction is about intent and features, not actual usage

**SBC vs. eSBC Ambiguity:**
- The key differentiator is a 3D-capable GPU, not merely the presence of a display connector
- Boards with both HDMI and MIPI DSI outputs → Classify by GPU presence
- If it has a 3D-capable GPU and can render a composited desktop GUI → **SBC**
- If display output is driven by a VPU, 2D hardware engine, or framebuffer without 3D acceleration → **eSBC**
- Example: a board with HDMI driven by a VPU for HMI applications (e.g. Luckfox Lyra with RV3506G2) → **eSBC**, not SBC

**SBC + AI/ML Accelerator Combos (e.g., Raspberry Pi 5 AI Kit):**
- A standard SBC fitted with an M.2 or HAT-based AI/ML accelerator (e.g., Hailo-8L) becomes a dual-category system
- Primary classification of the base board remains **SBC**
- The complete system (board + accelerator) may also be described as an **AI/ML Accelerator** when the inference workload is the primary use case
- Classify by the component being referenced, not the complete system

**RTOS Capabilities:**
- Modern RTOSes (Zephyr, NuttX) are increasingly capable
- The key differentiator is MMU support, not OS sophistication
- If it lacks MMU → **ESB**, regardless of RTOS features

**Hybrid Boards:**
- STM32MP1 boards (MCU + MPU in one chip) → Classify by primary processor
- RP2040 with Linux (via emulation/PIO tricks) → Still **ESB** (no true MMU)
- Boards with AI accelerators (BeagleBone AI-64, RK3588 boards) → **SBC** if they have MMU/GPU, can also be classified as **AI/ML Accelerator** depending on emphasis

## 📏 Common Form Factors

Different board categories typically align with certain form factors:

### Standard Sizes
- **Credit Card**: 85.6 × 53.98 mm (ISO/IEC 7810 ID-1 standard)
- **Mini-ITX**: 170 × 170 mm (PC industry standard)
- **SODIMM**: 67.6 × 30 mm (laptop memory module standard)
- **CM4 / CM5**: 55 × 40 mm (Raspberry Pi Compute Module standard)
- **Gumstick**: 51 × 21 mm base size, may extend to ~70 mm with Ethernet
- **Stamp**: ~25 × 25 mm (ultra-compact modules)
- **Cracker**: 43 × 43 mm to 50 × 50 mm (emerging square format; e.g., Milk-V Duo S at 43 × 43 mm, Luckfox Pico Ultra at 50 × 50 mm _(PoE HAT compatibility untested)_)

### Emerging Form Factors

The "cracker" form factor emerged around 2019 (based on market research and Google Trends data) with ultra-compact eSBCs in a square format, starting at 43 × 43 mm. This became more standardised in 2024 with the Milk-V Duo S, which also established a common PoE HAT header pin positioning. A larger variant at 50 × 50 mm appeared with the Luckfox Pico Ultra _(PoE HAT compatibility untested)_.

These boards combine the capabilities of traditional eSBCs with an extremely compact footprint, positioning themselves between stamp-sized and traditional gumstick formats. This trend represents a push towards more compact yet fully-featured Linux-capable boards, particularly in the RISC-V space where new chips are enabling smaller form factors without sacrificing capabilities.

### Form Factor Associations by Category

While any category can theoretically use any form factor, certain patterns are common:

**SBCs** typically use:
- Credit card size (85.6 × 53.98 mm) - Most common
- Mini-ITX (170 × 170 mm) - For high-performance variants
- Custom sizes based on PC standards

**Compute Modules / System-on-Modules** have emerging standards:
- **CM4/CM5 (55 × 40 mm)** - Emerging de facto standard with broad compatibility
- **SODIMM (67.6 × 30 mm)** - Established industrial standard
- **Custom implementations** - Vary widely with proprietary connectors (LGA, castellated edges, B2B)
- Connector standardisation is more important than physical size
- Size depends on feature set and target application

**eSBCs** trend toward compact formats:
- Gumstick (51-70 × 20 mm) - Very common
- Cracker (43-50 × 50 mm) - Emerging standard
- Stamp (~25 × 25 mm) - Ultra-compact
- Custom compact sizes

**ESBs** have the widest variety:
- Arduino form factors (various standardised sizes)
- Feather/PICO formats (~51 × 21 mm)
- Custom sizes based on ecosystem (Teensy, etc.)
- From tiny (< 20 × 20 mm) to large (> 100 × 70 mm)

**Dev/Eval Boards** are rarely standardised:
- Sized to expose all chip functionality
- Often larger to include debugging features
- May include expansion headers and test points

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
- If it runs full Linux (has MMU) and has a 3D-capable GPU with standard display outputs (HDMI/VGA/DP/DVI) → **SBC**
- If it runs full Linux (has MMU) but only has embedded display interfaces (MIPI DSI/LVDS), or display output is VPU/2D-only without a 3D GPU → **eSBC**
- If it only runs a basic RTOS or firmware (no MMU) → **ESB**
- If it has specialised AI/ML hardware and that's the primary function → **AI/ML Accelerator**

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

4. **Compute Modules/SoMs and Carrier Boards**: CM/SoM modules bridge multiple categories depending on their carrier board implementation - the complete system can function as an SBC, eSBC, or specialised device based on the carrier board design.

5. **Living Document**: This taxonomy evolves with the industry. Check the [CHANGELOG.md](CHANGELOG.md) for updates and revisions to definitions.

6. **FPGA Boards**: Field-Programmable Gate Arrays are reconfigurable hardware — the silicon has no fixed function until programmed with an HDL design. FPGA-based development boards are therefore classified at the hardware level as a specialised type of Development/Evaluation Board. The functional characteristics of any specific FPGA design loaded onto such a board (which may emulate an SBC, eSBC, ESB, or any other category) are outside the scope of this taxonomy. Classify the *board*, not the *loaded design*.

7. **License**: This taxonomy is available under the [MIT License](LICENSE), making it free to use, modify, and distribute.
