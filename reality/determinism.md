# Is the universe deterministic — and could we ever know?

*Status: open · last touched 2026-08-24 · sources checked 2026-08-23*

## The question

A friend put the question to me cold: *is the universe deterministic?* I answered before I had time to think — "no; quantum mechanics settled that" — and this note exists because I noticed how little that answer cost me. It arrived instantly, borrowed from popularizations I could not name, and I had never once checked it. So the note is an audit of my own reflex, run under the only rule that makes auditing worth anything: I care more about the answer being true than about it being mine. If the reflex survives scrutiny, good; if it does not, the note should say so plainly.

First, what is being asked. **Determinism** here is the Laplacean claim: the complete state of the world at one instant, together with the laws of nature, fixes the entire future — and the entire past — down to the last detail. Laplace's image was a vast intellect that, knowing every position and every force at one moment, would hold the future and the past "present before its eyes" [VERIFY — exact wording and edition, *Essai philosophique sur les probabilités*, 1814]. Note the shape of the claim: it is about what *fixes* what, not about what anyone could compute. And note a distinction that will matter later: determinism as a property of a *theory* (its dynamics admit exactly one history through each state) and determinism as a property of the *world* are different things, connected only if the theory is true of the world.

Three things determinism is **not**, because the question dissolves into fog the moment they blur:

- **Not predictability.** Deterministic chaos is routine: systems whose future is completely fixed by their present state and yet unforecastable in practice, because any error in reading the present state grows exponentially. The Laplacean claim is about ontology, not computation — a deterministic universe can stay permanently surprising to everyone inside it.
- **Not causality.** "Every event has a cause" and "the state at one time fixes the state at the next" are different claims; the second is the sharper one, and it does not lean on the notoriously slippery word *cause*.
- **Not fatalism.** Fatalism says the outcome comes for you regardless of what you do; determinism says what you do is part of the machinery producing the outcome. A determinist can consistently hold that deliberation matters — it is a gear, not a spectator.

Then the question splits, and the split carries the whole note:

1. **Is our best physics deterministic?** A question about the content of current theories — answerable by reading them carefully, and, it turns out, much less settled than the schoolbook version suggests.
2. **Even if we knew the final theory, could any observation made from inside the universe settle whether the world itself is deterministic?** This is the harder question, and the one this note is really about.

The reflex I started with will have a name in what follows: **the folk inference** — the widely shared conviction that quantum mechanics has already settled the matter in favor of chance. It was my conviction too, stated as fact, the day the question arrived. Most of the pressure below lands on it.

Why care? Partly because a cluster of questions I do care about — freedom, responsibility, whether the future is open in any interesting sense — are usually argued in this question's shadow. And partly for the discipline: this is the purest specimen I own of a belief adopted without cost, and watching what happens to it under pressure is the point of this repository.

## Conjectures

- **Conjecture A — Clockwork restored.** The universe is deterministic and always was. The quantum "collapse" that supposedly killed the clockwork is appearance, not process: there exist formulations of quantum mechanics — Bohm's pilot-wave theory, Everett's many-worlds — whose dynamics are strictly deterministic and which reproduce every quantum prediction ever confirmed. The dice live in our ignorance, not in the world.

- **Conjecture B — The dice are real.** Chance is physically real. Collapse is an actual physical process with genuinely undetermined outcomes, as objective-collapse theories describe; God does play dice, and the future is open in the strongest possible sense. Note what this conjecture is not: it says that chance *is* real, not that quantum mechanics has already *proved* it — B could be true even if the folk inference is a bad argument.

- **Conjecture C — Undecidable from inside.** The deterministic and the chancy readings of quantum mechanics make the same predictions, and no observation performed from inside the universe can tell a world with dice from a world without them. The question is not open the way an unsolved empirical problem is open; it is permanently metaphysical, and physics will never hand us the answer. The spine of this note.

- **Conjecture D — Wrong kind of question.** Determinism is a property of theories — of state spaces and dynamical laws — not of the world. Asking whether "the universe" is deterministic, as opposed to asking whether some particular description of it is, is a category error, and the felt depth of the question is a grammatical illusion.

- **Conjecture E — Nothing hangs on it.** Even a definitive answer would change nothing that matters. Responsibility, freedom, merit — everything we actually care about — survives, or fails, identically in both branches; a life run on gears and a life run on dice are the same life from inside. A full note on free will belongs in `mind/` someday; here this is a coda, not the argument.

## Refutations & tensions

- **Against the folk inference — Bell forbids less than advertised.** The textbook theory really does have two rules: between measurements the quantum state evolves by the Schrödinger equation, deterministically; upon "measurement" it collapses, at random, with probabilities given by the Born rule. The folk inference reads the second rule as a discovery about the world. But the theory never says what a "measurement" is — that is the measurement problem — and so never settles whether collapse is a physical process or a bookkeeping update, closer to a gambler revising odds than to a die being thrown. And the theorem everyone reaches for here, Bell's, forbids less than advertised: what Bell's theorem plus the experiments rules out is *local* accounts — granted one further premise, the independence of the experimenters' settings, whose refusal is superdeterminism's business below — and outcome determinism is *stronger than what the derivation needs*, not its target. The standing counterexample is Bohmian mechanics: particles always have definite positions, guided deterministically by the wave function; the appearance of chance is ignorance of initial positions; and it reproduces the predictions of nonrelativistic quantum mechanics. Bell himself, far from thinking he had buried determinism, examined the pilot-wave theory favorably and spent years defending it as unjustly ignored [VERIFY — exact wording of Bell's "impossible done" remark]. Everett's reading is deterministic too, and more radically: the universal wave function never collapses at all; everything evolves unitarily, and chance is what a single branch feels like from inside. So "quantum mechanics proved the dice" is a non sequitur: the dice are in one family of readings of the formalism and absent from others that match every experiment run to date. Asserting the folk inference is choosing a reading and calling the choice a proof. This is where my entering answer breaks — and it breaks cleanly. The friend asked; I said "no — quantum mechanics"; and the honest report is that quantum mechanics, as it actually stands, says no such thing.

- **Against A — restoration has prices, and they are steep.** Determinism does not come back for free. Bohm's price is nonlocality of an aggressive kind — the velocity of one particle depends on the instantaneous positions of others arbitrarily far away — and with it a quarrel with relativity: the theory is not Lorentz invariant, and its natural repair is a preferred foliation of spacetime, a universal "now" that relativity spent a century teaching us not to want. Everett's price is probability itself: if every outcome occurs, what does it mean that some are more probable than others? The decision-theoretic program of Deutsch and Wallace derives the Born weights from rationality axioms inside the branching picture — and it remains contested, with the critical literature still accumulating. Superdeterminism — the third deterministic road, in which the experimenters' choices of settings are correlated with the systems' hidden states — restores locality at the price of statistical independence, and with it something close to the methodology of experiment itself: if the world conspires in what we choose to test, no test is quite what it seems. (It deserves a fairer hearing than a parenthesis; see Threads.) None of this refutes A. It prices A: each deterministic reading buys the clockwork by selling something else the schoolbook picture of physics holds dear.

- **Against B — the fringe is being squeezed.** Objective-collapse models are the honest version of B, and they deserve credit for being the only party in this dispute that behaves like a scientific rival rather than an interpretation: GRW and CSL modify the Schrödinger dynamics, and modified dynamics have consequences — among them a faint spontaneous radiation from matter that standard quantum mechanics forbids. That makes a corner of the question empirically decidable — call it **the decidable fringe**. And on the fringe, so far, B is losing ground: an underground search for that radiation found none, and with it the gravity-related Diósi–Penrose collapse model was experimentally falsified in its simplest formulation (Donadi et al. 2021 [VERIFY — exact journal reference]), while the same class of experiments now sets the strongest upper bounds on the parameters of CSL (as of 2026-08). The conclusion needs care: these experiments constrain specific models at specific parameters; they have not refuted real chance, and cannot — the parameter space retreats rather than closes. But the direction of travel is real, and it embarrasses the version of B that expected the dice to show up on the first serious look.

## Where it stands

*(to be written)*

## Threads to pull

*(to be written)*

## Sources

*(to be written)*
