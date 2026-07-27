# Nuclear Blackmail — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Napsat, ověřit a commitnout druhou poznámku složky `war/` — `nuclear-blackmail.md` — podle specu `docs/superpowers/specs/2026-07-27-nuclear-blackmail-design.md`, včetně provedení auditu směnky z [[ukraine-war-justification]] a případné křížové revize.

**Architecture:** Jedna Markdown poznámka ve tvaru `TEMPLATE.md`, architektura „audit s předregistrací": The question cituje oba lokusy směnky a předregistruje výsledky (i)/(ii)/(iii); konjektury A–D jsou soupeři bez předvybraného vítěze; Where it stands vzniká až v draftu průchodem pěti testy. **Autor jde načisto — drafty vznikají z dialogu, ne ze schvalování hotových pozic.** Padne-li výsledek (ii)/(iii), samostatný task edituje ukrajinskou poznámku a zapíše křížovou revizi do obou.

**Tech Stack:** Markdown, git (přímo na `main` — konvence repa), WebSearch/WebFetch pro verifikaci zdrojů.

## Global Constraints

- Poznámka je **anglicky**; pracovní komunikace s autorem česky.
- Cílový soubor: `war/nuclear-blackmail.md`. H1: `# Can a nuclear threat change what is right?`
- Mimo cílovou poznámku se smí měnit **jen** `war/ukraine-war-justification.md`, a to výhradně v Tasku 6 (revizní hák, jen padne-li výsledek (ii)/(iii)) a v Tasku 9 (výhradně opravy konzistence téže revize). Žádné změny README/AGENTS/TEMPLATE/jiných poznámek.
- Pořadí sekcí přesně podle `TEMPLATE.md`; statusová řádka `*Status: open · last touched YYYY-MM-DD · sources checked YYYY-MM-DD*` (data = skutečné dny; `sources checked` finalizuje Task 8).
- Tón: thinking-in-progress, první osoba autora (Petr). **Autor nemá předem pozice** — každý obsahový krok začíná krátkou dialogickou výměnou (návrhy + protinávrhy), teprve pak se píše anglický text; Where it stands (Task 5) je strukturovaný dialog test po testu. Where it stands se na žádnou konjekturu předem neodvolává jako na autorovu.
- **Nikdy necitovat z paměti.** Citáty, atribuce, čísla, data → inline `[VERIFY]`. Empirická fakta nesoucí argument (kotevní blok, epizody červených linií) se ověřují **v tasku, který je zavádí**; texty a zbylé atribuce řeší Task 8. Po Tasku 8: `grep -c 'VERIFY' war/nuclear-blackmail.md` = 0.
- Každé rychle stárnoucí tvrzení nese inline `(as of YYYY-MM)`.
- Křížové odkazy stylem `[[kebab-name]]`.
- Pevná jména (všechny tasky beze změn): **the audited sentence / the IOU**; konjektury **A — Never yield**, **B — The tail dominates**, **C — There is no line**, **D — Build the counter-structure**; bloky **the umbrella admission**, **the Jupiter problem**; testy **the salami test**, **the Kavka test**, **the endogeneity ledger**, **the umbrella consistency test**, **the Jupiter test**; výsledky **(i) paid**, **(ii) paid with amendment**, **(iii) defaulted**.
- Každá obsahová sekce: **schválení autorem před commitem.** Bez schválení se necommituje.
- Commity: krátké, přítomný čas; každý končí trailery:
  `Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>` a
  `Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd`.
- Mimo rozsah: plná etika odstrašení, jiné jaderné dyády nad rámec konzistenčních zmínek, policy advocacy, změny ukrajinské poznámky nad rámec revizního háku.

---

### Task 1: Scaffold + The question

**Files:**
- Create: `war/nuclear-blackmail.md`

**Interfaces:**
- Consumes: `TEMPLATE.md` (tvar); spec sekce „The question"; oba lokusy směnky
  z `war/ukraine-war-justification.md` (citovat doslova ze souboru, ne z paměti).
- Produces: soubor se šesti `##` nadpisy; hotová The question s citovanou směnkou,
  předregistrací (i)/(ii)/(iii), kotevním blokem **„The nuclear record as of
  2026-07"** (bold lead-in, fakta ověřená in-task) a ohlášenou **the umbrella
  admission**. Jména asymetrie výsledků a testů, na která navazují všechny tasky.

- [ ] **Step 1: Založit soubor se skeletem**

Vytvořit `war/nuclear-blackmail.md`:

```markdown
# Can a nuclear threat change what is right?

*Status: open · last touched 2026-07-XX · sources checked 2026-07-XX*

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

(`XX` = skutečný den; `last touched` se aktualizuje s tasky, `sources checked`
finalizuje Task 8.)

- [ ] **Step 2: Check skeletu**

Run: `grep -n '^## ' war/nuclear-blackmail.md`
Expected (přesně toto pořadí):

```
## The question
## Conjectures
## Refutations & tensions
## Where it stands
## Threads to pull
## Sources
```

- [ ] **Step 3: Vytáhnout oba lokusy směnky ze zdrojového souboru**

Run: `grep -n 'constraint on \*how\*' war/ukraine-war-justification.md`
Expected: 2 řádky (blok „Against D" a odstavec o podpoře ve Where it stands).
Citace do The question převzít doslova z aktuálního stavu souboru (kvůli
případným mezitímním úpravám necitovat z tohoto plánu).

- [ ] **Step 4: Draft The question (anglicky, v dialogu s autorem)**

Obsahová specifikace (závazná, formulace vznikne v dialogu):

1. Otevřít směnkou: ukrajinská poznámka unesla verdikt o podpoře na větě, kterou
   si neodpracovala — oba lokusy citovat doslova (blockquote). Tato poznámka je
   audit; kdo audituje vlastní směnku, musí předem říct, jak vypadá propadnutí.
2. **Předregistrace výsledků** (i) paid / (ii) paid with amendment /
   (iii) defaulted — s explicitním závazkem: výsledek a jeho důsledek se zapíší
   do OBOU poznámek (revizní hák, Task 6).
3. Jádrová otázka: **can a nuclear threat change what is right?** Švy držené
   viditelně: prudence vs. dovolení/povinnosti; hrozba odstrašující vs.
   kompelentní (Schelling `[VERIFY]`); povinnosti obránce vs. třetích stran.
4. Kotevní blok **„The nuclear record as of 2026-07."** (bold lead-in uvnitř
   The question): (a) rekord ruských hrozeb 2022–2026 a epizody červených linií
   s daty — HIMARS, tanky, Storm Shadow, ATACMS, F-16, Kursk — každá: hrozba →
   akce → (žádná) jaderná odpověď `[VERIFY: každá epizoda]`; (b) podzimní krize
   2022 `[VERIFY]`; změna doktríny 19. 11. 2024 `[VERIFY: text]`; Bělorusko 2023
   `[VERIFY]`; Oreshnik 11/2024 `[VERIFY]`; stav doktríny k 2026-07 `[VERIFY:
   změny 2025–26]`; (c) base rate: Sechser & Fuhrmann — kompelentní jaderné
   hrozby historicky téměř neuspívají `[VERIFY: přesná teze + čísla]`;
   (d) odzbrojovací případy UA/BY/KZ po 1991, JAR `[VERIFY: JAR]`. Vše
   `(as of YYYY-MM)` + věta o expiraci.
5. **The umbrella admission** (ohlásit, plně v Tasku 4): autorova bezpečnost je
   koupena podmíněnými úmysly, které poznámka zkoumá; analog „daylight asymmetry"
   a „Mnichova v krvi".
6. Proč teď: revizní závazek + živý rekord hrozeb. Křížový odkaz
   [[ukraine-war-justification]] povinně v textu.

- [ ] **Step 5: In-task verifikace kotevního bloku**

WebSearch/WebFetch: časové osy jaderného signalingu (ISW/CSIS/arms-control
zdroje), text/reporting změny doktríny 19. 11. 2024, epizody linií s daty,
Sechser & Fuhrmann (kniha/recenze/dataset), JAR. Markery kotevního bloku vyřešit
hned (potvrdit/opravit/vypustit); zdroje do pracovního seznamu pro Task 8.
Markery mimo kotevní blok (Schelling) zůstávají.

Run: `grep -c 'VERIFY' war/nuclear-blackmail.md`
Expected: jen markery mimo kotevní blok (Schelling — tedy `1`).

- [ ] **Step 6: Schválení autorem**

Česky shrnout, anglický text ukázat celý, zapracovat úpravy. Bez souhlasu
nepokračovat.

- [ ] **Step 7: Commit**

```bash
git add war/nuclear-blackmail.md
git commit -m "add nuclear-blackmail conjecture

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd"
```

### Task 2: Conjectures A–D

**Files:**
- Modify: `war/nuclear-blackmail.md` (sekce `## Conjectures`)

**Interfaces:**
- Consumes: The question (Task 1), jména konjektur (Global Constraints).
- Produces: čtyři konjektury s pevnými jmény, na které se odkazují Tasky 3–5:
  **A — Never yield**, **B — The tail dominates**, **C — There is no line**,
  **D — Build the counter-structure**. Úvodní věta sekce výslovně: none of these
  is mine going in (autor načisto).

- [ ] **Step 1: Dialogická výměna před draftem**

Předložit autorovi česky kostry všech čtyř konjektur (ze specu) + zeptat se:
chybí hlas? má některá dostat jinou nejsilnější formu? Zapracovat odpovědi.

- [ ] **Step 2: Draft (anglicky)**

Formát `- **Conjecture A — Never yield.** …` Obsahová specifikace:

- **A — Never yield.** Universalizace (svět, kde hlavice platí, je svět samých
  hrozeb); pobídková kaskáda; base rate jako opora `[VERIFY: S&F]`. Nejsilnější
  forma: i započítat hrozbu do kalkulu je částečná platba.
- **B — The tail dominates.** Nenulová P(použití) × téměř nekonečná škoda;
  nenumerické hrdinství s cizími městy; „the threat that leaves something to
  chance" `[VERIFY: Schelling — dílo a znění]`; silná forma: zdrženlivé epizody
  války byly správné a víc ústupků by bylo správnějších.
- **C — There is no line.** Každé omezení „jak" doručilo část požadavku (NFZ,
  odklady, žádní vojáci); řízení rizika a částečná kapitulace = tytéž akty pod
  různými popisy; žádná principiální zastávka. Věta: obstojí-li C, směnka
  propadá.
- **D — Build the counter-structure.** Vydírání neživotaschopné ex ante:
  věrohodné rozšířené odstrašení, automatismy, záruky se zuby (ne-Budapešť);
  kde je vydírání kredibilní, někdo už selhal; povinnost leží na deštníkových
  státech před krizí.

- [ ] **Step 3: Check značení**

Run: `grep -c '\*\*Conjecture [A-D]' war/nuclear-blackmail.md`
Expected: `4`

- [ ] **Step 4: Schválení autorem** — zvlášť: jsou to soupeři v plné síle, ani
  jeden slaměný?

- [ ] **Step 5: Commit**

```bash
git add war/nuclear-blackmail.md
git commit -m "draft nuclear-blackmail: conjectures

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd"
```

### Task 3: Refutations — proti A a B

**Files:**
- Modify: `war/nuclear-blackmail.md` (sekce `## Refutations & tensions`, první část)

**Interfaces:**
- Consumes: konjektury (Task 2); kotevní blok (Task 1).
- Produces: dva bloky `**Against A — …**`, `**Against B — …**`, na které se
  odvolává Where it stands (the Kavka test, the endogeneity ledger).

- [ ] **Step 1: Dialogická výměna** — předložit palbu česky, zeptat se na váhy
  (co autora přesvědčuje, co ne); zapracovat.

- [ ] **Step 2: Draft (anglicky)**

Obsahová specifikace:

1. **Against A — the borrowed account, and the price of purity.** Kavkův tlak:
   never-yield stojí na protihrozbě, kterou nikdo nesmí vykonat `[VERIFY: Kavka
   1978, přesná formulace]`; blaf podkopává kredibilitu; je-li odstrašující
   úmysl nepřípustný, norma si půjčuje z insolventního účtu. Čistá forma
   („ignoruj hrozbu v kalkulu") je nesplnitelná a přestává vést jednání.
   Agregační problém: norma utrácí konkrétní města za systémová dobra — dveře
   řežou obousměrně ([[meaning-without-guarantee]] jen při organickém napojení).
   Endogenita base rate poctivě na obě strany: selhávání kompelence je produkt
   vzdoru (norma sebenaplňující) — ale citovat base rate jako nezávislý důkaz
   je kruh.
2. **Against B — the mugger's license, and the missing dynamic term.** Pascalovo
   přepadení: aritmetika s téměř nekonečnem je unesitelná kýmkoli, kdo řekne
   „nebo všechno" — B tiskne licenci budoucím vyděračům. Endogenita P(použití):
   pravděpodobnost reaguje na pobídky; ustoupení zvedá P(hrozba) i P(použití)
   později; statická EV ignoruje dynamický člen. Selektivní konsent: ustoupení
   hází kostkou za budoucí cíle precedentu. Empirie: epizody z kotevního bloku
   — linie překračovány bez jaderné odpovědi; P(použití|vzdor) soustavně
   nadhodnocena (odkázat na kotevní blok, čísla znovu neuvádět).

- [ ] **Step 3: Check bloků**

Run: `grep -c '^\*\*Against' war/nuclear-blackmail.md`
Expected: `2`

- [ ] **Step 4: Schválení autorem.**

- [ ] **Step 5: Commit**

```bash
git add war/nuclear-blackmail.md
git commit -m "draft nuclear-blackmail: refutations against A and B

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd"
```

### Task 4: Refutations — proti C a D + průřezové bloky

**Files:**
- Modify: `war/nuclear-blackmail.md` (sekce `## Refutations & tensions`, druhá část)

**Interfaces:**
- Consumes: bloky Tasku 3.
- Produces: bloky `**Against C — …**`, `**Against D — …**`, `**The umbrella
  admission.**`, `**The Jupiter problem.**` — na poslední dva se odvolává Where
  it stands (the umbrella consistency test, the Jupiter test).

- [ ] **Step 1: Dialogická výměna** — jako Task 3 Step 1.

- [ ] **Step 2: Draft (anglicky)**

Obsahová specifikace:

1. **Against C — dusk does not abolish day.** Čára u doručení požadavku:
   zdrženlivost rozkládající riziko, kterou vyděrač nežádal ≠ doručení žádané
   položky; sorites nepřenáší; těžké případy vyžadují soud, ne kapitulaci
   pojmu. C dokazuje příliš: pak je kapitulací i odstrašení. **Zapsat, co z C
   přežívá:** střední cesta musí zastavení UKÁZAT; auditovaná věta byla gesto —
   předjímka výsledku (ii).
2. **Against D — advice to the past.** Mění téma na účet oběti (co teď,
   s architekturou, kterou jsme nepostavili); automatismy kupují
   blackmail-proofing za riziko nehody (kubánské near-misses `[VERIFY]`);
   rozšířené odstrašení JE podmíněný úmysl krát spojenci — D dědí Kavku.
3. **The umbrella admission.** Autor žije pod deštníkem NATO; závěr
   o nepřípustnosti odstrašení by mu vystavil účet (vystoupit?); závěr
   o přípustnosti dluží argument. Bez schovávání za analýzu.
4. **The Jupiter problem.** Kuba 1962: veřejný vzdor + tichý ústupek (Jupitery
   z Turecka `[VERIFY: NSA]`) — vlajková loď never-yield obsahuje skrytý
   obchod. Co to dělá s A: fungující pokrytectví jako datový bod o čáře
   (tajnost ústupku = přiznání, že veřejné doručení požadavku učí, soukromé
   možná ne?).

- [ ] **Step 3: Check bloků**

Run: `grep -c '^\*\*Against' war/nuclear-blackmail.md`
Expected: `4`

Run: `grep -n '^\*\*The umbrella admission\|^\*\*The Jupiter problem' war/nuclear-blackmail.md`
Expected: 2 řádky.

- [ ] **Step 4: Schválení autorem** — výslovně bloky 3 a 4 (osobní kotva
  a nejtěžší protipříklad).

- [ ] **Step 5: Commit**

```bash
git add war/nuclear-blackmail.md
git commit -m "draft nuclear-blackmail: refutations against C and D, cross-blocks

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd"
```

### Task 5: Where it stands — pětitestová procedura

**Files:**
- Modify: `war/nuclear-blackmail.md` (sekce `## Where it stands`)

**Interfaces:**
- Consumes: všechny bloky refutací; jména testů a výsledků (Global Constraints).
- Produces: vyhlášený výsledek auditu — **(i) paid / (ii) paid with amendment /
  (iii) defaulted**, případně poctivé nerozhodnuto s rozhodovacím kritériem —
  a ≥ 4 odrážky **What would change my mind**. Na výsledek navazuje Task 6.

- [ ] **Step 1: Strukturovaný dialog — test po testu**

Pět testů předložit autorovi JEDNOTLIVĚ (každý: shrnutí relevantní palby +
kandidátní odpovědi + prostor pro vlastní formulaci); zachytit jeho verdikt
a důvod u každého:

1. **The salami test:** umí čára říct zastavení pravidlem pro NFZ / načasování
   ATACMS / žádné vojáky?
2. **The Kavka test:** potřebuje never-yield přípustný odstrašující úmysl —
   a existuje?
3. **The endogeneity ledger:** přebijí dynamické členy statický ocásek? Vypsat
   předpoklady.
4. **The umbrella consistency test:** unese autor závěr jako obyvatel deštníku?
5. **The Jupiter test:** norma, nebo fungující pokrytectví?

- [ ] **Step 2: Syntéza výsledku**

Autor volí (i)/(ii)/(iii), nebo nerozhodnuto + co by rozhodlo. Zapsat jeho
zdůvodnění (v jeho hlasu — vznikne z odpovědí Step 1).

- [ ] **Step 3: Draft sekce (anglicky)**

Struktura: průchod pěti testy s verdikty → vyhlášení výsledku → důsledek
(ohlásit Task 6, padne-li (ii)/(iii)) → **What would change my mind** (≥ 4
odrážky formulované podle výsledku).

- [ ] **Step 4: Checks**

Run: `grep -n 'What would change my mind' war/nuclear-blackmail.md`
Expected: 1 výskyt; pod ním ≥ 4 odrážky.

Run: `grep -n 'paid with amendment\|defaulted\|(i) paid\|the IOU' war/nuclear-blackmail.md`
Expected: vyhlášení výsledku přítomno ve Where it stands.

- [ ] **Step 5: Schválení autorem** — je to JEHO verdikt; anglické znění ukázat
  celé.

- [ ] **Step 6: Commit**

```bash
git add war/nuclear-blackmail.md
git commit -m "draft nuclear-blackmail: where it stands

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd"
```

### Task 6: Revizní hák (podmíněný — jen při výsledku (ii)/(iii))

**Files:**
- Modify: `war/ukraine-war-justification.md` (jen oba lokusy směnky + Sources
  preambule + statusová řádka)
- Modify: `war/nuclear-blackmail.md` (jen doplnění křížového záznamu, je-li
  třeba)

**Interfaces:**
- Consumes: výsledek Tasku 5.
- Produces: obě poznámky konzistentní; revize viditelně zaznamenaná v obou.

- [ ] **Step 1: Větvení podle výsledku**

Výsledek (i) paid → ukrajinská poznámka se NEMĚNÍ; zkontrolovat, že vindikace
je zapsaná ve Where it stands nové poznámky; Task 6 končí bez commitu.
Výsledek (ii)/(iii) → pokračovat.

- [ ] **Step 2: Editovat oba lokusy směnky**

Vytáhnout aktuální znění: `grep -n 'constraint on \*how\*' war/ukraine-war-justification.md`
(2 řádky — blok Against D a odstavec o podpoře). Nahradit podle výsledku:

- **(ii) paid with amendment:** větu přeformulovat podle amendmentu z Tasku 5
  (např. doplnit kritérium zastavení), + doplnit za ni: „(Amended YYYY-MM-DD
  after the audit in [[nuclear-blackmail]]; the original sentence promised more
  than it had argued.)"
- **(iii) defaulted:** větu nahradit poctivou opravou verdiktu o podpoře podle
  Tasku 5, + tentýž dovětek s „the original claim did not survive the audit".

- [ ] **Step 3: Zaznamenat revizi v Sources ukrajinské poznámky**

Do preambule Sources přidat větu: co se změnilo, proč, odkaz
[[nuclear-blackmail]], datum. Aktualizovat `last touched` ukrajinské poznámky.

- [ ] **Step 4: Check konzistence**

Run: `grep -c 'never on \*whether\*' war/ukraine-war-justification.md`
Expected: `0` při výsledku (ii)/(iii) s reformulací obou lokusů (nebo počet
odpovídající amendmentu — původní absolutní znění nesmí přežít beze změny).

Run: `grep -n 'nuclear-blackmail' war/ukraine-war-justification.md`
Expected: ≥ 1 (křížový odkaz revize).

- [ ] **Step 5: Schválení autorem** — edit CIZÍ (už publikované) poznámky;
  ukázat diff obou lokusů.

- [ ] **Step 6: Commit (jen při (ii)/(iii))**

```bash
git add war/ukraine-war-justification.md war/nuclear-blackmail.md
git commit -m "revise ukraine-war-justification: pay the nuclear IOU

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd"
```

### Task 7: Threads to pull

**Files:**
- Modify: `war/nuclear-blackmail.md` (sekce `## Threads to pull`)

**Interfaces:**
- Consumes: refutace, výsledek auditu.
- Produces: pět nitek; odkazy, které kontroluje Task 9.

- [ ] **Step 1: Draft (v dialogu s autorem)**

Pět odrážek (obsahová specifikace):

1. **Plná etika odstrašení.** Kavka, Finnis/Boyle/Grisez, Ramsey — kandidát na
   vlastní poznámku; tato jen půjčovala tlak.
2. **Proliferační pokračování Budapešti.** Napojit na vlákno „co dluží
   signatáři" v [[ukraine-war-justification]].
3. **Kuba 1962 do epistemologie analogií.** Vlajkový případ s tajným ústupkem
   → co dělá tajnost s lekčním efektem precedentu (napojení na Mnichov vs.
   Finsko).
4. **Rodina strukturálních kritérií.** Test doručení požadavku vedle
   vstupní/výstupní asymetrie a jednosměrných dveří ([[meaning-without-guarantee]])
   — meta-poznámka o tvaru „nech strukturu rozhodnout".
5. **Kolektivní konsent pod existenčním rizikem.** Kdo smí házet kostkou za
   nesouhlasící — navazuje na „who speaks for Ukraine's choice".

- [ ] **Step 2: Schválení autorem.**

- [ ] **Step 3: Commit**

```bash
git add war/nuclear-blackmail.md
git commit -m "draft nuclear-blackmail: threads to pull

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd"
```

### Task 8: Konsolidační verifikace + Sources

**Files:**
- Modify: `war/nuclear-blackmail.md` (řešení zbylých `[VERIFY]`; sekce
  `## Sources`; datum `sources checked`; kontrola stárnutí kotevního bloku)

**Interfaces:**
- Consumes: zbylé markery z Tasků 1–7 + pracovní seznam zdrojů z in-task
  verifikací.
- Produces: text bez markerů; Sources po vzoru předchozích poznámek (skupiny,
  anotace, preambule s opravami, NOT VERIFIED viditelně).

- [ ] **Step 1: Checklist markerů**

Run: `grep -n 'VERIFY' war/nuclear-blackmail.md`
Expected: seznam — každý dostane řešení níže.

- [ ] **Step 2: Textový blok — teorie**

Schelling: *The Strategy of Conflict* (1960) vs. *Arms and Influence* (1966) —
které dílo nese deterrence/compellence a které „the threat that leaves
something to chance"; přesná znění. Kavka, „Some Paradoxes of Deterrence",
*J. Phil.* 75:6 (1978) — přesné formulace. Sechser & Fuhrmann (2017) — teze
a čísla datasetu. Walzer (odstrašení/supreme emergency) a Finnis/Boyle/Grisez
(1987) jen v použitém rozsahu. Fail-mode pozor: plausibilní fabrikát —
přijmout jen viděný text.

- [ ] **Step 3: Historický blok**

Kuba 1962 / Jupitery: National Security Archive či ekvivalent. Epizody
červených linií: znovu projít data z Tasku 1 (mohla zastarat). Doktrína
k 2026-07: dohledat případné změny 2025–26. JAR a UA/BY/KZ odzbrojení.

- [ ] **Step 4: Zapsat Sources a vyřešit markery**

Skupiny: Theory / The nuclear record 2022–2026 / History (Cuba, disarmament) /
Inherited from the Ukraine note. Preambule poctivě: co verifikace opravila
(i „nic" je záznam); NOT VERIFIED s důvodem; perishables `(as of …)`.
Aktualizovat `sources checked`.

Run: `grep -c 'VERIFY' war/nuclear-blackmail.md`
Expected: `0`

- [ ] **Step 5: Schválení autorem** — zejména co verifikace změnila.

- [ ] **Step 6: Commit**

```bash
git add war/nuclear-blackmail.md
git commit -m "verify nuclear-blackmail sources; record corrections

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd"
```

### Task 9: Závěrečný průchod

**Files:**
- Modify: `war/nuclear-blackmail.md` (jen opravy z checků); případně
  `war/ukraine-war-justification.md` (jen konzistence křížové revize)

**Interfaces:**
- Consumes: hotová poznámka z Tasků 1–8; stav ukrajinské poznámky po Tasku 6.
- Produces: finální stav na `main`.

- [ ] **Step 1: Strukturní check**

Run: `grep -n '^## ' war/nuclear-blackmail.md`
Expected: šest sekcí v pořadí šablony.

Run: `grep -n '^\*Status: open · last touched' war/nuclear-blackmail.md`
Expected: 1 řádek, obě data skutečná.

Run: `grep -c 'to be written' war/nuclear-blackmail.md`
Expected: `0`

- [ ] **Step 2: Check odkazů a křížové konzistence**

Run: `ls war/ukraine-war-justification.md meaning/meaning-without-guarantee.md`
Expected: oba existují.

Dále ručně: každý `[[…]]` míří na existující soubor; výsledek auditu ve Where
it stands odpovídá stavu ukrajinské poznámky (při (i): směnka tam beze změny;
při (ii)/(iii): revize provedena a zaznamenána v obou).

- [ ] **Step 3: Check stárnutí**

Run: `grep -n 'as of 20' war/nuclear-blackmail.md`
Expected: každé rychle stárnoucí tvrzení datované; žádné nedatované perishable.

- [ ] **Step 4: Čtení celku**

Tón; konzistence pevných jmen (IOU, A–D, testy, výsledky); žádná konjektura
předem autorova; umbrella admission přítomna v The question i refutacích;
Jupiter problem zapsán; výsledek auditu vyhlášen a vykonán.

- [ ] **Step 5: Finální schválení autorem.**

- [ ] **Step 6: Commit (jen pokud Step 1–5 něco změnily)**

```bash
git add war/nuclear-blackmail.md war/ukraine-war-justification.md
git commit -m "revise nuclear-blackmail: final pass

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd"
```
