# TODO

Tracked tasks and known gaps for the Board-Taxonomies repository.

## Near-term

- [ ] Verify GitHub anchor links render correctly after emoji-heading ToC fix (`%EF%B8%8F-` prefix for headings using `🖥️`, `🛠️`, `🗺️`) — manual check required on GitHub after push
- [x] Tag `v1.1.0` release on GitHub after pi-implementation PR is merged
- [x] Add `.gitattributes` to normalise line endings across platforms

## Content additions

- [x] Add Milk-V Oasis to SBC examples (Mini-ITX form factor, RISC-V)
- [x] Add Luckfox Pico Ultra dimensions note (50 × 50 mm cracker, PoE HAT compatibility needs testing)
- [x] Clarify Raspberry Pi 5 AI Kit classification (SBC + AI/ML Accelerator dual-category edge case)
- [ ] Consider adding a "Peripheral/Accelerator" sub-type for USB/PCIe/M.2 dongles (Coral, Hailo, Intel NCS) that are not standalone boards — deferred pending taxonomy design discussion

## Documentation

- [x] Add a real-world classification walkthrough example (Milk-V Duo S, step-by-step through Decision Tree)
- [x] Cross-reference CLAUDE.md decision tree with README Classification Guide — CLAUDE.md updated to match 5-step README tree

## Housekeeping

- [x] Review whether `Board-Taxonomies.code-workspace` should be tracked or added to `.gitignore` — **deliberate choice: keep tracked** (shared workspace config)
- [ ] Create a GitHub Discussions category for community classification questions (complement to issue templates)
