# AGENTS.md

Guidance for AI coding agents working in this repository (Claude Code, Cursor, Aider, Copilot, …).

## Project overview

A personal, slowly-growing collection of Markdown notes thinking through large open questions — mortality, meaning, consciousness, our place in the cosmos, how the world is wired, faith seen from outside, and the ethics of war. A folder can be declared before its first note lands. The name nods to Popper's *Conjectures and Refutations*: everything here is a bold guess written to be refuted and revised, not a settled conclusion. There is no code and no build step — the deliverable is prose.

## Structure

- `continuity/` — Death and what (if anything) survives it: personal identity, cryonics, digital preservation.
- `cosmos/` — Our place in the universe: the Fermi paradox, the Great Filter, and their candidate resolutions.
- `meaning/` — What a life is for: purpose, value, living without guarantees.
- `mind/` — Consciousness, free will, and whether experience is what it seems.
- `reality/` — How the world is wired: determinism, chance, the nature of physical law, and what physics can and cannot decide.
- `religion/` — Faith examined from outside: scripture against checkable evidence, and what makes a religion dangerous.
- `war/` — The ethics of war: aggression, defense, prolongation, and third-party duties, tested on the war in Ukraine.
- `docs/` — Working documents, not notes, written in Czech: `docs/superpowers/specs/` and `docs/superpowers/plans/` hold the design spec and implementation plan of each larger note; `docs/analyses/` holds dialogue analyses (see Conventions); `docs/backlog.md` is the topic backlog — done, in progress, parked, candidates — and is updated whenever a topic changes state.

The structure is itself a conjecture and will change as the questions do.

## Parked work

- Branch `nuclear-blackmail` (on `origin`) holds a spec, a plan and a partly written `war/nuclear-blackmail.md` on the ethics of nuclear blackmail — The question and conjectures A–G approved, refutations not started. Parked 2026-07-27 because the author found the topic too complex for the moment; it is to be resumed, not abandoned. To resume: switch to the branch, rebase it onto `main`, and continue the plan at the refutations task. The author goes into this one without prior positions, so draft full text to react to rather than asking for weights or rankings.

## Setup

None. Any Markdown editor works; there are no dependencies to install.

## Run / build / test

- **Run / build:** N/A — plain Markdown, nothing to compile.
- **Test:** N/A. (Optional: a Markdown linter such as `markdownlint` could be added later.)

## Conventions

- Every note follows the shape in `TEMPLATE.md`: **The question → Conjectures → Refutations & tensions → Where it stands → Threads to pull → Sources.** Start new notes by copying `TEMPLATE.md`. The Sources section is optional for purely conceptual notes and expected for any note leaning on checkable facts.
- Each note carries a status line: `*Status: open · last touched YYYY-MM-DD · sources checked YYYY-MM-DD*`. The two dates mean different things and drift apart on purpose — **last touched** is when the prose changed, **sources checked** is when the empirical claims were last verified against sources. Update each when you do that particular thing. A partial re-check of one claim's sources goes into a trailing parenthetical rather than moving the whole date — `sources checked 2026-07-20 (Tyre re-checked 2026-08-22)` — so the date keeps meaning "everything was checked then".
- Tone is thinking-in-progress, not conclusions. Prefer "my best current guess" over confident assertion; the point is the refutations.
- **Never cite from memory.** Verify a source exists and actually says what it is being cited for, or mark it unverified in the note. A confabulated citation is worse than none, because it borrows authority it hasn't earned.
- **Verbatim is not enough — a quotation is checked only in its paragraph.** Two quotations in `religion/science-as-religion.md` were verbatim, verified against the raw page, and still wrong: a scientist's argument cut two sentences before the point where it stops being even-handed, and a pair of symmetric-sounding sentences that turned out to close a paragraph one-way from its first line. Before a quotation carries weight, read to where it ends and what follows it. A concession is often the premise of a *tu quoque*, so the sentence after the concession is the one to read — when a source seems to concede your point, that is the signal to keep reading, not to stop.
- **Two kinds of error need two different habits.** A claim can be *untrue* (the inscription is not on the wall) or merely *stale* (the settlement timescale was superseded, the open question was answered). Untrue is caught once and fixed forever; stale returns without anyone writing a false word. So mark perishable claims — prices, survey data, "no one has yet done X," anything about the state of the art — with an inline `(as of YYYY-MM)`, and treat the `sources checked` date as the note's expiry warning.
- **Record what the sourcing cost you.** When a source corrects a claim, refuses the use you wanted, or forces a conclusion to weaken, write that into the note rather than silently editing around it. Withdrawn claims stay visible, with the reason. This is the Popperian point of the project made concrete: a note that only shows its wins isn't a conjecture, it's a pitch.
- **Refutation passes are recorded in Sources, including what was not adopted.** When a fresh-context reviewer is set on a note or a new section, brief it to *refute*, not to check, and give it the raw source pages on disk so it can verify quotations character by character. The pass then goes into the note's Sources: date, what it broke, what changed because of it, and which findings were *not* adopted and why — the reviewer sees less than the author (it cannot read a private exchange, for instance) and is sometimes wrong, so re-verify its top findings against the source yourself before applying any. A second pass over rebuilt material can overturn the first: in `religion/science-as-religion.md` the 2026-09-14 pass replaced a "veto" reading with a "levelling" one, and the 2026-09-17 pass showed the levelling reading was the error. Both stay recorded; the sequence is the point.
- Filenames: lowercase kebab-case `.md` (e.g. `fermi-paradox.md`), placed in the topic folder that fits.
- Commit messages: short, present-tense, describing the change to the notes (e.g. `add fermi-paradox conjecture`, `revise meaning: where-it-stands`).
- **Git workflow.** The author's own work lands on `main` directly; there are no pull requests for it. From a Claude Code worktree (branch `worktree-<name>`) push with `git push origin HEAD:main`, then `git pull` in the main checkout. A worktree branch is pushed under its own name only when a topic is parked (see Parked work).
- **English is canonical; translations mirror it.** All notes and `README.md` are
  English. `README.<lang>.md` files (currently `README.cs.md` and `README.pl.md`)
  are translations of `README.md` — never edit content in them directly. Edit
  `README.md`, then update every existing translation to match, including the
  translation-state sync date in its header. A translation may carry one extra
  section summarising the untranslated `CONTRIBUTING.md` ("Jak nesouhlasit" in
  `README.cs.md`, "Jak się nie zgadzać" in `README.pl.md`); everything else mirrors
  the original. When a note's "Where it
  stands" section changes, re-check that note's one-sentence verdict in `README.md`
  (and therefore in every translation): update it when it no longer distils the
  section; when it still does, leave it and write `Verdict unchanged.` in the commit
  message, so the check is visible. Verdict rules: one sentence, distilled from
  "Where it stands" — no new claims, no sharper than the note itself, nothing
  perishable (no numbers, no "as of").
- Working documents are written in Czech, the author's working language: specs and plans under `docs/superpowers/`, and dialogue analyses under `docs/analyses/` — a first-pass answer to a question the author brought, written to be reacted to; the seed of a note, not a note. Notes, `README.md` and repo docs are English.
- Notes are drafted in dialogue with the author. For substantive content decisions
  (positions, wording, weighing refutations), offer plain-text questions or a full
  drafted text to react to — the author prefers reacting to prose over filling
  multi-select forms.
- **Write down the entry intuition before the research.** When a topic starts, the design spec records the author's raw first guess as one of the claims the note will test — stated bluntly, not hedged — and the note says whether it survived. Determinism began from "quantum mechanics means the universe is not deterministic"; the literature broke it, and that recorded break is the most valuable thing in the note. Without an entry position there is nothing to refute, and what comes out is a survey, not a conjecture.
- **Prose is not hard-wrapped.** A paragraph is one long line; the reader's renderer reflows it to their window. Wrap only where the line is itself the unit of meaning: code blocks, tables, list items, and commit-message bodies (~72 characters there, because `git log` does not reflow). Several early notes are still wrapped at ~90 characters — that is legacy, not the convention. Don't copy it when editing them, and don't reflow a whole file just to fix it.
- **Refute the organized defence, not the popular version.** When a note attacks a position that has an apologetics behind it, find that defence's strongest textual form, state it fairly, and beat it explicitly. The Tyre paragraph in `religion/bible-veracity.md` originally answered only the popular claim, and had to be rewritten when the standard defence was put to it: the shift from a singular to a plural agent at Ezekiel 26:12, and Alexander's causeway as a literal match for "stones into the water". A refutation that only beats the weak version invites exactly that correction — and conceding the strong point first is what makes the rest land.
- **Notes stay depersonalized.** Exchanges with specific people — their arguments, replies sent under the author's name — are archived outside this repo, in a separate private `debates` repository with one folder per person. A debate can force a revision here (the Tyre paragraph was rewritten after one), but the note records the argument and its source, never the opponent. When asked to draft a reply to someone, do not create the file in this repo.
- **Read primary texts raw, not through a summarizer.** "Never cite from memory" needs somewhere cheap to check. For scripture: Czech Bible 21 at `obohu.cz/bible/index.php?styl=B21&k=<book>&kap=<chapter>`, English at `bible-api.com/<book>+<ch>:<v>?translation=web`, Hebrew and Greek morphology at `biblehub.com/text/<book>/<ch>-<v>.htm` — the last of these is what settled that Ezekiel 26:14 has God in the first person and an agentless passive. Fetching BibleGateway through a summarizing tool returned a garbled paraphrase of Ezekiel 29:17–20 that dropped the very clause the argument rested on. When wording is load-bearing, fetch the raw text and read it yourself.
