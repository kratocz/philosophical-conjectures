# README Verdicts + Czech README Mirror — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Přidat jednovětné verdikty všech 9 poznámek do `README.md`, vytvořit české zrcadlo `README.cs.md` a zakotvit překladovou konvenci v `AGENTS.md` — podle specu `docs/superpowers/specs/2026-07-27-readme-verdicts-czech-readme-design.md`.

**Architecture:** Tři malé tasky, každý končí samostatným commitem na `main` (konvence repa) a zanechává repo konzistentní (žádný commit s rozbitým odkazem). Verdikty jsou fixované v tomto plánu a schválené autorem — exekutor je přebírá doslova, nevymýšlí je. `README.cs.md` je plný překlad `README.md` po Tasku 1 + hlavička překladu + sekce „Jak nesouhlasit".

**Tech Stack:** Markdown, git (přímo na `main`), bash na kontrolu odkazů.

## Global Constraints

- Angličtina je canonical; `README.cs.md` je zrcadlo a edituje se jen v rámci syncu s originálem.
- Verdikt = jedna věta, destilát „Where it stands", žádné číslice ani „as of" (verdikt nesmí mít vlastní expirační datum), ne ostřejší než poznámka.
- Mění se **jen** `README.md`, `README.cs.md` (nový) a `AGENTS.md`. Na poznámky, `TEMPLATE.md` a `CONTRIBUTING.md` se nesahá.
- Česká verze s plnou diakritikou (nikdy ASCII náhrady).
- Commit messages: krátké, present-tense, anglicky; s trailery
  `Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>` a
  `Claude-Session: https://claude.ai/code/session_018XCtx3J1pdswHHvAJMLHzW`.

---

### Task 1: Verdikty poznámek v README.md

**Files:**
- Modify: `README.md` (sekce `## How it's organized`, řádky 15–24)

**Interfaces:**
- Consumes: sekce „Where it stands" všech 9 poznámek (jen ke kontrole — verdikty jsou už vydestilované níže).
- Produces: přesná anglická znění 9 verdiktů, která Task 2 překládá do češtiny. Formát pod-odrážky: `  - [Krátký titul](cesta/soubor.md) — *Verdikt.*`

- [ ] **Step 1: Nahradit sekci „How it's organized"**

V `README.md` nahradit celý blok od řádku `## How it's organized` po řádek `The structure is itself a conjecture, and will change as the questions do.` (včetně) tímto zněním — popisy složek zůstávají doslova stejné, přibývá úvodní odstavec a pod-odrážky poznámek:

```markdown
## How it's organized

Each folder below lists its notes, each with a one-sentence snapshot of where that note
currently lands. The snapshots are provisional by design and go stale first — the note
itself, its "Where it stands" section and the caveats around it, is always the source
of truth.

- **`continuity/`** — Death, and what (if anything) survives it. Personal identity over time, cryonics, digital preservation of a self.
  - [Cryonics](continuity/cryonics.md) — *The case is thinner than advocates admit — the bet must win twice, on preservation and on identity — and part of its real draw is present-tense agency, for the living.*
  - [Desirability of immortality](continuity/immortality-desirability.md) — *The personal case against long life turned out weaker than it sounds, the social case stronger: I'd want the extra time, with an out — and I'm unsure the world should have it.*
  - [Personal identity](continuity/personal-identity.md) — *Identity consists in continuity with no further fact behind it, and in the hard cases the concept simply returns no verdict — which may itself be the answer.*
- **`cosmos/`** — Our place in the universe. The Fermi paradox and its candidate resolutions; what we might ask another intelligence if we ever met one.
  - [The Fermi paradox](cosmos/fermi-paradox.md) — *Dark forest beats zoo on economy of assumptions, but the whole "silence is a choice" family ranks below the mundane resolutions: they're rare, we're early.*
  - [The Great Filter](cosmos/great-filter.md) — *No verdict, on purpose: the evidence can't adjudicate — and the unsettling map says the more life we find, the worse our odds probably are.*
- **`meaning/`** — What a life is for. Purpose, value, and how to live without a guarantee that any of it means anything.
  - [Meaning without a guarantee](meaning/meaning-without-guarantee.md) — *The demand for an outside guarantee fails on its own terms, the question what is worth engaging in survives it — and the case for living is not that life means something, but option value at a one-way door.*
- **`mind/`** — The thing doing all the asking. Consciousness, free will, and whether experience is what it seems to be.
- **`religion/`** — Faith examined from outside. What scripture gets right and wrong against checkable reality, and what makes a religion dangerous to the civilization hosting it.
  - [The Bible against checkable reality](religion/bible-veracity.md) — *A human library of its era, not an oracle: reliability rises as the text approaches its own present — the signature of human authorship.*
  - [What makes a religion dangerous](religion/religion-risk.md) — *Text is ammunition, structure is the gun, power is the trigger — what can be assessed is never "a religion" in the abstract, only a configuration at a time and place.*
- **`war/`** — The ethics of war, tested on the one running now: who started it, who keeps it going, and what bystanders owe.
  - [The war in Ukraine](war/ukraine-war-justification.md) — *The invasion and its prolongation are unjust, the defense and its support justified — and the defense's one limit is Ukraine's own settled choice, which no third party may manufacture.*

The structure is itself a conjecture, and will change as the questions do.
```

Pořadí pod-odrážek uvnitř složky: abecedně podle názvu souboru. `mind/` nemá poznámky, zůstává bez pod-odrážek.

- [ ] **Step 2: Ověřit odkazy a čistotu verdiktů**

Spustit:

```bash
grep -oE '\]\([A-Za-z0-9/._-]+\.md\)' README.md | sed 's/^](//; s/)$//' | sort -u | while read f; do [ -f "$f" ] && echo "OK $f" || echo "MISSING $f"; done
grep -E '^  - \[' README.md | grep -cE '[0-9]|as of' || echo "verdicts clean"
```

Očekáváno: první příkaz vypíše `OK` pro všech 9 cest k poznámkám + `OK CONTRIBUTING.md`, žádný řádek `MISSING`; druhý příkaz vypíše `verdicts clean` (žádná číslice ani „as of" ve verdiktových řádcích).

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "$(cat <<'EOF'
add note verdicts to readme

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_018XCtx3J1pdswHHvAJMLHzW
EOF
)"
```

---

### Task 2: README.cs.md + odkaz z originálu

**Files:**
- Create: `README.cs.md`
- Modify: `README.md` (řádek za H1)

**Interfaces:**
- Consumes: anglická znění verdiktů a strukturu sekce z Tasku 1 (české verdikty níže jsou jejich schválené překlady).
- Produces: soubor `README.cs.md`, na jehož název se odkazuje Task 3 (konvence v AGENTS.md) i řádek překladů v `README.md`.

- [ ] **Step 1: Vytvořit README.cs.md**

Celý obsah souboru (doslova):

```markdown
# Filozofické konjektury

*Toto je český překlad [anglického originálu](README.md). Originál je závazný a jediný
se edituje — návrhy změn (issue, pull request) prosím směřujte na něj; psát je můžete
i česky. Překlad odpovídá stavu originálu k 2026-07-27.*

Osobní, pomalu rostoucí sbírka poznámek, v nichž promýšlím některé z největších
otevřených otázek — smrtelnost, smysl, jestli jsme sami — a snažím se své odpovědi
držet poctivě.

Název odkazuje na knihu Karla Poppera *Conjectures and Refutations* (Domněnky
a vyvrácení): myšlenku, že k pravdě nedocházíme dokazováním, ale odvážnými odhady,
které se pak ze všech sil snažíme srazit. Všechno tady je konjektura. Nic není
uzavřené. Každá poznámka je psaná proto, aby byla revidována.

Většina poznámek vzniká v dialogu — často s AI asistentem — proto se čtou spíš jako
rozhovor se sebou samým než jako hotové eseje.

> ### Myslíte, že je tu něco špatně? Dobře — přesně o to jde.
>
> Každé tvrzení v tomto repozitáři je otevřené sporu a opravy jsou to nejcennější, co
> může kdokoli poslat. **[Jak tu něco vyvrátit](CONTRIBUTING.md)** (anglicky) je mapa
> míst, kde jsou poznámky nejslabší — seznamy „What would change my mind", tvrzení
> označená jako neověřená, ta, která mohla potichu zastarat — abyste měkká místa
> nemuseli hledat. Miřte tam.
>
> Nemusíte to změkčovat a nemusíte mít pravdu.

## Jak je to uspořádané

U každé složky jsou níže vypsané její poznámky, každá s jednovětným snímkem toho, kde
právě stojí. Snímky jsou záměrně provizorní a zastarávají jako první — zdrojem pravdy
je vždy poznámka sama, její sekce „Where it stands" a výhrady kolem ní.

- **`continuity/`** — Smrt a co (pokud vůbec něco) ji přežívá. Osobní identita v čase, kryonika, digitální uchování já.
  - [Kryonika](continuity/cryonics.md) — *Argument je tenčí, než zastánci přiznávají — sázka musí vyhrát dvakrát, na uchování i na identitě — a část její skutečné přitažlivosti je možnost jednat už teď, pro živé.*
  - [Žádoucnost nesmrtelnosti](continuity/immortality-desirability.md) — *Osobní argumenty proti dlouhému životu se ukázaly slabší, než znějí, společenské silnější: čas navíc bych chtěl, s možností odchodu — a nejsem si jistý, jestli ho mám přát světu.*
  - [Osobní identita](continuity/personal-identity.md) — *Identita spočívá v kontinuitě a žádný další fakt za ní není; v hraničních případech pojem prostě žádný verdikt nevrací — což může být sama odpověď.*
- **`cosmos/`** — Naše místo ve vesmíru. Fermiho paradox a kandidátská řešení; na co bychom se ptali jiné inteligence, kdybychom ji potkali.
  - [Fermiho paradox](cosmos/fermi-paradox.md) — *Temný les poráží zoo úsporností předpokladů, ale celá rodina „ticho je volba" stojí níž než všední vysvětlení: jsou vzácní, jsme tu brzy.*
  - [Velký filtr](cosmos/great-filter.md) — *Záměrně bez verdiktu: důkazy rozhodnout neumějí — a znepokojivá mapa říká, že čím víc života najdeme, tím hůř na tom nejspíš jsme.*
- **`meaning/`** — K čemu život je. Účel, hodnota a jak žít bez záruky, že cokoli z toho něco znamená.
  - [Smysl bez záruky](meaning/meaning-without-guarantee.md) — *Požadavek vnější záruky selhává sám o sobě, otázka, co stojí za angažmá, ho přežívá — a důvodem k životu není, že život něco znamená, ale opční hodnota u jednosměrných dveří.*
- **`mind/`** — To, co se tu celou dobu ptá. Vědomí, svobodná vůle a jestli je prožitek tím, čím se zdá být.
- **`religion/`** — Víra zkoumaná zvenčí. Co Písmo trefuje a netrefuje proti ověřitelné realitě a čím je náboženství nebezpečné civilizaci, která ho hostí.
  - [Bible proti ověřitelné realitě](religion/bible-veracity.md) — *Lidská knihovna své doby, ne orákulum: spolehlivost roste s tím, jak se text blíží vlastní současnosti — podpis lidského autorství.*
  - [Čím je náboženství nebezpečné](religion/religion-risk.md) — *Text je munice, struktura je zbraň a moc je spoušť — hodnotit nelze „náboženství" v abstraktu, jen konkrétní konfiguraci v čase a místě.*
- **`war/`** — Etika války, testovaná na té, která právě běží: kdo ji začal, kdo ji udržuje a co dlužíme my ostatní.
  - [Válka na Ukrajině](war/ukraine-war-justification.md) — *Invaze i její prodlužování jsou nespravedlivé, obrana i její podpora oprávněné — a jedinou mezí obrany je vlastní ustálená volba Ukrajiny, kterou žádná třetí strana nesmí vyrobit.*

Struktura je sama o sobě konjektura a bude se měnit s otázkami.

## Jak poznámka funguje

Každý záznam má zhruba stejný tvar (viz `TEMPLATE.md`):

1. **The question** — otázka, tak přesně, jak jen dokážu.
2. **Conjectures** — kandidátské odpovědi, vyslovené odvážně.
3. **Refutations & tensions** — kde se každá z nich láme.
4. **Where it stands** — můj současný, provizorní pohled a co by ho změnilo.
5. **Threads to pull** — otevřené podotázky a co číst příště.
6. **Sources** — tam, kde se poznámka opírá o ověřitelná fakta: co bylo ověřeno, co se
   ukázalo špatně a co jsem cestou stáhl.

Každá poznámka nese dvě data — kdy se naposledy změnila próza a kdy byla fakta
naposledy ověřena proti zdrojům. Rozcházejí se schválně. Poznámka může zastarat, aniž
by jediné její slovo přestalo platit, a varuje před tím jen to druhé datum.

## Poznámka k tónu

Tohle je myšlení v průběhu, ne závěry. Pokud něco zní sebejistě, čtěte to jako „tohle
je můj nejlepší současný odhad", ne „tohle je pravda". Pointa jsou vyvrácení.

## Kdo psal námitky

Stojí za to říct natvrdo, protože to ovlivňuje, jakou mají vyvrácení cenu: sekci
**„Refutations & tensions" v každé poznámce jsem psal já** — tentýž člověk, který dělá
konjektury.

To je skutečný limit a nezmizí tím, že si ho všimnu. Proti sobě umím argumentovat jen
námitkami, které mě napadly, a nejsem nestranný soudce toho, které sedí —
protiargumenty, které považuji za zdrcující, bývají ty, s nimiž jsem se už smířil,
a ty, které považuji za slabé, si zaslouží víc podezření, než jim umím dát. Kde
poznámka zaujímá postoj k živé tradici, spornému oboru nebo čemukoli, kolem čeho si
rozumní lidé organizují život, předpokládejte, že nejsilnější verze druhé strany je
silnější než ta, kterou najdete tady.

Opravy jsou tedy vítané, nejvíc od lidí, kteří si myslí, že je poznámka špatně — a jak
na to, shrnuje další sekce.

Jakmile poznámky začnou číst lidé, kteří s nimi nesouhlasí, zaznamenám to
**v poznámce**, místo abych tuhle sekci potichu smazal. Seznam těch, kdo se ohradili,
a kde, je informativnější než chybějící přiznání.

## Jak nesouhlasit

Krátce z plného návodu [CONTRIBUTING.md](CONTRIBUTING.md) (anglicky):

- Nejcennější příspěvek je **věcná oprava s dohledatelným zdrojem** — a nejlepší terč
  jsou seznamy **„What would change my mind"** na konci každé poznámky: podmínky, za
  kterých pozici opustím, vyslovené předem.
- Dobré terče jsou i položky označené **NOT VERIFIED** (tvrzení, která se nepodařilo
  ověřit) a staré datum **„sources checked"** ve statusové řádce poznámky — poznámka
  mohla potichu zastarat, aniž je v ní jediné nepravdivé slovo.
- Issue nebo pull request **klidně pište česky** — poznámky jsou anglicky, ale spor se
  o ně může vést i česky.

## Licence

Texty v tomto repozitáři jsou pod licencí [Creative Commons Attribution-ShareAlike 4.0
International](https://creativecommons.org/licenses/by-sa/4.0/deed.cs) (CC BY-SA 4.0)
— © Petr Kratochvíl. Kopírujte, překládejte, citujte, forkujte a pište lepší
vyvrácení; zachovejte atribuci a svou verzi šiřte pod stejnými podmínkami. Kdyby tu
někdy přistál kód (konfigurace linteru, build skript), byl by pod MIT — dnes tu žádný
není.

Jedna prosba, kterou licence vynutit neumí: několik poznámek nese tabulky a bodovaná
pořadí, která znamenají jen to, co říkají, spolu s výhradami kolem nich. Pokud
některé přebíráte, vezměte s sebou i kontext.
```

- [ ] **Step 2: Přidat řádek překladů do README.md**

Za řádek `# Philosophical Conjectures` (a prázdný řádek za ním) vložit:

```markdown
*Česky: [README.cs.md](README.cs.md)*
```

…následovaný prázdným řádkem. (Formát snese další jazyky oddělené ` · `.)

- [ ] **Step 3: Ověřit odkazy obou souborů a diakritiku**

Spustit:

```bash
for md in README.md README.cs.md; do echo "== $md"; grep -oE '\]\([A-Za-z0-9/._-]+\.md\)' "$md" | sed 's/^](//; s/)$//' | sort -u | while read f; do [ -f "$f" ] && echo "OK $f" || echo "MISSING $f"; done; done
grep -c '[ěščřžýáíéúůďťň]' README.cs.md
```

Očekáváno: žádný řádek `MISSING` (v `README.md` přibylo `OK README.cs.md`); počet řádků s diakritikou v `README.cs.md` je vysoký (řádově 80+), což potvrzuje, že nedošlo k ASCII degradaci.

- [ ] **Step 4: Commit**

```bash
git add README.md README.cs.md
git commit -m "$(cat <<'EOF'
add czech readme mirror

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_018XCtx3J1pdswHHvAJMLHzW
EOF
)"
```

---

### Task 3: Překladová konvence v AGENTS.md

**Files:**
- Modify: `AGENTS.md` (sekce `## Conventions`, za odrážku o commit messages na konci)

**Interfaces:**
- Consumes: název souboru `README.cs.md` z Tasku 2.
- Produces: nic pro další tasky (poslední task).

- [ ] **Step 1: Přidat konvenci**

Na konec sekce `## Conventions` v `AGENTS.md` (za odrážku `- Commit messages: …`) přidat:

```markdown
- **English is canonical; translations mirror it.** All notes and `README.md` are
  English. `README.<lang>.md` files (currently `README.cs.md`) are translations of
  `README.md` — never edit content in them directly. Edit `README.md`, then update
  every existing translation to match, including the "Překlad odpovídá stavu
  originálu k YYYY-MM-DD" sync date in its header. When a note's "Where it stands"
  section changes, update that note's one-sentence verdict in `README.md` (and
  therefore in every translation).
```

- [ ] **Step 2: Ověřit konzistenci**

Spustit:

```bash
grep -n 'README.cs.md' AGENTS.md README.md && ls README.cs.md
```

Očekáváno: zásah v obou souborech a existující `README.cs.md`.

- [ ] **Step 3: Commit**

```bash
git add AGENTS.md
git commit -m "$(cat <<'EOF'
document translation convention in agents.md

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_018XCtx3J1pdswHHvAJMLHzW
EOF
)"
```
