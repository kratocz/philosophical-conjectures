# Ukraine War Justification — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Napsat, ověřit a commitnout první poznámku nové složky `war/` — `ukraine-war-justification.md` — podle specu `docs/superpowers/specs/2026-07-24-ukraine-war-justification-design.md`.

**Architecture:** Jedna Markdown poznámka ve tvaru `TEMPLATE.md`, architektura „dvě asymetrie jako páteř": otázkou je oprávněnost *prodlužování* války; konjektury A–E jsou soupeřící verdikty; tři vrstvy (invaze / obrana / podpora) vystupují jako důsledky asymetrií. Drafty vznikají po sekcích v dialogu s autorem. Verifikace je dvoustupňová: empirická fakta se ověřují už při draftování své sekce, textové citace a atribuce v konsolidačním Tasku 7; vše rychle stárnoucí nese `(as of YYYY-MM)`.

**Tech Stack:** Markdown, git (přímo na `main` — konvence repa), WebSearch/WebFetch pro verifikaci zdrojů.

## Global Constraints

- Poznámka je **anglicky**; pracovní komunikace s autorem česky.
- Cílový soubor: `war/ukraine-war-justification.md`. H1: `# Who could end the war in Ukraine tomorrow — and what justifies not doing it?`
- Mimo cílovou poznámku se mění **jen** `README.md` a `AGENTS.md` (řádka složky `war/`, Task 1). Žádné změny TEMPLATE/CONTRIBUTING ani jiných poznámek.
- Pořadí sekcí přesně podle `TEMPLATE.md`; statusová řádka `*Status: open · last touched YYYY-MM-DD · sources checked YYYY-MM-DD*` (data = skutečné dny činností; `sources checked` se finalizuje v Tasku 7).
- Tón: thinking-in-progress, první osoba autora (Petr), „my best current guess"; verdikt se v refutacích zaslouží, nepředpokládá.
- **Nikdy necitovat z paměti.** Každý citát, atribuce, číslo, datum nebo poměr hlasů jde do draftu s inline markerem `[VERIFY]`. Empirická fakta nesoucí argument (kotevní blok, čísla v refutacích) se ověřují **už v tasku, který je zavádí**; textové citace a zbylé atribuce řeší Task 7. Po Tasku 7: `grep -c 'VERIFY' war/ukraine-war-justification.md` = 0.
- Každé rychle stárnoucí tvrzení (stav fronty, čísla obětí, objemy podpory, průzkumy, stav řízení) nese inline `(as of YYYY-MM)`.
- Křížové odkazy stylem `[[kebab-name]]` (bez cesty, bez přípony).
- Pevná jména, která používají všechny tasky beze změn (definována zde, poprvé vyslovena v The question, plně nasazena v konjekturách):
  - **the entry asymmetry** — kdo první použil fyzickou sílu přes hranici, je ověřitelný fakt; podezření útok nelicencuje (universalizace + **the domestic analogy**),
  - **the exit asymmetry** — Rusko může válku kdykoli jednostranně ukončit stažením; ukrajinské „ukončení" končí Ukrajinu, ne válku,
  - **the standing argument** — cenu svobody smí vážit jen ten, kdo ji platí,
  - konjektury: **A — The Russian case for war**, **B — Nobody's war is just**, **C — The realist dissolution**, **D — A just defense meets its limit**, **E — Two asymmetries and a burden**.
- Každá obsahová sekce: **schválení autorem před commitem** (konjektury i verdikt jsou autorovy; role asistenta: struktura, formulace, protiargumenty, verifikace). Bez schválení se necommituje.
- Commity: krátké, přítomný čas; každý končí trailery:
  `Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>` a
  `Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd`.
- Jus in bello se neadjudikuje (jen zmínka s ukazateli); žádné vojenské predikce; jiné konflikty jen jako konzistenční zmínky.

---

### Task 1: Scaffold + složka war/ + The question

**Files:**
- Create: `war/ukraine-war-justification.md`
- Modify: `README.md` (sekce „How it's organized" — nová odrážka mezi `religion/` a závěrečnou větou; seznam je abecední, `war/` patří na konec)
- Modify: `AGENTS.md` (sekce „Structure" — tamtéž)

**Interfaces:**
- Consumes: `TEMPLATE.md` (tvar), spec sekce „The question" a „Kontext k datu návrhu".
- Produces: soubor se všemi šesti `##` nadpisy, hotovou sekcí The question včetně kotevního bloku **„The war as of 2026-07"** (bold lead-in, ne `###` — repo styl), H1 a statusová řádka; řádky složky `war/` v README a AGENTS. Na jména **the entry asymmetry**, **the exit asymmetry**, **the domestic analogy** navazují všechny další tasky.

- [ ] **Step 1: Založit soubor se skeletem**

Vytvořit `war/ukraine-war-justification.md`:

```markdown
# Who could end the war in Ukraine tomorrow — and what justifies not doing it?

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

(`XX` = den, kdy Task 1 skutečně běží; `last touched` se aktualizuje s každým dalším taskem, `sources checked` finalizuje Task 7.)

- [ ] **Step 2: Check skeletu**

Run: `grep -n '^## ' war/ukraine-war-justification.md`
Expected (přesně toto pořadí):

```
## The question
## Conjectures
## Refutations & tensions
## Where it stands
## Threads to pull
## Sources
```

- [ ] **Step 3: Přidat řádky složky do README a AGENTS**

`README.md`, do seznamu „How it's organized" za řádku `religion/`:

```markdown
- **`war/`** — The ethics of war, tested on the one running now: who started it, who keeps it going, and what bystanders owe.
```

`AGENTS.md`, do sekce „Structure" za řádku `religion/`:

```markdown
- `war/` — The ethics of war: aggression, defense, prolongation, and third-party duties, tested on the war in Ukraine.
```

- [ ] **Step 4: Draft The question (anglicky, v dialogu s autorem)**

Obsahová specifikace (závazná, formulace vznikne v dialogu):

1. Otevřít oběma asymetriemi jako ověřitelnými fakty, ne názory: **the entry
   asymmetry** (ruští vojáci překročili ukrajinskou hranici, ne naopak — kdo první
   použil fyzickou sílu přes hranici, je checkovatelné) a **the exit asymmetry**
   (válka může skončit kterýkoli den ruským stažením; ukrajinské „ukončení" končí
   Ukrajinu, ne válku). Z obou plyne přesměrování otázky: ne „smí se Ukrajina
   bránit?" — dotaz adresovaný oběti — ale **„je Putinovo odmítání válku ukončit
   podložené něčím, co obstojí?"**
2. Metodický tah: **the domestic analogy** v autorově formulaci (nemohu někoho
   zmlátit na ulici a obhájit se pocitem, že mi chtěl ublížit) + universalizace
   (svět, kde podezření licencuje preventivní útok, je svět permanentní války).
   Poznamenat konvergenci s Walzerem `[VERIFY]` a standardem Caroline / čl. 51
   `[VERIFY]` — autor k nim došel nezávisle, literatura je opora, ne autorita.
3. Švy držené viditelně (půl práce poznámky): legálnost ≠ morálnost; zahájení
   (2014/2022) ≠ pokračování (2026) ≠ vedení války (jus in bello — mimo záběr, jen
   ukazatele); fakt ≠ standard (asymetrie jsou fakta; filosofická práce je ukázat,
   proč jsou rozhodující).
4. Co z odpovědi plyne: meze ukrajinské obrany a povinnosti třetích stran — tři
   vrstvy z původní otázky, uvedené jako důsledky, ne osnova.
5. Kotevní blok **„The war as of 2026-07."** (bold lead-in + krátký odstavec či
   odrážky): plnohodnotná invaze od 24. 2. 2022, válka od 2014 (Krym) `[VERIFY]`;
   krátká příměří jara 2026 nevydržela `[VERIFY]`; diplomacie uvázlá v březnu, oživovaná
   v červenci 2026 `[VERIFY]`; pomalý ruský postup (~31 km² za 30 dní k 30. 6. 2026,
   Economist) `[VERIFY]`; řádové ztráty a vysídlení `[VERIFY]`; objem západní podpory
   `[VERIFY]`. Vše s `(as of 2026-MM)`. Blok výslovně uvést větou o expiraci: fakta
   níže jsou snímek k datu `sources checked`, filosofická páteř na nich závisí jen
   v označených místech.
6. Motivace: proč to řeší Čech (Mnichov, malé národy vedle velkých — jen ohlásit,
   plně až v konjektuře E a refutacích) a proč teď (tlak na Kyjev v běžící
   diplomacii). Křížový odkaz zatím žádný; [[meaning-without-guarantee]] přijde až
   ve Where it stands / Threads.

- [ ] **Step 5: Ověřit fakta kotevního bloku (in-task verifikace)**

WebSearch/WebFetch: ISW/Critical Threats (červenec 2026), Russia Matters report card
(1. 7. 2026), Economist (30. 6. 2026), Wikipedia jen jako rozcestník k primárům.
Každý `[VERIFY]` v kotevním bloku vyřešit hned: potvrdit (marker pryč, zdroj si
poznamenat do pracovního seznamu pro Task 7 Sources), opravit, nebo tvrzení vypustit.
Textové markery mimo kotevní blok (Walzer, Caroline) zůstávají na Task 7.

Run: `grep -c 'VERIFY' war/ukraine-war-justification.md`
Expected: jen markery mimo kotevní blok (Walzer, Caroline — tedy `2`).

- [ ] **Step 6: Schválení autorem**

Předložit draft sekce autorovi (česky shrnout, anglický text ukázat). Zapracovat
úpravy. Bez explicitního souhlasu nepokračovat.

- [ ] **Step 7: Commit**

```bash
git add war/ukraine-war-justification.md README.md AGENTS.md
git commit -m "add ukraine-war-justification conjecture

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd"
```

(Zpráva podle specu — tento commit zavádí poznámku i složku; další tasky revidují.)

### Task 2: Conjectures A–E

**Files:**
- Modify: `war/ukraine-war-justification.md` (sekce `## Conjectures`)

**Interfaces:**
- Consumes: H1, The question, jména asymetrií (Task 1).
- Produces: pět konjektur s pevnými jmény (viz Global Constraints), na která se
  odkazují Tasky 3–6: **A — The Russian case for war**, **B — Nobody's war is
  just**, **C — The realist dissolution**, **D — A just defense meets its limit**,
  **E — Two asymmetries and a burden**.

- [ ] **Step 1: Draft pěti konjektur (v dialogu s autorem)**

Formát: `- **Conjecture A — The Russian case for war.** …` Každá vyslovena odvážně;
hedging až v refutacích. Obsahová specifikace:

- **A — The Russian case for war.** Steelman, formulovaný tak silně, aby vyvrácení
  něco vážilo: expanze NATO jako existenční hrozba (Bukurešť 2008 `[VERIFY]`);
  ochrana rusky mluvících a Donbasu; kosovský precedent + „pozvání" uznaných
  republik `[VERIFY]`; specificky pro pokračování 2026: anektované oblasti ústavně
  ruské `[VERIFY]`, západním zárukám nelze věřit, bez vyřešení „root causes" je
  válka jen odložená a horší — pokračovat je cesta k trvalému míru.
- **B — Nobody's war is just.** Pacifistický verdikt: válka jako metoda je
  neobhajitelná; nemorální je každý den pokračování všemi stranami; jediný morální
  požadavek je okamžité příměří; západní zbraně přikládají pod kotel (proxy-war
  čtení jako morální bratranec).
- **C — The realist dissolution.** Kategorie oprávněnosti na mezinárodní anarchii
  nesedí: státy sledují bezpečnost, morální slovník je dekorace; reálné otázky jsou
  jen prudenciální. Nejostřejší forma: Mearsheimerovo „je to vina Západu"
  `[VERIFY]`.
- **D — A just defense meets its limit.** Nejsilnější rival autorovy pozice: invaze
  neoprávněná, obrana zprvu oprávněná — ale proporcionalita se přepočítává průběžně
  (jus ex bello `[VERIFY: Moellendorf]`): padlí, demografie, destrukce, jaderné
  riziko a globální dopady mohou převážit, co ještě lze bojem získat; od toho bodu
  je vyjednávání povinnost a povinnost třetích stran se překlápí ze zbrojení na
  tlak k dohodě. Empirický exponát: „lepší mír byl k mání dřív" (Istanbul 2022
  `[VERIFY]`).
- **E — Two asymmetries and a burden.** Autorova pozice: agresi fixuje **the entry
  asymmetry** (první fyzický přeshraniční útok; podezření nelicencuje —
  universalizace + the domestic analogy). Prodlužování je každodenní ruská volba
  (**the exit asymmetry**) a nic z A neobstojí — neoprávněné právně i morálně.
  Obrana oprávněná bez vnější povinnosti ustoupit (**the standing argument**).
  Podpora oprávněná, spíš povinná a fakticky nedostatečná — Mnichov 1938 jako
  epistemická kotva, Budapešťské memorandum `[VERIFY]` jako závazkový háček.

- [ ] **Step 2: Check značení**

Run: `grep -c '\*\*Conjecture [A-E]' war/ukraine-war-justification.md`
Expected: `5`

- [ ] **Step 3: Schválení autorem** — jako Task 1 Step 6.

- [ ] **Step 4: Commit**

```bash
git add war/ukraine-war-justification.md
git commit -m "draft ukraine-war-justification: conjectures

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd"
```

### Task 3: Refutations — proti rivalům (A, B, C)

**Files:**
- Modify: `war/ukraine-war-justification.md` (sekce `## Refutations & tensions`, první část)

**Interfaces:**
- Consumes: jména konjektur (Task 2), jména asymetrií (Task 1).
- Produces: tři bloky s tučnými lead-iny, na které se odvolává Where it stands:
  `**Against A — …**`, `**Against B — …**`, `**Against C — …**`. Empirická jádra
  (chronologie 2014, OHCHR trend, poměry hlasů) ověřená in-task.

- [ ] **Step 1: Draft (v dialogu s autorem)**

Obsahová specifikace, v tomto pořadí:

1. **Against A — the chronology problem, and protection that multiplies harm.**
   (a) Chronologie: Krym (únor 2014) `[VERIFY]` předchází každému údajnému
   spouštěči z 2022; Ukrajina neměla MAP `[VERIFY]`; historiografie „slibu
   o nerozšiřování" poctivě — Kramer 2009 vs. Sarotte 2021 `[VERIFY]`, závěr jen
   takový, jaký prameny unesou. (b) Ochrana, která násobí škodu: civilní oběti na
   Donbasu před invazí klesaly `[VERIFY: OHCHR čísla]`, po invazi vzrostly o řády
   `[VERIFY]`; „genocida" bez důkazů (stav u ICJ `[VERIFY]`). (c) Právní lešení
   padá: čl. 2(4) `[VERIFY: znění]`; Nikaragua 1986 — pozvání loutkových entit
   nelegalizuje intervenci `[VERIFY]`; ES-11/1 (141:5) a ES-11/4 (143:5)
   `[VERIFY: poměry]`; Kosovo jako disanalogie `[VERIFY: fakta jen v použitém
   rozsahu]` — a kdyby bylo Kosovo špatně, nelicencuje to nic (dvě křivdy).
   (d) Specificky k pokračování: požadavky rostly s válečným štěstím `[VERIFY:
   doložit posun požadavků]`; anexe oblastí, které Rusko nekontroluje `[VERIFY]`;
   „nedůvěra v záruky" je symetrická — ruský rejstřík (Budapešť, Minsk `[VERIFY]`)
   ji diskvalifikuje jako důvod pokračovat.
2. **Against B — "stop shooting" is not one demand but two.** Agresorovo zastavení
   končí válku, obráncovo končí obránce — pacifistův imperativ se v asymetrické
   situaci rozpadá na dva s opačným obsahem; příměří-hned zmrazuje dobytí →
   odměňuje agresi → zvyšuje pravděpodobnost dalších válek; poctivá cena
   pacifismu: práva existující jen z milosti agresorů (Orwell 1942 jen s ověřeným
   zněním `[VERIFY]`, jinak vlastními slovy).
3. **Against C — the slide from is to ought.** Z „státy sledují zájmy" neplyne
   „mají"; performativní rozpor (i Rusko zdůvodňuje — prostor důvodů je
   konstitutivní, ne dekorace); „buffer state" myšlení upírá Ukrajině agenci —
   přesně to, co the standing argument odhaluje; Mearsheimerovy konkrétní výroky
   jen ověřené `[VERIFY]`. Zaznamenat, co z C přežívá: opatrnost vůči eskalační
   pýše je reálná constraint, kterou E vstřebává (předjímka Against D).

- [ ] **Step 2: In-task verifikace empirických jader**

WebSearch/WebFetch: OHCHR (trend civilních obětí Donbas 2018–2021 a kumulativ po
2022), UN press releases k ES-11/1 a ES-11/4 (poměry hlasů), časová osa anexí
a posunu ruských požadavků. Markery těchto čísel vyřešit hned; textové citace
(Kramer/Sarotte, Orwell, Mearsheimer, znění čl. 2(4), Nikaragua, Kosovo) nechat
na Task 7.

- [ ] **Step 3: Check bloků**

Run: `grep -c '^\*\*Against' war/ukraine-war-justification.md`
Expected: `3`

- [ ] **Step 4: Schválení autorem** — zvlášť projít, že steelman A je vyvracen
  v nejsilnější formě (ne slaměný panák).

- [ ] **Step 5: Commit**

```bash
git add war/ukraine-war-justification.md
git commit -m "draft ukraine-war-justification: refutations against the rivals

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd"
```

### Task 4: Refutations — proti autorovi (D v plné síle, palba na E)

**Files:**
- Modify: `war/ukraine-war-justification.md` (sekce `## Refutations & tensions`, druhá část)

**Interfaces:**
- Consumes: bloky Tasku 3; jména asymetrií a konjektur; the standing argument.
- Produces: osm bloků, na které se Where it stands odvolává jmény:
  `**Against D — the case at full strength.**`, `**The reply from standing — and
  its double edge.**`, `**The door cuts both ways.**`, `**Against E — the Kursk
  objection.**`, `**Against E — the mirror move, and the missing endpoint.**`,
  `**Against E — Munich against Finland.**`, `**Against E — "too little" must
  survive the numbers.**`, `**Against E — consistency, and an admission.**`

- [ ] **Step 1: Draft (v dialogu s autorem)**

Obsahová specifikace, v tomto pořadí:

1. **Against D — the case at full strength.** Nejdřív plná síla rivala: padlí
   v řádech statisíců napříč stranami `[VERIFY: rozptyl odhadů + atribuce]`;
   demografie a vysídlení `[VERIFY: UNHCR]`; destrukce; jaderný ocásek rizika
   (i malé p × katastrofa); Istanbul 2022 jako exponát „lepší mír byl k mání dřív"
   `[VERIFY: Charap & Radchenko]`; zmenšující se vojenské vyhlídky `[VERIFY: stav
   fronty]`. Pak odpovědi E: hlavní dvě mají vlastní bloky (2–3); k tomu přímo
   zde (a) na jádro — riziko absorbovat jako omezení *jak* eskalovat podporu, ne
   *zda* se bránit, jinak se jaderné vydírání stává universálním paklíčem
   a proliferační pobídkou (universalizace podruhé; inverze poučení z Budapešti);
   (b) na Istanbul — jádrem krachu byly nedotažené bezpečnostní záruky `[VERIFY:
   Charap & Radchenko]` a ruský rejstřík dodržování (Against A, bod d) dělá
   z „lepšího míru tehdy" nefalzifikovatelnou hypotézu. Přiznat, kde se E ohýbá.
2. **The reply from standing — and its double edge.** Vážení cena/zisk patří tomu,
   kdo platí — the standing argument. Jenže řeže obousměrně: pokud ukrajinská
   většina začne preferovat dohodu `[VERIFY: KIIS/Gallup trend 2022→2026]`, E musí
   dohodu podpořit; standing umlčuje vnější jestřáby stejně jako vnější holubice.
   E ≠ „bojovat věčně"; E = „volba patří platícím". Zbytkový spor s D se zužuje na
   otázku: smí třetí strany podmiňovat podporu tlakem na jednání?
3. **The door cuts both ways.** Rekurze jednosměrných dveří
   ([[meaning-without-guarantee]]): kapitulace je kvazi-nevratná (okupovaná země
   a lidé pod okupací východ nemají), obrana volbu drží — ale mrtví taky nemají
   opce. Argument zakládá silný default, ne absolutno; zapsat jako reálné pnutí
   uvnitř E, ne odbýt rétorikou.
4. **Against E — the Kursk objection.** Srpen 2024 – jaro 2025: ukrajinská vojska
   na ruském území `[VERIFY: časové rozpětí]` — kritérium „čí vojáci kde" je moc
   hrubé. Oprava kritéria: míří na *iniciaci* síly přes hranici bez doložené
   bezprostřední hrozby (Caroline `[VERIFY]`); přeshraniční operace obránce uvnitř
   běžící války je pokračování téže války, ne nová agrese (jus ad bellum se váže
   k válce, ne ke každé operaci); Ukrajina Kursk neanektovala. Zpřesnění platí
   i pro jednotlivce: ani tam neplatí „kdo první udeřil", nýbrž „na doložené
   tasení reagovat smíš" — Rusko žádné tasení nedoložilo, jeho kauza byla otevřeně
   preventivní.
5. **Against E — the mirror move, and the missing endpoint.** Zrcadlo („Ukrajina
   to taky může ukončit — přijetím reality"): ta dvě „ukončení" se liší druhem —
   stažení obnovuje status quo ante a právo, ústupek ratifikuje dobytí; loupež ≠
   odpor. Ale steelman tvrději: „skončit zítra" potřebuje definovaný koncový bod
   (stažení kam — předinvazní linie 24. 2. 2022? hranice 1991 včetně Krymu?),
   jinak je the exit asymmetry fuzzy. E dluží specifikaci — splatí ji Where it
   stands.
6. **Against E — Munich against Finland.** Meze mnichovské analogie: 1938 bez
   jaderných zbraní; Hitlerova sériová agrese doložená ex post vs. inference
   o Putinovi (esej 7/2021 jako doklad záměru `[VERIFY: pasáže]`); a Finsko 1940
   jako protimodel — postoupilo část území `[VERIFY: podíl]` a přežilo svobodné
   (po tvrdém boji, za cenu dekád finlandizace). Souboj analogií: co licencuje
   kterou → epistemologické vlákno (Threads).
7. **Against E — "too little" must survive the numbers.** Tvrzení „podpory je
   málo" musí projít čísly, ne dojmem: Kiel tracker — objemy, % HDP, srovnání
   `[VERIFY: as of 2026]`; munice/PVO gapy `[VERIFY]`. Pokud čísla ukážou
   opak, tvrzení v E oslabit a zapsat to.
8. **Against E — consistency, and an admission.** (a) Konzistence: the entry
   asymmetry odsuzuje i Irák 2003 — kousnout nahlas; kritérium, které šetří
   spojence, není kritérium. (b) Nezávislost ad bellum / in bello: verdikt
   o obraně nebílí případná ukrajinská porušení vedení války `[VERIFY: zprávy COI
   OSN, jen zmínka s ukazateli]`. (c) Motivovaná kognice přiznaná: autor je Čech
   s Mnichovem v krvi — anti-appeasementový prior předchází důkazům, které pro
   něj cituje (tentýž tah jako daylight asymmetry u smyslu).

- [ ] **Step 2: In-task verifikace empirických jader**

WebSearch/WebFetch: rozptyl odhadů ztrát (Mediazona/BBC jmenné počty vs. západní
odhady, atribuce), UNHCR kumulativ, KIIS/Gallup trend, časové rozpětí kurské
operace, Kiel tracker. Markery čísel vyřešit hned; textové (Charap & Radchenko,
Putinova esej, Finsko 1940, Caroline, COI) nechat na Task 7.

- [ ] **Step 3: Check bloků**

Run: `grep -c '^\*\*Against' war/ukraine-war-justification.md`
Expected: `9` (3 z Tasku 3 + 6 nových)

Run: `grep -n '^\*\*The reply from standing\|^\*\*The door cuts both ways' war/ukraine-war-justification.md`
Expected: 2 řádky.

- [ ] **Step 4: Schválení autorem** — výslovně projít bloky 2, 3 a 8 (palba na
  jeho vlastní pozici a osobní přiznání).

- [ ] **Step 5: Commit**

```bash
git add war/ukraine-war-justification.md
git commit -m "draft ukraine-war-justification: refutations against the author

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd"
```

### Task 5: Where it stands

**Files:**
- Modify: `war/ukraine-war-justification.md` (sekce `## Where it stands`)

**Interfaces:**
- Consumes: jména konjektur a asymetrií; bloky refutací z Tasků 3–4 (zejména the
  double edge, the door cuts both ways, the missing endpoint).
- Produces: verdikty tří vrstev s uvedenou konfidencí; specifikace koncového bodu
  (dluh z Tasku 4, blok 5); pět odrážek **What would change my mind** (na sekci
  odkazuje CONTRIBUTING konvence).

- [ ] **Step 1: Draft (v dialogu s autorem)**

Obsahová specifikace — čtyři tahy + co by změnilo názor:

1. **Invaze a prodlužování: neoprávněné, vysoká konfidence.** Obě asymetrie
   + selhání všech větví A (odkázat na Against A). Splatit dluh koncového bodu:
   minimální „konec" = zastavení palby + stažení aspoň za předinvazní linie
   z 24. 2. 2022 — to stačí k vyvrácení „řešení neexistuje"; spravedlnostní nárok
   = hranice 1991. Obě roviny držet oddělené (fakt vs. nárok); E unese obojí
   naráz.
2. **Obrana: oprávněná, bez vnější povinnosti ustoupit** — s výslovně přiznanou
   dvojsečností: zvolí-li dohodu Ukrajina, zavazuje to vnější moralisty v obou
   směrech (jestřáby i holubice). Poznamenat stav ukrajinské preference k datu
   `[VERIFY: aktuální KIIS/Gallup]` s `(as of 2026-MM)`.
3. **Podpora: oprávněná; „spíš povinná a nedostatečná" s nižší konfidencí,**
   podmíněná trvající ukrajinskou vůlí; jaderné riziko jako omezení *jak*, ne
   *zda* (odkaz na universalizaci vydírání z Against D odpovědí); výsledek
   konfrontace s čísly z Tasku 4 bloku 7 poctivě promítnout.
4. **Zapsaná pnutí:** the door cuts both ways → silný default, ne absolutno
   (stejná poctivost jako „default, not a law" u [[meaning-without-guarantee]]);
   motivovaná kognice z Tasku 4 bloku 8 zůstává viditelná.

**What would change my mind:**
- doložená trvalá ukrajinská preference ústupků přehlasovávaná zvenčí (standing
  se obrací proti E),
- ověřitelná změna ruského rejstříku dodržování dohod (např. reálně provedené
  monitorované stažení),
- kvantifikace jaderného rizika, v níž ocásek dominuje (ohýbá podporu k D),
- historiografický důkaz, že vymahatelná dohoda typu Istanbul byla reálně na
  stole,
- kolaps kritérií na konzistenčních testech (Irák, Gaza, Karabach).

- [ ] **Step 2: Check**

Run: `grep -n 'What would change my mind' war/ukraine-war-justification.md`
Expected: 1 výskyt; pod ním pět odrážek.

- [ ] **Step 3: Schválení autorem** — u tohoto tasku obzvlášť: je to jeho verdikt;
  anglické znění mu předložit celé.

- [ ] **Step 4: Commit**

```bash
git add war/ukraine-war-justification.md
git commit -m "draft ukraine-war-justification: where it stands

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd"
```

### Task 6: Threads to pull

**Files:**
- Modify: `war/ukraine-war-justification.md` (sekce `## Threads to pull`)

**Interfaces:**
- Consumes: jména asymetrií, bloky refutací (Munich against Finland; consistency).
- Produces: sedm nitek; odkaz `[[meaning-without-guarantee]]`, který kontroluje
  Task 8.

- [ ] **Step 1: Draft (v dialogu s autorem)**

Sedm odrážek:

1. **Etika jaderného vydírání.** Universalizace jaderné koerce (paklíč na všechno
   → proliferační pobídka; inverze poučení z Budapešti) — kandidát na vlastní
   poznámku ve `war/`.
2. **Epistemologie historických analogií.** Mnichov vs. Finsko 1940: kdy analogie
   licencuje závěr; problém referenční třídy.
3. **Jus in bello samostatně.** Vedení války oběma stranami (COI OSN); tady jen
   ukazatele, adjudikace by byla vlastní poznámka.
4. **Kolektivní agence.** Kdo vyslovuje „volbu Ukrajiny" — volby za martial law,
   mandát, reprezentace; the standing argument potřebuje teorii kolektivního
   subjektu.
5. **Rodina asymetrických argumentů.** Jednosměrné dveře
   ([[meaning-without-guarantee]]) a dvě asymetrie téhle poznámky — strukturální
   asymetrie jako tiebreaker při hodnotové nejistotě; kandidát na meta-poznámku.
6. **Co dluží signatáři ujištění.** Budapešť 1994: síla „assurances" vs.
   „guarantees"; co z toho plyne pro dnešní povinnost podpory.
7. **Konzistenční testy.** Vstupní/výstupní asymetrie na dalších konfliktech
   (Irák 2003 — kousnuto v refutacích; Gaza; Karabach 2023): drží kritéria tvar,
   nebo se ohýbají podle sympatií?

- [ ] **Step 2: Schválení autorem** — jako výše.

- [ ] **Step 3: Commit**

```bash
git add war/ukraine-war-justification.md
git commit -m "draft ukraine-war-justification: threads to pull

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd"
```

### Task 7: Konsolidační verifikace + Sources

**Files:**
- Modify: `war/ukraine-war-justification.md` (celý text — řešení zbylých
  `[VERIFY]` markerů; sekce `## Sources`; datum `sources checked`; kontrola
  stárnutí kotevního bloku)

**Interfaces:**
- Consumes: všechny zbylé `[VERIFY]` markery z Tasků 1–6 + pracovní seznam zdrojů
  z in-task verifikací.
- Produces: text bez markerů; Sources sekce po vzoru meaning-without-guarantee
  (skupiny po argumentech, anotace „co položka podpírá", opravy zaznamenané,
  **NOT VERIFIED** položky přiznané, `(as of …)` u perishables).

- [ ] **Step 1: Sestavit checklist markerů**

Run: `grep -n 'VERIFY' war/ukraine-war-justification.md`
Expected: seznam řádků — každý dostane řešení v krocích níže. K tomu přizvat
pracovní seznam zdrojů z in-task verifikací (Tasky 1, 3, 4) — i ty patří do
Sources, ověřené znovu jen pokud mezitím mohly zastarat.

- [ ] **Step 2: Právní blok**

WebFetch primárních dokumentů: Charta OSN čl. 2(4) a 51 (un.org — přesný text);
rezoluce ES-11/1 (2. 3. 2022) a ES-11/4 (12. 10. 2022) — formulace a poměry hlasů
(UN Digital Library / press release); ICJ Ukrajina v. Rusko: opatření 16. 3. 2022
a stav řízení k 2026 (icj-cij.org); ICJ Nicaragua v. USA 1986 (relevantní
paragrafy k intervenci na pozvání); ICC zatykače 17. 3. 2023 — přesný rozsah
(icc-cpi.int). Nedostupné → **NOT VERIFIED** s důvodem.

- [ ] **Step 3: Datový blok**

OHCHR (civilní oběti: trend Donbas 2018–2021, kumulativ po 2022);
Mediazona/BBC jmenné počty a západní odhady ztrát (rozptyl + čí odhad);
UNHCR (vysídlení); Kiel Institute tracker (objemy, % HDP); ISW/Economist (stav
fronty). Všechna čísla v poznámce: rozptyl, atribuce, `(as of …)`. Kotevní blok
z Tasku 1 zkontrolovat proti aktuálnímu stavu (mohl zastarat během psaní).

- [ ] **Step 4: Průzkumový blok**

KIIS a Gallup: trend ukrajinské preference jednání 2022→2026; výhrada znění
otázek do textu poznámky (rozdílná znění → rozdílná čísla).

- [ ] **Step 5: Diplomaticko-historický blok**

Charap & Radchenko (Foreign Affairs 2024): co Istanbul 2022 obsahoval a proč
padl; Budapešťské memorandum 1994 (text, síla závazků); Minsk I/II (závazky
a osud); rejstřík příměří 2026 (duben, květen). Mnichov 1938 (jedna solidní
reference); Moskevský mír 1940 (postoupený podíl finského území); Kosovo 1999
(fakta pro disanalogii, jen v rozsahu použitém v Against A); kurská operace
(časové rozpětí, žádná anexe).

- [ ] **Step 6: Filosoficko-textový blok**

Walzer, *Just and Unjust Wars*: domestic analogy, teorie agrese, appeasement —
přesné pasáže; Moellendorf: jus ex bello — dohledat přesná díla (článek 2008?
kniha?) a přesné teze; Caroline test (Webster 1841–42) — standardní formulace;
Mearsheimer 2014 (FA) — přesné výroky pro C; Kramer 2009 („myth") vs. Sarotte
2021 (*Not One Inch*) — co přesně tvrdí; Putin, „On the Historical Unity…"
(12. 7. 2021, kremlin.ru) — pasáže dokládající záměr; Girkin 2014 — přesné znění
a zdroj, jinak nepoužít; Orwell, „Pacifism and the War" (1942) — přesné znění,
jinak nepoužít. Pozor na známý fail-mode: plausibilní fabrikovaný citát —
přijmout jen text viděný v primárním zdroji.

- [ ] **Step 7: Zapsat Sources a vyřešit markery**

Sources po vzoru meaning-without-guarantee: skupiny (Law and UN record / Casualty
and displacement data / Support and polling / Diplomacy and history / Just war
theory and its critics), každá položka anotovaná tím, co podpírá; předmluva
sekce poctivě: co verifikace opravila (i „nic" je záznam); withdrawn/NOT VERIFIED
viditelné s důvodem; perishables s `(as of …)`. V textu: markery odstranit
(potvrzené) nebo přepsat na přiznané not-verified. Aktualizovat `sources
checked` na skutečné datum.

Run: `grep -c 'VERIFY' war/ukraine-war-justification.md`
Expected: `0`

- [ ] **Step 8: Schválení autorem** — zejména co verifikace změnila (opravy
  zapsané v Sources).

- [ ] **Step 9: Commit**

```bash
git add war/ukraine-war-justification.md
git commit -m "verify ukraine-war-justification sources; record corrections

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd"
```

### Task 8: Závěrečný průchod

**Files:**
- Modify: `war/ukraine-war-justification.md` (jen opravy z checků)

**Interfaces:**
- Consumes: hotová poznámka z Tasků 1–7; README/AGENTS řádky z Tasku 1.
- Produces: finální stav na `main`.

- [ ] **Step 1: Strukturní check**

Run: `grep -n '^## ' war/ukraine-war-justification.md`
Expected: šest sekcí v pořadí šablony (viz Task 1 Step 2).

Run: `grep -n '^\*Status: open · last touched' war/ukraine-war-justification.md`
Expected: 1 řádek, obě data skutečná (last touched = poslední den úprav prózy,
sources checked = den Tasku 7).

Run: `grep -c 'to be written' war/ukraine-war-justification.md`
Expected: `0`

- [ ] **Step 2: Check odkazů a složky**

Run: `ls meaning/meaning-without-guarantee.md`
Expected: existuje (cíl `[[…]]` odkazu).

Run: `grep -n 'war/' README.md AGENTS.md`
Expected: po jedné řádce složky v každém souboru (z Tasku 1).

Dále ručně: každý `[[…]]` v poznámce míří na existující soubor.

- [ ] **Step 3: Check stárnutí**

Run: `grep -n 'as of 2026' war/ukraine-war-justification.md`
Expected: každé rychle stárnoucí tvrzení (kotevní blok, čísla, průzkumy, stav
řízení, objemy podpory) má `(as of 2026-MM)`; žádné nedatované perishable. Ručně
projít čísla proti Sources.

- [ ] **Step 4: Čtení celku**

Přečíst poznámku vcelku: tón (thinking-in-progress); konzistence pevných jmen
(the entry asymmetry, the exit asymmetry, the standing argument, the domestic
analogy, jména A–E); verdikt se v refutacích zaslouží, nepředpokládá; steelman A
není slaměný panák; pnutí E (double edge, door cuts both ways, Kursk, mirror,
Munich/Finland, motivovaná kognice) viditelná; jus in bello neadjudikováno.

- [ ] **Step 5: Finální schválení autorem**

Poslat autorovi celou poznámku; zapracovat poslední úpravy.

- [ ] **Step 6: Commit (jen pokud Step 1–5 něco změnily)**

```bash
git add war/ukraine-war-justification.md
git commit -m "revise ukraine-war-justification: final pass

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01QUpkiWsUA66TN5crGUvFKd"
```
