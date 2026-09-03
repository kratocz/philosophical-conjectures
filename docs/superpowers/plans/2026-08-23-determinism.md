# Determinism Note — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Napsat, ověřit a commitnout první poznámku nové složky `reality/` — `determinism.md` — podle specu `docs/superpowers/specs/2026-08-23-determinism-design.md`.

**Architecture:** Jedna Markdown poznámka ve tvaru `TEMPLATE.md`. Páteř je epistemická: hlavní konjekturou je nerozhodnutelnost (C), fyzika vystupuje jako ověřená kotva uvnitř refutací, dovětek „no a co" (E) drží jednu konjekturu s dopředným odkazem na budoucí `mind/`. Autorova vstupní intuice („kvůli QM není vesmír deterministický") je v textu přiznaná a testovaná. Drafty vznikají po sekcích v dialogu s autorem; empirická jádra se ověřují už při draftování své sekce, textové citace a atribuce v konsolidačním Tasku 7; zásahy do README/AGENTS landují až po dopsání poznámky (Task 8, jedna dávka s verdiktem).

**Tech Stack:** Markdown, git (přímo na `main` — konvence repa), WebSearch/WebFetch pro verifikaci zdrojů.

## Global Constraints

- Poznámka je **anglicky**; pracovní dialog s autorem česky; **žádné formulářové dotazníky** — autor reaguje na hotový text (drafty ukazovat anglicky, shrnovat česky).
- Cílový soubor: `reality/determinism.md`. H1: `# Is the universe deterministic — and could we ever know?`
- Pořadí sekcí přesně podle `TEMPLATE.md`; statusová řádka `*Status: open · last touched YYYY-MM-DD · sources checked YYYY-MM-DD*` (data = skutečné dny činností; `sources checked` finalizuje Task 7).
- Mimo poznámku se mění **jen** `README.md`, `README.cs.md`, `README.pl.md` a `AGENTS.md`, a to výhradně v Tasku 8 (spec: jedna dávka s verdiktem). Žádné změny TEMPLATE/CONTRIBUTING ani jiných poznámek.
- **Never cite from memory:** každé empirické či textové tvrzení se buď ověří v tasku, kde vzniká (in-task verifikace), nebo nese marker `[VERIFY]` do Tasku 7. Co verifikací neprojde: opravit, vypustit, nebo označit NOT VERIFIED. Co verifikace změnila, zaznamenat v Sources (konvence repa: prohry zůstávají viditelné).
- Perishable tvrzení — zejména stav experimentů s kolapsovými modely — nesou `(as of YYYY-MM)`.
- Odstavce prózy **nezalamovat** (odstavec = jeden řádek; pravidlo autora). Starší poznámky jsou zalamované — nové už ne; nepřepisovat kvůli tomu staré.
- Cíl rozsahu: spec říká 350–450 řádků kalibrovaných na zalamovaný styl; v nezalamovaném stylu tomu odpovídá **~4000–5500 slov** (`wc -w`). Řídit se slovy.
- Pevná jména napříč tasky: konjektury **A — Clockwork restored**, **B — The dice are real**, **C — Undecidable from inside** (páteřní), **D — Wrong kind of question**, **E — Nothing hangs on it**; dále **the folk inference** (vstupní intuice „QM už to dokázala"), **the decidable fringe** (kolapsové modely jako testovatelný okraj prostoru), **the schoolbook picture** („klasika = hodiny, kvantovka = kostky").
- Tón: thinking-in-progress, první osoba autora (Petr); the folk inference se testuje, nehájí; refutace C nesmí být měkčí než refutace ostatních (páteř si nenadržuje).
- Commity: krátké, present-tense, podle vzorů níže. Trailer `Co-Authored-By` + `Claude-Session` podle session, ve které task reálně běží.

---

### Task 1: Scaffold + The question

**Files:**
- Create: `reality/determinism.md`

**Interfaces:**
- Consumes: `TEMPLATE.md` (tvar), spec sekce „Titul a The question".
- Produces: soubor se všemi šesti `##` nadpisy, hotovou sekcí The question, H1 a statusovou řádkou; zavedené jméno **the folk inference**, na které navazují Tasky 2–5. Složka `reality/` vzniká tímto souborem (git složky netrackuje, žádný `.gitkeep`).

- [x] **Step 1: Založit soubor se skeletem**

Vytvořit `reality/determinism.md`:

```markdown
# Is the universe deterministic — and could we ever know?

*Status: open · last touched 2026-08-XX · sources checked 2026-08-XX*

## The question

(drafted within this task, before the commit)

## Conjectures

*(to be written)*

## Refutations & tensions

*(to be written)*

## Where it stands

*(to be written)*

## Threads to pull

*(to be written)*

## Sources

*(to be written)*
```

(`XX` = den, kdy Task 1 skutečně běží; `last touched` se aktualizuje s každým dalším taskem, `sources checked` finalizuje Task 7.)

- [x] **Step 2: Check skeletu**

Run: `grep -n '^## ' reality/determinism.md`
Expected (přesně toto pořadí): `## The question`, `## Conjectures`, `## Refutations & tensions`, `## Where it stands`, `## Threads to pull`, `## Sources`

- [x] **Step 3: Draft The question (anglicky, v dialogu s autorem)**

Obsahová specifikace (závazná, formulace vznikne v dialogu):

1. **Původ otázky:** položil ji autorovi kamarád (bez jména), a autorova okamžitá odpověď zněla „ne — kvantová mechanika". Poznámka je audit té odpovědi; závazek vyslovit explicitně: pravda má přednost před přežitím intuice.
2. **Definice:** laplaceovský determinismus — úplný stav světa v čase t + zákony ⇒ jediná možná budoucnost (a minulost). Laplaceův démon s odkazem na *Essai philosophique sur les probabilités* (1814) `[VERIFY]` — v draftu parafráze, přesné znění a vydání řeší Task 7. Rozlišit determinismus *teorie* (vlastnost dynamiky) od determinismu *světa* — předznamenává konjekturu D.
3. **Co determinismus není** (po jedné–dvou větách): předvídatelnost (deterministický chaos — citlivá závislost na počátečních podmínkách; démon je o ontologii, ne o výpočtu), kauzalita, fatalismus (výsledek přijde nezávisle na tom, co uděláš).
4. **Rozdvojení otázky, které nese celou poznámku:** (i) je naše nejlepší fyzika deterministická? (ii) i kdybychom finální teorii znali — může pozorování zevnitř vesmíru rozhodnout, jaký svět *je*? Páteř poznámky je (ii).
5. **the folk inference** pojmenovat hned zde: rozšířené přesvědčení „quantum mechanics settled it — the universe is chancy". Ohlásit, že poznámka ji podrobí tlaku, a že je to i vstupní intuice autora.

- [x] **Step 4: Schválení autorem**

Předložit draft sekce (anglický text + české shrnutí). Zapracovat úpravy. Bez explicitního souhlasu nepokračovat.

- [x] **Step 5: Commit**

```bash
git add reality/determinism.md
git commit -m "add determinism conjecture

Co-Authored-By: Claude Opus 5 (1M context) <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01BGtkbfoRJooRXZ44TYKKbg"
```

### Task 2: Conjectures A–E

**Files:**
- Modify: `reality/determinism.md` (sekce `## Conjectures`)

**Interfaces:**
- Consumes: H1, The question, jméno the folk inference (Task 1).
- Produces: pět konjektur s pevnými jmény (viz Global Constraints), na která se odkazují Tasky 3–5.

- [x] **Step 1: Draft pěti konjektur (v dialogu s autorem)**

Formát: `- **Conjecture A — Clockwork restored.** …` Každá vyslovena odvážně, bez hedgingu — hedging patří do refutací. Obsahová specifikace:

- **A — Clockwork restored.** Vesmír je deterministický a vždy byl; kvantový „kolaps" je zdání, ne proces. Bohmova mechanika i Everett reprodukují kvantové predikce s přísně deterministickou dynamikou — kostky jsou v naší nevědomosti, ne ve světě.
- **B — The dice are real.** Náhoda je fyzikálně skutečná: kolaps je reálný fyzikální proces s nedeterminovaným výsledkem (objektivní kolapsové teorie, GRW/CSL). Výslovně oddělit od the folk inference: B tvrdí, že náhoda reálná *je*; the folk inference tvrdí, že QM to už *prokázala*. B může být pravdivá, i kdyby the folk inference byla neplatný úsudek.
- **C — Undecidable from inside.** Deterministická a indeterministická čtení dávají stejné predikce; žádné pozorování provedené zevnitř vesmíru nedokáže oddělit svět s kostkami od světa bez nich. Otázka je trvale metafyzická, ne empirická. **Páteřní konjektura.**
- **D — Wrong kind of question.** Determinismus je vlastnost teorií (stavových prostorů a dynamik), ne světa; ptát se, zda „vesmír" je deterministický, je kategorická chyba.
- **E — Nothing hangs on it.** I definitivní odpověď by nezměnila nic, na čem záleží — odpovědnost, svoboda a zásluha přežijí (nebo padnou) v obou větvích stejně. Dovětek; plná poznámka o svobodné vůli patří do `mind/` (dopředná zmínka prózou, ne `[[…]]` odkaz — cílový soubor neexistuje).

- [x] **Step 2: Check značení**

Run: `grep -c '^\- \*\*Conjecture' reality/determinism.md`
Expected: `5`

- [x] **Step 3: Schválení autorem** — jako Task 1 Step 4.

- [x] **Step 4: Commit**

```bash
git add reality/determinism.md
git commit -m "draft determinism: conjectures

Co-Authored-By: Claude Opus 5 (1M context) <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01BGtkbfoRJooRXZ44TYKKbg"
```

### Task 3: Refutations — kvantové jádro (proti the folk inference, A, B)

**Files:**
- Modify: `reality/determinism.md` (sekce `## Refutations & tensions`, bloky 1–3)

**Interfaces:**
- Consumes: konjektury A–C, the folk inference (Tasky 1–2).
- Produces: bloky 1–3 refutací s bold lead-iny (repo styl, ne `###`); zavedené jméno **the decidable fringe** (blok 3), na které navazují Task 4 (proti C) a Task 5 (what would change my mind); pracovní seznam ověřených zdrojů pro Task 7.

- [x] **Step 1: Draft bloků 1–3 (v dialogu s autorem)**

Obsahová specifikace:

1. **Against the folk inference — Bell forbids less than advertised.** Učebnicová QM má dvě pravidla: unitární vývoj (deterministický) a stochastický kolaps při měření — a „měření" nemá definici (measurement problem); kolaps může být fyzikální proces, nebo jen účetnictví pozorovatele. Bellův teorém (Bell 1964 `[VERIFY]`) vylučuje *lokální* skryté proměnné, ne determinismus — Bohmova mechanika je deterministická, nelokální a empiricky ekvivalentní standardním kvantovým predikcím `[VERIFY přes SEP]`; sám Bell ji hájil (citát „in 1952 I saw the impossible done" `[VERIFY — přesné znění a místo, Speakable and Unspeakable]`). Everett: univerzální vlnová funkce se vyvíjí čistě unitárně, tedy deterministicky; „náhoda" je perspektiva jedné větve. Závěr bloku: „QM ⇒ indeterminismus" je non sequitur — platí jen uvnitř kolapsových čtení, tedy předpokládá, co má dokázat. Tady se láme autorova vstupní intuice a text to musí říct bez obalu.
2. **Against A — the prices.** Deterministické záchrany nejsou zadarmo: Bohm platí nelokalitou a potřebou preferované foliace (napětí s relativitou `[VERIFY]`); Everett platí problémem pravděpodobnosti — odkud Bornovy váhy, když se stane všechno (Deutschovo–Wallaceovo rozhodovací odvození existuje a je kontroverzní `[VERIFY]`); superdeterminismus platí vzdáním se statistické nezávislosti volby měření, což vypadá jako kosmická konspirace a podkopává metodologii experimentu (jen ohlásit, hloubka patří do Threads).
3. **Against B — the fringe is being squeezed.** Kolapsové modely nejsou „interpretace", ale soupeřící teorie: predikují drobné odchylky od QM (spontánní radiace `[VERIFY]`). Podzemní testy (Donadi et al., Nature Physics ~2020–2021 `[VERIFY — přesná citace]`) signál nenašly a vyloučily část parametrického prostoru (Diósi–Penrose `[VERIFY]`; aktuální stav CSL `[VERIFY]`) — vše `(as of YYYY-MM)`. Zavést jméno **the decidable fringe**: tohle je testovatelný okraj celé otázky. Pozor na přestřel: ořezání ≠ vyvrácení všech kolapsových modelů; blok musí přesně říct, co je vyloučeno a co ne.

- [x] **Step 2: In-task verifikace empirických jader**

WebSearch/WebFetch: SEP „Bell's Theorem", SEP „Bohmian Mechanics", SEP „Many-Worlds Interpretation", SEP „Collapse Theories"; Bell 1964 (Physics); Donadi et al. Každý `[VERIFY]` v blocích 1–3 vyřešit hned: potvrdit (marker pryč, zdroj + co přesně nese do pracovního seznamu pro Task 7), opravit, nebo tvrzení vypustit. Výjimka: markery čistě citátové/atribuční (přesné znění Bellova citátu) smějí počkat na Task 7.

Run: `grep -n 'VERIFY' reality/determinism.md`
Expected: v blocích 1–3 žádný marker kromě citátových/atribučních; každý zbývající umět přiřadit k Tasku 7.

- [x] **Step 3: Schválení autorem** — výslovně projít blok 1: tady padá jeho vstupní intuice; text musí být tvrdý k intuici a fér k autorovi.

- [x] **Step 4: Commit**

```bash
git add reality/determinism.md
git commit -m "draft determinism: refutations (quantum core)

Co-Authored-By: Claude Opus 5 (1M context) <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01BGtkbfoRJooRXZ44TYKKbg"
```

### Task 4: Refutations — rozhodnutelnost, kategorie, sázky (proti C, D, E)

**Files:**
- Modify: `reality/determinism.md` (sekce `## Refutations & tensions`, bloky 4–6)

**Interfaces:**
- Consumes: konjektury C–E, the decidable fringe (Task 3), the schoolbook picture (Global Constraints).
- Produces: bloky 4–6; kompletní sekce Refutations & tensions.

- [x] **Step 1: Draft bloků 4–6 (v dialogu s autorem)**

Obsahová specifikace:

4. **Against C — decidability leaks in at the edges.** (a) the decidable fringe: právě proto, že kolapsové modely predikují odchylky, není nerozhodnutelnost globální; C je nutné vyslovit přesně — po každém proveditelném experimentu zbývá jádro rivalů (Bohm / Everett / standardní QM), které stále obkračuje obě odpovědi. (b) C tiše předpokládá, že dnešní menu formulací je finální — budoucí teorie může ekvivalenci rozbít, jako ji kolapsové modely už rozbily na okraji. (c) Klasika sama není čistě deterministická: Nortonova kupole — newtonovská ne-jednoznačnost řešení `[VERIFY — Norton, „The Dome", Philosophy of Science ~2008]`; útěk hmotných bodů do nekonečna v konečném čase — noncollision singularities (Xia, Annals of Mathematics ~1992 `[VERIFY]`; popularizace Saari & Xia, Notices of the AMS ~1995 `[VERIFY]`). The schoolbook picture padá na obou polovinách; determinismus se hodnotí teorie po teorii (Earmanův přístup `[VERIFY]`), ne jedním řezem „klasika vs. kvantovka".
5. **Against D — realism bites back.** Pro vědeckého realistu teorie svět reprezentují: má-li naše nejlepší (natož finální) teorie deterministickou dynamiku, je to evidence o světě, ne jen o modelu. D v silné verzi hrozí být verifikacionismus v převleku. Skromné jádro D ale přežívá: determinismus je dobře definovaný jen vůči popisu stavového prostoru — což je přesně důvod, proč Earman postupuje teorie po teorii.
6. **Against E — some things do hang on it.** Libertariánská svoboda indeterminismus *potřebuje* (Kane `[VERIFY]`) — pro celý jeden tábor na odpovědi visí všechno. Jestli ale kvantová náhoda nepercoluje do měřítka neuronů (dekoherence v teplém, mokrém mozku `[VERIFY — kandidát Tegmark 2000; pokud se neověří snadno, jen Threads]`), hádají se oba tábory o irelevantní fyzice. Pereboom: odpovědnost prohrává v *obou* větvích — determinismus i loterie ji berou stejně (hard incompatibilism `[VERIFY]`) — takže na odpovědi nezáleží, ale z hlubšího důvodu, než E tvrdí. Strawson: reaktivní postoje na fyziku nečekají a čekat nemohou `[VERIFY — „Freedom and Resentment" 1962]`. Blok končí: E je napadnutelné z obou stran, a to, co na fyzice nevisí, nevisí z hlubších důvodů, než E udává.

- [x] **Step 2: In-task verifikace empirických jader**

WebSearch/WebFetch: Norton (kupole), Xia/Saari. Markery filosofických atribucí (Kane, Pereboom, Strawson, Earman, Tegmark) smějí počkat na Task 7 — jsou textové, ne empirické.

Run: `grep -n 'VERIFY' reality/determinism.md`
Expected: v blocích 4–6 zbývají jen atribuční markery pro Task 7.

- [x] **Step 3: Check bloků**

Run: `grep -c '^\- \*\*Against' reality/determinism.md` (příp. podle zvoleného lead-in formátu)
Expected: `6`

- [x] **Step 4: Schválení autorem** — zvlášť projít blok 4: refutace páteřní konjektury nesmí být měkčí než ostatní.

- [x] **Step 5: Commit**

```bash
git add reality/determinism.md
git commit -m "draft determinism: refutations (decidability and stakes)

Co-Authored-By: Claude Opus 5 (1M context) <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01BGtkbfoRJooRXZ44TYKKbg"
```

### Task 5: Where it stands

**Files:**
- Modify: `reality/determinism.md` (sekce `## Where it stands`)

**Interfaces:**
- Consumes: kompletní refutace (Tasky 3–4), the folk inference, the decidable fringe.
- Produces: autorův provizorní verdikt + seznam „what would change my mind"; podklad pro destilaci verdiktu do README (Task 8).

- [x] **Step 1: Draft (v dialogu s autorem — u tohoto tasku obzvlášť: je to jeho hlas)**

Plán předepisuje povinné prvky, ne závěr:

1. **Účtování the folk inference:** přežila / padla / v jaké podobě. Očekávání ze specu: padá jako *inference* („QM to dokázala"), zatímco „náhoda může být reálná" přežívá jako otevřená možnost — ale text patří autorovi a vznikne až tady.
2. **Autorův aktuální lean** mezi A–E, vysloveně provizorní; přiznat, co je temperament a co inference.
3. **What would change my mind** s reálnými experimenty: detekce signatur spontánního kolapsu → silný posun k B a proti C; další ořezávání kolapsových modelů → mírný posun od B (fringe se zavírá, C sílí); konsensuální odvození Bornova pravidla v Everettovi → odpadá hlavní cena everettovské větve A; superdeterministický program s testovatelným obsahem → přehodnotit celý rám. U každé položky říct, co by udělala s páteřní C.
4. **Přiznané napětí:** chtít „objektivní posouzení" otázky, jejíž páteřní konjektura tvrdí nerozhodnutelnost, je samo pointa — poctivý verdikt může znít „podstatná část otázky je mimo dosah verdiktů, a tady je přesná hranice".

- [x] **Step 2: Check**

Ručně: sekce obsahuje explicitní větu o osudu the folk inference a seznam změn názoru s aspoň třemi položkami vázanými na experimenty.

- [x] **Step 3: Schválení autorem** — jeho verdikt; bez souhlasu nepokračovat.

- [x] **Step 4: Commit**

```bash
git add reality/determinism.md
git commit -m "draft determinism: where it stands

Co-Authored-By: Claude Opus 5 (1M context) <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01BGtkbfoRJooRXZ44TYKKbg"
```

### Task 6: Threads to pull

**Files:**
- Modify: `reality/determinism.md` (sekce `## Threads to pull`)

**Interfaces:**
- Consumes: celé dosavadní znění.
- Produces: seznam otevřených vláken; dopředné zmínky na budoucí poznámky v `reality/` a `mind/`.

- [ ] **Step 1: Draft (v dialogu s autorem)**

Kandidátní vlákna (výběr a formulace v dialogu):

- Superdeterminismus do hloubky: 't Hooftova celulárně-automatová interpretace `[VERIFY]`, Hossenfelder & Palmer `[VERIFY]` — co přesně by stálo vzdát se statistické nezávislosti.
- Conway–Kochen „free will theorem" a jeho běžná dezčtení `[VERIFY]` — „free will" je tam technický termín.
- Obecná relativita jako samostatná kapitola determinismu: Cauchyho horizonty, strong cosmic censorship, Earmanovy kapitoly `[VERIFY]` — vědomě mimo záběr této poznámky.
- Odvození Bornova pravidla v Everettovi (Deutsch–Wallace) `[VERIFY]` — stav debaty.
- Certifikovaná kvantová náhodnost (device-independent randomness z Bellových testů) `[VERIFY]` — most: za předpokladu ne-superdeterminismu Bell certifikuje náhodu; co přesně to znamená pro C.
- Budoucí sourozenci v `reality/`: šipka času, simulační hypotéza. Budoucí poznámka v `mind/`: svobodná vůle a odpovědnost v plné šíři (E je jen dovětek).

Markery v Threads smějí zůstat jako „co číst" — Threads nejsou tvrzení; ale jména a tituly ověřit v Tasku 7, ať se nedoporučuje neexistující text.

- [ ] **Step 2: Schválení autorem** — jako výše.

- [ ] **Step 3: Commit**

```bash
git add reality/determinism.md
git commit -m "draft determinism: threads to pull

Co-Authored-By: Claude Opus 5 (1M context) <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01BGtkbfoRJooRXZ44TYKKbg"
```

### Task 7: Konsolidační verifikace + Sources

**Files:**
- Modify: `reality/determinism.md` (sekce `## Sources`; opravy kdekoli v textu, kam verifikace zasáhne; statusová řádka)

**Interfaces:**
- Consumes: celé znění s markery `[VERIFY]`; pracovní seznam zdrojů z Tasků 3–4.
- Produces: sekce Sources seskupená podle argumentu s anotacemi; `sources checked` = den tohoto tasku; nula `[VERIFY]` markerů.

- [ ] **Step 1: Sestavit checklist markerů**

Run: `grep -n 'VERIFY' reality/determinism.md`
Každý nalezený marker přiřadit jednomu z bloků níže; žádný nesmí zůstat nepřiřazený.

- [ ] **Step 2: Filosoficko-textový blok**

Ověřit: Laplace, *Essai philosophique sur les probabilités* (1814) — přesná pasáž o démonovi v dostupném překladu; Strawson, „Freedom and Resentment" (1962) — kde vyšlo; van Inwagen, *An Essay on Free Will* (1983) — consequence argument; Pereboom (hard incompatibilism — *Living Without Free Will*, 2001?); Kane (libertarianismus — *The Significance of Free Will*, 1996?). SEP hesla („Causal Determinism", „Free Will", „Incompatibilism") jako sekundární opora — u každého ověřit, že říká, co poznámka tvrdí.

- [ ] **Step 3: Kvantový blok**

Ověřit: Bell 1964 — přesná citace (Physics 1, 195–200?); Bellův citát o Bohmovi — přesné znění a místo (*Speakable and Unspeakable in Quantum Mechanics*); SEP „Bohmian Mechanics", „Many-Worlds Interpretation", „Collapse Theories", „Bell's Theorem" — empirická ekvivalence Bohma, deterministická unitarita Everetta, status Bornova pravidla (Deutsch–Wallace), cena superdeterminismu.

- [ ] **Step 4: Experimentální blok (perishable)**

Ověřit: Donadi et al. — přesná citace a co přesně vyloučili (Diósi–Penrose parametry?); aktuální stav testů kolapsových modelů k datu verifikace (CSL bounds). Všechna tvrzení o stavu experimentů dostávají `(as of YYYY-MM)` podle dne verifikace.

- [ ] **Step 5: Klasický blok**

Ověřit: Norton, „The Dome" — publikace a rok (Philosophy of Science ~2008?); Xia — Annals of Mathematics (~1992); Saari & Xia — „Off to Infinity in Finite Time", Notices of the AMS (~1995); Earman, *A Primer on Determinism* (1986) — přístup „teorie po teorii".

- [ ] **Step 6: Zapsat Sources a vyřešit markery**

Struktura sekce: úvodní odstavec-předmluva zaznamenávající, co verifikace opravila nebo zabila (konvence repa — prohry viditelné, withdrawn s důvodem); pak skupiny podle argumentu, např. **The framing** (Laplace, Earman, SEP), **The quantum core** (Bell, SEP hesla), **The experiments** (Donadi et al., stav kolapsových testů), **The classical surprise** (Norton, Xia/Saari), **The stakes** (Strawson, van Inwagen, Pereboom, Kane). Každá položka s anotací, co přesně nese — ne jen jméno. Neověřitelné: NOT VERIFIED nebo pryč. Aktualizovat statusovou řádku (`sources checked` = dnešek tasku).

- [ ] **Step 7: Check**

Run: `grep -c 'VERIFY' reality/determinism.md`
Expected: `0`

Run: `grep -n 'as of 20' reality/determinism.md`
Expected: každé perishable tvrzení (stav experimentů, „no one has yet…") má `(as of YYYY-MM)`.

- [ ] **Step 8: Schválení autorem** — zejména co verifikace změnila (opravy, withdrawn, NOT VERIFIED).

- [ ] **Step 9: Commit**

```bash
git add reality/determinism.md
git commit -m "verify determinism sources

Co-Authored-By: Claude Opus 5 (1M context) <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01BGtkbfoRJooRXZ44TYKKbg"
```

### Task 8: README ×3 + AGENTS + verdikt

**Files:**
- Modify: `README.md` (sekce „How it's organized" — složková odrážka + odrážka poznámky s verdiktem)
- Modify: `README.cs.md`, `README.pl.md` (zrcadlení + sync datum v hlavičce)
- Modify: `AGENTS.md` (sekce „Structure")

**Interfaces:**
- Consumes: hotové Where it stands (Task 5), hotová poznámka (Task 7).
- Produces: složka `reality/` viditelná ve všech rozcestnících; verdikt poznámky ve třech jazycích.

- [ ] **Step 1: Destilovat verdikt (v dialogu s autorem)**

Pravidla verdiktu (AGENTS.md): jedna věta, destilát z Where it stands, žádné nové tvrzení, ne ostřejší než poznámka, nic perishable (žádná čísla, žádné „as of"). Navrhnout anglicky + česky + polsky, schválit autorem.

- [ ] **Step 2: README.md**

Do seznamu „How it's organized" mezi `mind/` a `religion/` (seznam je abecední):

```markdown
- **`reality/`** — How the world is wired. Determinism and chance, the nature of physical law, and which of those questions observation can even reach.
  - [Determinism](reality/determinism.md) — *<schválený verdikt z Step 1>*
```

- [ ] **Step 3: AGENTS.md**

Do sekce „Structure" mezi `mind/` a `religion/`:

```markdown
- `reality/` — How the world is wired: determinism, chance, the nature of physical law, and what physics can and cannot decide.
```

- [ ] **Step 4: README.cs.md a README.pl.md**

Zrcadlit složkovou odrážku i odrážku poznámky (překlad, verdikt ve schváleném znění z Step 1); aktualizovat datum synchronizace překladu v hlavičce souboru (přesný formát převzít z aktuálního znění obou souborů). Nic jiného v překladech neměnit.

- [ ] **Step 5: Check**

Run: `grep -n 'reality/' README.md README.cs.md README.pl.md AGENTS.md`
Expected: složková odrážka ve všech třech README + řádka v AGENTS; odrážka poznámky ve všech třech README.

- [ ] **Step 6: Schválení autorem** — verdikt je jeho, ve všech třech jazycích.

- [ ] **Step 7: Commit**

```bash
git add README.md README.cs.md README.pl.md AGENTS.md
git commit -m "readme+agents: add reality/ and determinism verdict

Co-Authored-By: Claude Opus 5 (1M context) <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01BGtkbfoRJooRXZ44TYKKbg"
```

### Task 9: Závěrečný průchod

**Files:**
- Modify: `reality/determinism.md` (jen opravy z checků)

**Interfaces:**
- Consumes: hotová poznámka + rozcestníky (Tasky 1–8).
- Produces: finální stav na `main`.

- [ ] **Step 1: Strukturní check**

Run: `grep -n '^## ' reality/determinism.md` → šest sekcí v pořadí šablony.
Run: `grep -n '^\*Status: open · last touched' reality/determinism.md` → 1 řádek, obě data skutečná (last touched = poslední den úprav prózy, sources checked = den Tasku 7).
Run: `grep -c 'to be written' reality/determinism.md` → `0`
Run: `grep -c 'VERIFY' reality/determinism.md` → `0`

- [ ] **Step 2: Check odkazů**

Ručně: každý `[[…]]` v poznámce (pokud nějaký je) míří na existující soubor; zmínky na budoucí poznámky (`mind/`, šipka času) jsou próza, ne `[[…]]`.

- [ ] **Step 3: Check stárnutí a rozsahu**

Run: `grep -n 'as of 20' reality/determinism.md` → každé perishable tvrzení datované; čísla souhlasí se Sources.
Run: `wc -w reality/determinism.md` → ~4000–5500 slov; výrazný přesah řešit s autorem (krácení vs. vědomá výjimka).

- [ ] **Step 4: Čtení celku**

Přečíst poznámku vcelku: tón thinking-in-progress; konzistence pevných jmen (A–E, the folk inference, the decidable fringe, the schoolbook picture); the folk inference testována, ne hájena; refutace C nejsou měkčí než ostatní; E drží jednu konjekturu a neroste; verdikt v README není ostřejší než Where it stands.

- [ ] **Step 5: Finální schválení autorem**

Poslat autorovi celou poznámku; zapracovat poslední úpravy.

- [ ] **Step 6: Commit (jen pokud Step 1–5 něco změnily)**

```bash
git add reality/determinism.md
git commit -m "revise determinism: final pass

Co-Authored-By: Claude Opus 5 (1M context) <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01BGtkbfoRJooRXZ44TYKKbg"
```
