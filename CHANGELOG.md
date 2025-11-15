# Changelog

All notable changes to the Board Taxonomies will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## [Unreleased]

### Added
- MIT License
- Contributing guidelines (CONTRIBUTING.md)
- Code of Conduct (CODE_OF_CONDUCT.md)
- This changelog
- FPGA Development Board category
- AI/ML Accelerator Board category
- Classification decision tree
- Edge cases and overlapping categories section
- GitHub issue templates
- Additional board examples across all categories (based on real-world testing)

### Changed
- **Merged Compute Module (CM) and System-on-Module (SoM)** into single category "CM/SoM"
  - Organized by connector standards (CM4/CM5, SODIMM, Custom) instead of artificial market distinction
  - Acknowledges these terms are used interchangeably in the industry
  - Highlights CM4/CM5 as emerging de facto standard with broad compatibility
- Clarified eSBC display output requirements (no GPU vs. has GPU)
- Fixed form factor dimension inconsistencies (credit card size)
- Improved carrier board classification examples
- Enhanced OS classification criteria (MCU/SOC, MMU, GPU-based)
- Reorganized form factor section to note common associations while maintaining flexibility
- Added reference to 2019 cracker form factor trend origin
- Fixed broken Table of Contents links
- Updated board examples: Raspberry Pi Pico 2, BeagleV-Fire, ESP32-P4-Function-EV-Board, and many others

### Fixed
- Corrected credit card dimensions to standard 85.6 × 53.98 mm
- Removed LattePanda Alpha and BeagleBone AI-64 from eSBC examples (both have GPUs, should be classified as SBC)
- Removed conflicting Raspberry Pi Compute Module example from eSBC category

## [1.0.0] - 2025-01-14

### Added
- Initial taxonomy with five main categories:
  - Single Board Computer (SBC)
  - Compute Module (CM)
  - Embedded Single Board Computer (eSBC)
  - Embedded System Board (ESB)
  - Development/Evaluation Board
- Common form factors section
- Consumer electronics integration section
- Contributing section
- Board examples for each category

[Unreleased]: https://github.com/platima/Board-Taxonomies/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/platima/Board-Taxonomies/releases/tag/v1.0.0
