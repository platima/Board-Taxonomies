# CLAUDE.md — AI Assistant Guide for Board-Taxonomies

This file provides context and conventions for AI assistants (such as Claude) working in this repository.

## Repository Overview

**Board-Taxonomies** is a pure documentation repository that defines a clear, shared vocabulary for categorising embedded computing boards. There is no application code, build system, or test suite. All meaningful content lives in `README.md`.

**Maintainer:** Platima (<kp+github@auth8.net>)
**Primary branch:** `master`
**Remote:** `http://local_proxy@127.0.0.1:35142/git/platima/Board-Taxonomies`

---

## Repository Structure

```
Board-Taxonomies/
├── README.md          # The entire taxonomy — all definitions, examples, and guidance
└── .github/
    └── FUNDING.yml    # GitHub sponsorship configuration (GitHub: platima, Patreon: Platima)
```

There are no source files, dependency manifests, Dockerfiles, or CI/CD pipelines.

---

## Purpose and Scope

The taxonomy defines five board categories used across the embedded/maker community:

| Category | Abbreviation | Key trait |
|---|---|---|
| Single Board Computer | SBC | Full OS, display output |
| Compute Module | CM | Core compute, requires carrier board |
| Embedded Single Board Computer | eSBC | Full OS, headless (no display output) |
| Embedded System Board | ESB | MCU/simple SoC, no full OS |
| Development/Evaluation Board | DevBoard / EvalBoard | Chip showcase and prototyping |

A secondary section covers common **form factors** (Credit Card, Mini-ITX, SODIMM, CM4/CM5, Gumstick, Stamp, Cracker) and a **Consumer Electronics Integration** section explains how the taxonomy maps to repurposed hardware.

The document is intentionally living — new board examples, edge-case clarifications, and emerging form factors are welcome contributions.

---

## Content Conventions

These conventions are derived from the existing README.md and must be followed for all edits.

### Markdown style
- **Headings** use emoji prefixes consistently: `🖥️` for SBC/CM, `🌐` for eSBC, `🔌` for ESB, `🛠️` for DevBoard, `📏` for form factors, `📺` for consumer electronics, `🤝` for contributing, `📝` for notes.
- Top-level sections use `##`; sub-sections use `###`.
- Bullet lists use `-` (not `*` or `+`).
- No trailing whitespace; blank lines separate sections.

### Table of Contents
- The ToC at the top of README.md uses anchor links. When adding or renaming sections, update both the heading and the corresponding ToC entry.
- Emoji characters in anchors must be URL-encoded (e.g., `🖥️` → `%EF%B8%8F`). GitHub renders these automatically, but verify the anchor works when editing manually.

### Board examples
- List specific, real product names (e.g., "Raspberry Pi Compute Module 4", not "a CM4-style board").
- Keep example lists concise — 4–6 representative boards per category is the norm.
- Do not duplicate a board across categories unless there is an explicit justification; instead, use the "Notes" section to explain dual-category cases.

### Measurements and units
- Dimensions are in **mm** (not inches).
- Width × Height order is used consistently (e.g., `85 × 56 mm`).
- Approximate sizes use `~` prefix: `~50 × 50 mm`.

### Language
Australian English in **all** documentation and commit messages.
Examples: initialise, behaviour, colour, licence, serialisation, organisation, optimise, minimise, recognise.

### Tone and voice
- Neutral, reference-document style — no marketing language.
- Present tense, third person for definitions.
- Italics (`_..._`) are used for caveats or clarifications (e.g., `_(PoE HAT compatibility untested)_`).

---

## Development Workflow

Because this is a documentation-only repository, the "development" workflow is simple:

1. **Branch** — create a `feature/<name>` or `fix/<name>` branch off `master` for non-trivial changes.
2. **Edit** `README.md` directly — there is no code generation or build step.
3. **Verify** Markdown renders correctly (headings, bullet lists, table of contents anchor links).
4. **Commit** using [Conventional Commits](https://www.conventionalcommits.org/) format:
   - `docs:` — content additions or updates (new boards, form factors, clarifications)
   - `fix:` — typo corrections, broken anchor links, formatting errors
   - `chore:` — CLAUDE.md updates, FUNDING.yml, repo housekeeping
   ```
   docs: add Milk-V Oasis to SBC examples
   fix: correct cracker form factor dimensions for Luckfox Pico Ultra
   ```
5. **Push** to the appropriate branch (see below).

There are no linters, formatters, pre-commit hooks, or tests to run.

### Branching
- `master` is the stable branch; direct pushes are acceptable for the maintainer.
- Claude sessions work on `claude/<session-id>` branches and open pull requests to `master`.

### Standard task completion checklist
Every change must complete **all** of these steps before it is considered done:

1. Edit `README.md` (and/or `CLAUDE.md` if conventions changed).
2. Verify ToC anchor links still resolve after any heading changes.
3. Commit with a Conventional Commits message (Australian English).
4. Push and open a pull request to `master` if the change is non-trivial.

---

## Guidelines for AI Assistants

### What to do
- When asked to **add a board**, place it under the most appropriate category using the decision logic in "Consumer Electronics Integration" as a guide, and follow existing list formatting.
- When asked to **add a category**, follow the established heading/emoji/list pattern and add a ToC entry.
- When asked to **add a form factor**, include approximate dimensions (mm) and at least one real-world example board.
- When editing measurements, use the same `W × H mm` notation already in use.
- Preserve all existing anchor-compatible heading text unless explicitly asked to rename a section (renaming breaks incoming links).

### What not to do
- Do not introduce code, scripts, CI configuration, or build tooling — this is intentionally a documentation-only repo.
- Do not reformat the entire document for minor edits; make surgical changes.
- Do not change the emoji used for existing section headings unless explicitly asked — they are part of the established visual identity.
- Do not remove the visitor badge (`<img>` at line 1 of README.md).
- Do not add boards that are not real, shipping products.

### Contribution pathway
All non-trivial changes (new categories, significant rewording of definitions) should be proposed via a pull request rather than committed directly to `master`, so the maintainer can review them.

---

## Key Reference: Board Classification Decision Tree

When classifying an unknown board, apply the following logic (mirroring the "Recycling and Repurposing" section):

```
Does it run a full multi-tasking OS (Linux, Windows)?
├─ YES → Does it have standard display output (HDMI / DP / DVI / VGA)?
│         ├─ YES → SBC
│         └─ NO  → eSBC (or Compute Module if it requires a carrier board)
└─ NO  → Is its primary purpose chip evaluation / demonstration?
          ├─ YES → DevBoard / EvalBoard
          └─ NO  → ESB (MCU or simple SoC, runs Arduino / MicroPython / RTOS)
```

Compute Modules are a special case: they contain the CPU/RAM/storage of an SBC but expose no direct I/O — they always require a carrier board, which then determines whether the final assembly behaves as an SBC or eSBC.
