# AGENTS.md

Guidance for AI coding agents working in this repository (Claude Code, Cursor, Aider, Copilot, …).

## Project overview

A personal, slowly-growing collection of Markdown notes thinking through large open
questions — mortality, meaning, consciousness, our place in the cosmos. A folder can be
declared before its first note lands — `mind/` currently awaits its first. The name nods to
Popper's *Conjectures and Refutations*: everything here is a bold guess written to be
refuted and revised, not a settled conclusion. There is no code and no build step — the
deliverable is prose.

## Structure

- `continuity/` — Death and what (if anything) survives it: personal identity, cryonics, digital preservation.
- `cosmos/` — Our place in the universe: the Fermi paradox, the Great Filter, and their candidate resolutions.
- `meaning/` — What a life is for: purpose, value, living without guarantees.
- `mind/` — Consciousness, free will, and whether experience is what it seems.
- `reality/` — How the world is wired: determinism, chance, the nature of physical law, and what physics can and cannot decide.
- `religion/` — Faith examined from outside: scripture against checkable evidence, and what makes a religion dangerous.
- `war/` — The ethics of war: aggression, defense, prolongation, and third-party duties, tested on the war in Ukraine.

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
- **English is canonical; translations mirror it.** All notes and `README.md` are
  English. `README.<lang>.md` files (currently `README.cs.md` and `README.pl.md`)
  are translations of `README.md` — never edit content in them directly. Edit
  `README.md`, then update every existing translation to match, including the
  translation-state sync date in its header. A translation may carry one extra
  section summarising the untranslated `CONTRIBUTING.md` ("Jak nesouhlasit" in
  `README.cs.md`, "Jak się nie zgadzać" in `README.pl.md`); everything else mirrors
  the original. When a note's "Where it
  stands" section changes, update that note's one-sentence verdict in `README.md`
  (and therefore in every translation). Verdict rules: one sentence, distilled from
  "Where it stands" — no new claims, no sharper than the note itself, nothing
  perishable (no numbers, no "as of").
- Working documents under `docs/superpowers/` (specs, plans) are written in Czech —
  the author's working language. Notes, `README.md` and repo docs are English.
- Notes are drafted in dialogue with the author. For substantive content decisions
  (positions, wording, weighing refutations), offer plain-text questions or a full
  drafted text to react to — the author prefers reacting to prose over filling
  multi-select forms.
- **Prose is not hard-wrapped.** A paragraph is one long line; the reader's renderer reflows it to their window. Wrap only where the line is itself the unit of meaning: code blocks, tables, list items, and commit-message bodies (~72 characters there, because `git log` does not reflow). Several early notes are still wrapped at ~90 characters — that is legacy, not the convention. Don't copy it when editing them, and don't reflow a whole file just to fix it.
- **Refute the organized defence, not the popular version.** When a note attacks a position that has an apologetics behind it, find that defence's strongest textual form, state it fairly, and beat it explicitly. The Tyre paragraph in `religion/bible-veracity.md` originally answered only the popular claim, and had to be rewritten when the standard defence was put to it: the shift from a singular to a plural agent at Ezekiel 26:12, and Alexander's causeway as a literal match for "stones into the water". A refutation that only beats the weak version invites exactly that correction — and conceding the strong point first is what makes the rest land.
- **Read primary texts raw, not through a summarizer.** "Never cite from memory" needs somewhere cheap to check. For scripture: Czech Bible 21 at `obohu.cz/bible/index.php?styl=B21&k=<book>&kap=<chapter>`, English at `bible-api.com/<book>+<ch>:<v>?translation=web`, Hebrew and Greek morphology at `biblehub.com/text/<book>/<ch>-<v>.htm` — the last of these is what settled that Ezekiel 26:14 has God in the first person and an agentless passive. Fetching BibleGateway through a summarizing tool returned a garbled paraphrase of Ezekiel 29:17–20 that dropped the very clause the argument rested on. When wording is load-bearing, fetch the raw text and read it yourself.
