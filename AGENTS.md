# AGENTS.md

Guidance for AI coding agents working in this repository (Claude Code, Cursor, Aider, Copilot, …).

## Project overview

A personal, slowly-growing collection of Markdown notes thinking through large open
questions — mortality, meaning, consciousness, our place in the cosmos. The name nods to
Popper's *Conjectures and Refutations*: everything here is a bold guess written to be
refuted and revised, not a settled conclusion. There is no code and no build step — the
deliverable is prose.

## Structure

- `continuity/` — Death and what (if anything) survives it: personal identity, cryonics, digital preservation.
- `cosmos/` — Our place in the universe: the Fermi paradox and its candidate resolutions.
- `meaning/` — What a life is for: purpose, value, living without guarantees.
- `mind/` — Consciousness, free will, and whether experience is what it seems.

The structure is itself a conjecture and will change as the questions do.

## Setup

None. Any Markdown editor works; there are no dependencies to install.

## Run / build / test

- **Run / build:** N/A — plain Markdown, nothing to compile.
- **Test:** N/A. (Optional: a Markdown linter such as `markdownlint` could be added later.)

## Conventions

- Every note follows the shape in `TEMPLATE.md`: **The question → Conjectures → Refutations & tensions → Where it stands → Threads to pull.** Start new notes by copying `TEMPLATE.md`.
- Each note carries a status line: `*Status: open · last touched YYYY-MM-DD*`. Update the date when you meaningfully revise a note.
- Tone is thinking-in-progress, not conclusions. Prefer "my best current guess" over confident assertion; the point is the refutations.
- Filenames: lowercase kebab-case `.md` (e.g. `fermi-paradox.md`), placed in the topic folder that fits.
- Commit messages: short, present-tense, describing the change to the notes (e.g. `add fermi-paradox conjecture`, `revise meaning: where-it-stands`).
