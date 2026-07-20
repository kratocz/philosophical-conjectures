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
- `religion/` — Faith examined from outside: scripture against checkable evidence, and what makes a religion dangerous.

The structure is itself a conjecture and will change as the questions do.

## Setup

None. Any Markdown editor works; there are no dependencies to install.

## Run / build / test

- **Run / build:** N/A — plain Markdown, nothing to compile.
- **Test:** N/A. (Optional: a Markdown linter such as `markdownlint` could be added later.)

## Conventions

- Every note follows the shape in `TEMPLATE.md`: **The question → Conjectures → Refutations & tensions → Where it stands → Threads to pull → Sources.** Start new notes by copying `TEMPLATE.md`. The Sources section is optional for purely conceptual notes and expected for any note leaning on checkable facts.
- Each note carries a status line: `*Status: open · last touched YYYY-MM-DD · sources checked YYYY-MM-DD*`. The two dates mean different things and drift apart on purpose — **last touched** is when the prose changed, **sources checked** is when the empirical claims were last verified against sources. Update each when you do that particular thing.
- Tone is thinking-in-progress, not conclusions. Prefer "my best current guess" over confident assertion; the point is the refutations.
- **Never cite from memory.** Verify a source exists and actually says what it is being cited for, or mark it unverified in the note. A confabulated citation is worse than none, because it borrows authority it hasn't earned.
- **Two kinds of error need two different habits.** A claim can be *untrue* (the inscription is not on the wall) or merely *stale* (the settlement timescale was superseded, the open question was answered). Untrue is caught once and fixed forever; stale returns without anyone writing a false word. So mark perishable claims — prices, survey data, "no one has yet done X," anything about the state of the art — with an inline `(as of YYYY-MM)`, and treat the `sources checked` date as the note's expiry warning.
- **Record what the sourcing cost you.** When a source corrects a claim, refuses the use you wanted, or forces a conclusion to weaken, write that into the note rather than silently editing around it. Withdrawn claims stay visible, with the reason. This is the Popperian point of the project made concrete: a note that only shows its wins isn't a conjecture, it's a pitch.
- Filenames: lowercase kebab-case `.md` (e.g. `fermi-paradox.md`), placed in the topic folder that fits.
- Commit messages: short, present-tense, describing the change to the notes (e.g. `add fermi-paradox conjecture`, `revise meaning: where-it-stands`).
