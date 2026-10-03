# Online Anonymity Note — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Napsat, ověřit a commitnout první poznámku nové složky `society/` — `online-anonymity.md` — podle specu `docs/superpowers/specs/2026-10-03-online-anonymity-design.md`.

**Architecture:** Jedna Markdown poznámka ve tvaru `TEMPLATE.md`. Páteř je etická (má být anonymita dostupná, když z ní těží i svinstvo), technická otázka vystupuje jako ověřená kotva uvnitř refutací, politická otázka („kdo drží klíč") je závěrečná část. Autorova vstupní intuice — anonymita je mírně zlo, protože skrývá nelegální činnost, umožňuje dezinformace a botí farmy — je v textu přiznaná a testovaná; spec předem ohlašuje, že dvě ze tří nohou nejspíš zeslábnou z „umožňuje" na „zlevňuje". Drafty vznikají po sekcích v dialogu s autorem; empirická jádra se ověřují už při draftování své sekce, konsolidace citací a atribucí je v Tasku 9, adversariální refutační průchod v Tasku 10, zásahy do README/AGENTS až v Tasku 11 (jedna dávka s verdiktem).

**Tech Stack:** Markdown, git (přímo na `main` — konvence repa), WebSearch/WebFetch pro verifikaci zdrojů, `curl` + odstranění tagů pro surové stránky k ověřování citací.

## Global Constraints

- Poznámka je **anglicky**; pracovní dialog s autorem **česky**; **žádné formulářové dotazníky** — autor reaguje na hotový text (drafty ukazovat anglicky, shrnovat česky).
- Cílový soubor: `society/online-anonymity.md`. H1: `# Does online anonymity do more harm than good — and is less of it even on the table?`
- Pořadí sekcí přesně podle `TEMPLATE.md`; statusová řádka `*Status: open · last touched YYYY-MM-DD · sources checked YYYY-MM-DD*` (data = skutečné dny činností; `sources checked` finalizuje Task 9).
- Mimo poznámku se mění **jen** `README.md`, `README.cs.md`, `README.pl.md` a `AGENTS.md`, a to výhradně v Tasku 11. Žádné změny `TEMPLATE.md`, `CONTRIBUTING.md` ani jiných poznámek. `docs/backlog.md` se aktualizuje v Tasku 12.
- **Never cite from memory:** každé empirické či textové tvrzení se buď ověří v tasku, kde vzniká (in-task verifikace), nebo nese inline marker `[VERIFY]` do Tasku 9. Co verifikací neprojde: opravit, vypustit, nebo označit `NOT VERIFIED` s důvodem. Co verifikace změnila, zaznamenat v Sources — prohry zůstávají viditelné.
- **Doslovnost nestačí; citát se ověřuje ve svém odstavci.** U každé citace přečíst, co stojí před ní a po ní, a ověřit, že odstavec nemíří jinam než použití citátu. Tahle konvence vznikla ze dvou citací v `religion/science-as-religion.md`, které byly doslovné, ověřené proti surové stránce a přesto zavádějící.
- Perishable tvrzení — **zejména legislativa** (ověřování věku, návrhy na skenování obsahu, platformní politiky) a jakákoli čísla o podílu provozu — nesou `(as of YYYY-MM)`.
- Odstavce prózy **nezalamovat** (odstavec = jeden řádek). Zalamuje se jen to, co má řádek jako jednotku významu: odrážky, tabulky, kódové bloky, těla commit messages (~72 znaků).
- Cíl rozsahu: spec říká 350–450 řádků kalibrovaných na starý zalamovaný styl; v nezalamovaném stylu tomu odpovídá **~4000–5500 slov** (`wc -w`). Řídit se slovy, ne řádky.
- **Pevná jména napříč tasky** (používat beze změny, jinak si tasky přestanou rozumět):
  - Konjektury: **A — Net harm** (autorova vstupní pozice), **B — Shield of the weak**, **C — Not a dial**, **D — The middle rung**, **E — Who holds the key**.
  - Tři stupně anonymity: **pseudonymity** (platforma identitu zná, publikum ne), **platform-blind anonymity** (identitu nezná ani platforma, síť ano), **network-blind anonymity** (ani jedno — Tor, mixnety).
  - **the three legs** — tři důvody autorovy vstupní pozice (illegality, disinformation, bot farms).
  - **the cheaper-not-possible shift** — posun tvrzení z „anonymita to umožňuje" na „anonymita to zlevňuje".
  - **the visibility asymmetry** — škody mají jména a čísla, užitek je z principu nespočitatelný.
  - **the keyholder question** — politická závěrečná část: každý návrh na zrušení anonymity je návrhem na přidělení moci.
  - **the Korean experiment** — jihokorejský systém ověřování identity (~2007–2012).
- Tón: thinking-in-progress, první osoba autora (Petr). **A se testuje, nehájí** — ale dostane svou *nejsilnější* verzi, postavenou na nejlépe dokumentovaných škodách, ne na botích farmách (konvence „refute the organized defence"). Refutace A nesmí být tvrdší než refutace B–E; žádná konjektura si nenadržuje.
- Poznámka **neobsahuje** žádný návod, jak se anonymizovat, a žádný osobní dovětek o tom, zda má autor používat VPN. Účel „munice do diskuzí" je kontext práce, ne obsah textu.
- Commity: krátké, present-tense, podle vzorů v jednotlivých taskách. Trailery `Co-Authored-By` + `Claude-Session` podle session, ve které task reálně běží.
- Před každým commitem `git fetch` a kontrola, že `main` není za `origin/main` — na repu běží paralelní session. Soubory přidávat **jmenovitě**, nikdy `git add .`.

---

### Task 1: Scaffold + The question

**Files:**
- Create: `society/online-anonymity.md`

**Interfaces:**
- Consumes: `TEMPLATE.md` (tvar), spec sekce „Titul a The question".
- Produces: soubor se všemi šesti `##` nadpisy, hotovou sekcí The question, H1 a statusovou řádkou; zavedená jména **pseudonymity / platform-blind anonymity / network-blind anonymity** a **the three legs**, na která navazují Tasky 2–6. Složka `society/` vzniká tímto souborem (git složky netrackuje, žádný `.gitkeep`).

- [x] **Step 1: Založit soubor se skeletem**

Vytvořit `society/online-anonymity.md` s tímto obsahem:

```markdown
# Does online anonymity do more harm than good — and is less of it even on the table?

*Status: open · last touched 2026-10-03 · sources checked 2026-10-03*

## The question

## Conjectures

## Refutations & tensions

## Where it stands

## Threads to pull

## Sources
```

- [x] **Step 2: Check skeletu**

```bash
cd /Users/krato/IdeaProjects/github.com/kratocz/philosophical-conjectures
command grep -c '^## ' society/online-anonymity.md
command grep -n '^# \|^\*Status' society/online-anonymity.md
```

Expected: `6` pro počet `##` nadpisů; H1 a statusová řádka na řádcích 1 a 3.

- [x] **Step 3: Draft The question (anglicky, v dialogu s autorem)**

Sekce musí udělat čtyři věci, v tomto pořadí:

1. Položit otázku a přiznat, odkud přišla (autor ji přinesl po videu o VPN; konkrétní video nejmenovat).
2. **Rozplést tři stupně** — `pseudonymity`, `platform-blind anonymity`, `network-blind anonymity` — a explicitně říct, že většina sporů o anonymitu je spor, v němž každá strana mluví o jiném stupni. Tahle pasáž je nosná pro celou poznámku: bez ní nelze formulovat D ani vyhodnotit A.
3. **Odlišit, co anonymita není:** soukromí (to je o obsahu, ne o autorství), šifrování (chrání obsah, ne identitu), beztrestnost (anonymita zvyšuje cenu dohledání, neruší právo).
4. **Přiznat autorovu vstupní intuici včetně the three legs** — anonymita je mírně zlo, protože skrývá nelegální činnost ubližující nevinným, umožňuje dezinformace a umožňuje botí farmy — a říct, že se v této poznámce testuje.

Žádné empirické číslo v této sekci; všechna čísla patří do refutací, kde se ověřují.

- [x] **Step 4: Schválení autorem**

Ukázat hotovou sekci anglicky, shrnout česky dvěma až třemi větami, co sekce tvrdí a co z toho plyne pro zbytek. Bez souhlasu nepokračovat. Jde o obsahové rozhodnutí: **žádný formulář.**

- [x] **Step 5: Commit**

```bash
cd /Users/krato/IdeaProjects/github.com/kratocz/philosophical-conjectures
git fetch --quiet && git status --short
git add society/online-anonymity.md
git commit -m "add online-anonymity conjecture"
```

---

### Task 2: Conjectures A–E

**Files:**
- Modify: `society/online-anonymity.md` (sekce `## Conjectures`)

**Interfaces:**
- Consumes: jména tří stupňů a **the three legs** z Tasku 1; spec sekce „Konjektury (5)".
- Produces: pět pojmenovaných konjektur **A — Net harm**, **B — Shield of the weak**, **C — Not a dial**, **D — The middle rung**, **E — Who holds the key**, na které adresně míří Tasky 3–6.

- [x] **Step 1: Draft pěti konjektur (v dialogu s autorem)**

Každá konjektura je odrážka: **tučné jméno** + teze bez hedgingu. Obsah podle specu:

- **A — Net harm** — celková bilance je negativní: anonymita zlevňuje trestnou činnost ubližující nevinným, zaplavuje veřejný prostor manipulací, umožňuje botí sítě; svět s menší anonymitou by byl lepší. Označit jako autorovu vstupní pozici a napsat ji v **nejsilnější** formě — opřít ji o nejlépe dokumentované škody, ne o botí farmy.
- **B — Shield of the weak** — anonymita je nutná podmínka toho, aby mohli mluvit lidé, kteří mají co ztratit (whistlebloweři, disidenti, oběti domácího násilí, novinářské zdroje, lidé pronásledovaní za identitu); náklady jsou cenou za existenci opozice vůči moci.
- **C — Not a dial** — otázka „má být dostupná" je špatně položená: buď technická možnost `network-blind anonymity` existuje a nelze ji odebrat jen zlým aktérům, nebo neexistuje a nemají ji ani ohrožení. Mezistupeň není, je jen otázka, komu dáme klíč.
- **D — The middle rung** — většinu užitku dodá `pseudonymity`, většinu škod až `network-blind anonymity`; odpověď není krajní poloha, ale posun o jeden stupeň.
- **E — Who holds the key** — skutečná otázka není kolik anonymity, ale kdo ji smí prolomit, za jakých podmínek a pod jakou kontrolou; každý návrh na zrušení anonymity je návrh na přidělení moci.

- [x] **Step 2: Check značení**

```bash
command grep -n '^- \*\*[A-E] — ' society/online-anonymity.md
```

Expected: přesně pět řádků, jména v pořadí A, B, C, D, E a doslova shodná s Global Constraints.

- [x] **Step 3: Schválení autorem** — jako Task 1 Step 4. Zvlášť se zeptat, zda A zní dost silně: pokud autor řekne „takhle bych to neřekl", je A formulovaná slabě a musí se přepsat, protože se bude napadat.

- [x] **Step 4: Commit**

```bash
git fetch --quiet && git status --short
git add society/online-anonymity.md
git commit -m "draft online-anonymity: conjectures"
```

---

### Task 3: Refutations — rozklad A (the three legs)

**Files:**
- Modify: `society/online-anonymity.md` (sekce `## Refutations & tensions`, bloky 1–3)

**Interfaces:**
- Consumes: A a **the three legs** z Tasků 1–2.
- Produces: **the cheaper-not-possible shift** jako pojmenovaný výsledek, na který odkazují Task 7 (Where it stands) a Task 10.

Tohle je nejdůležitější task celé poznámky: tady se testuje autorova pozice. Text musí být tvrdý k tvrzení a fér k autorovi.

- [x] **Step 1: Draft bloků 1–3 (v dialogu s autorem)**

Jeden blok na každou nohu, každý ve tvaru *nejsilnější verze tvrzení → co proti němu stojí → co z tvrzení zbývá*:

1. **Illegality** — nejpevnější noha. Nejsilnější verze: existují kategorie škody, kde je `network-blind anonymity` provozní podmínkou trhu (materiál zneužívání dětí, trhy s drogami, ransomware). Tlak: nakolik je anonymita *nutná* podmínka? Velké případy padaly na operačních chybách a běžné vyšetřovací práci, ne na prolomení protokolu — což ukazuje, že anonymita zvedá cenu vyšetřování, ale neuzavírá ho. Zapsat, co z nohy zbývá.
2. **Disinformation** — tlak: nejúčinnější dezinformace jdou pod skutečnými jmény a přes státní média, protože jméno dodává autoritu, kterou anonym nemá. Očekávaný výsledek: **the cheaper-not-possible shift**.
3. **Bot farms** — tlak: botí sítě běží na kupovaných, kradených a často plně verifikovaných účtech; verifikace je pro ně vstupní náklad, ne překážka. Očekávaný výsledek: tentýž posun, možná silnější než u dezinformací.

Na konci bloku 3 jednou větou pojmenovat, co se právě stalo s autorovou pozicí — nehodnotit, jen zaznamenat.

- [x] **Step 2: In-task verifikace empirických jader**

Ověřit v tomto tasku (ne odkládat), protože na nich stojí celý rozklad:

- jak padly velké případy darknetových trhů — operační chyba vs. prolomení protokolu;
- jak fungují botí a trollí farmy: podíl verifikovaných, kupovaných a kradených účtů, dokumentace k personám pod reálně vypadajícími jmény;
- koncentrace šíření dezinformací a role účtů pod reálnými jmény a státních médií.

Co se nepodaří ověřit, nese inline `[VERIFY]` do Tasku 9. Žádné číslo bez primárního zdroje; u čísel o podílu provozu ověřit i metodologii, protože tahle čísla jsou notoricky sporná.

- [x] **Step 3: Check**

```bash
command grep -c '\[VERIFY\]' society/online-anonymity.md
wc -w society/online-anonymity.md
```

Expected: počet markerů vypsaný a zapsaný do checklistu pro Task 9; slov po tomto tasku řádově 1200–2000.

- [x] **Step 4: Schválení autorem** — výslovně projít blok 1 a pak bloky 2–3: tady se mu hýbe pozice. Říct česky, co obstálo a co se posunulo, a nechat ho reagovat, než se jde dál.

- [x] **Step 5: Commit**

```bash
git fetch --quiet && git status --short
git add society/online-anonymity.md
git commit -m "draft online-anonymity: refutations (the three legs)"
```

---

### Task 4: Refutations — technická kotva (C)

**Files:**
- Modify: `society/online-anonymity.md` (sekce `## Refutations & tensions`, bloky 4–5)

**Interfaces:**
- Consumes: C a tři stupně z Tasků 1–2.
- Produces: vyřízené téma VPN a pojmenovaný seznam reálných mezistupňů, na který staví D v Tasku 5 a E v Tasku 6.

- [x] **Step 1: Draft bloků 4–5 (v dialogu s autorem)**

4. **Co VPN vlastně dělá.** Tohle je místo, kde se vyřizuje podnět, z něhož téma vzniklo: VPN neodstraňuje sledovatelnost, jen přesouvá důvěru od poskytovatele připojení k provozovateli VPN — pro většinu hrozeb nulový posun. Zmínit rozpor mezi marketingem a threat modelem a to, co znamenají tvrzení typu „no logs" (a které byly nezávisle auditované). Bez jmenování konkrétních poskytovatelů.
5. **Proti C: mezistupně existují a fungují asymetricky.** Ověřování věku, KYC u platforem, povinné uchovávání provozních dat — zvednou cenu pro náhodného trolla, ne pro odhodlaného aktéra. Z toho plyne přesnější formulace než „není to kohoutek": je to kohoutek, který účinkuje právě na ty, kterých se nejvíc nebojíme. Tuhle větu zapsat, je nosná pro Where it stands.

- [x] **Step 2: In-task verifikace**

- co VPN technicky mění na threat modelu; stav nezávislých auditů „no logs" tvrzení;
- aktuální legislativa k ověřování věku a návrhům na skenování obsahu — **perishable, označit `(as of YYYY-MM)`**;
- odhady podílu nelegálního provozu v anonymizačních sítích: ověřit metodologii, nebo tvrzení vypustit.

- [x] **Step 3: Check**

```bash
command grep -n '(as of ' society/online-anonymity.md
command grep -c '\[VERIFY\]' society/online-anonymity.md
```

Expected: každé legislativní tvrzení nese `(as of YYYY-MM)`; počet markerů aktualizovaný v checklistu.

- [x] **Step 4: Schválení autorem** — jako výše.

- [x] **Step 5: Commit**

```bash
git fetch --quiet && git status --short
git add society/online-anonymity.md
git commit -m "draft online-anonymity: refutations (what VPN does, the rungs)"
```

---

### Task 5: Refutations — B, D a the visibility asymmetry

**Files:**
- Modify: `society/online-anonymity.md` (sekce `## Refutations & tensions`, bloky 6–8)

**Interfaces:**
- Consumes: B, D, tři stupně, seznam mezistupňů z Tasku 4.
- Produces: **the visibility asymmetry** jako pojmenovaný argument, na který odkazuje Where it stands.

- [x] **Step 1: Draft bloků 6–8 (v dialogu s autorem)**

6. **Proti B: nutná, nebo jen užitečná podmínka?** Whistleblowing často probíhá přes identifikované kanály s právní ochranou a nejznámější případy šly přes novináře, který zdroj znal. Pokud je anonymita jen užitečná, váha B proti A klesá — a to je výsledek proti autorovi i proti B, takže se zapisuje tak jak je.
7. **Proti D: jediný bod selhání.** `pseudonymity` znamená, že identitu drží provozovatel — a ten se dá hacknout, koupit, podrobit nebo prostě vyměnit majitele. Pro disidenta je „provozovatel mě zná" totéž jako žádná anonymita. D tedy funguje proti trollingu, ne proti tomu, co chrání B. Doložit, pokud se najde, dokumentovanou škodou z platformních politik reálných jmen na skupinách, které jméno ohrožuje.
8. **the visibility asymmetry.** Škody z anonymity mají jména, oběti a čísla; užitek je z principu nespočitatelný, protože projev, který se uskutečnil jen proto, že autor nebyl dohledatelný, nikdo nenahlásí ani neidentifikuje. To systematicky táhne intuici k A u každého, kdo o tom přemýšlí poctivě — včetně autora — a je to argument proti důvěře ve vlastní pocit z té bilance, ne argument pro B.

- [x] **Step 2: In-task verifikace**

- právní ochrana whistleblowerů (EU směrnice, americká úprava) vs. anonymita jako cesta; jak u známých případů běžel kanál ke zdroji;
- dokumentovaná škoda z politik reálných jmen;
- měření efektu na chování po roce 2013 (chilling effect). **V paměti mám jednu práci o provozu na Wikipedii — citaci neověřenou; dohledat primární zdroj, nebo tvrzení vypustit.**

- [x] **Step 3: Check** — jako Task 4 Step 3; navíc `wc -w` (řádově 2800–4000 slov po tomto tasku).

- [x] **Step 4: Schválení autorem** — upozornit, že blok 6 oslabuje i protistranu jeho pozice, a blok 8 vysvětluje, proč jeho vstupní pocit mohl vzniknout, aniž by byl nutně špatný.

- [x] **Step 5: Commit**

```bash
git fetch --quiet && git status --short
git add society/online-anonymity.md
git commit -m "draft online-anonymity: refutations (shield, middle rung, visibility)"
```

---

### Task 6: Refutations — the keyholder question (E)

**Files:**
- Modify: `society/online-anonymity.md` (sekce `## Refutations & tensions`, blok 9)

**Interfaces:**
- Consumes: E, mezistupně z Tasku 4.
- Produces: závěrečná politická část refutací; **the keyholder question** jako pojmenovaná teze pro Where it stands.

- [x] **Step 1: Draft bloku 9 (v dialogu s autorem)**

Blok nese tvrzení, že „zrušit anonymitu" v praxi nikdy neznamená zrušit ji, nýbrž dát někomu moc ji prolomit — takže reálná volba není mezi anonymitou a jejím opakem, ale mezi držiteli klíče a kontrolou nad nimi. Zmínit paralelu s verdiktem `religion/religion-risk.md` (text je munice, struktura je zbraň, **moc je spoušť**) a odkázat na ni relativním odkazem.

Pak protitlak proti E: přesouvá otázku, ale neodpovídá na ni — i dobře kontrolovaný klíč mění chování lidí už svou existencí, takže bilanci nelze uzavřít poukazem na kvalitu kontroly.

- [x] **Step 2: Check odkazu**

```bash
command grep -n 'religion-risk' society/online-anonymity.md
test -f religion/religion-risk.md && echo "cil existuje"
```

Expected: relativní odkaz `../religion/religion-risk.md`, cíl existuje.

- [x] **Step 3: Schválení autorem** — jako výše.

- [x] **Step 4: Commit**

```bash
git fetch --quiet && git status --short
git add society/online-anonymity.md
git commit -m "draft online-anonymity: refutations (who holds the key)"
```

---

### Task 7: Where it stands

**Files:**
- Modify: `society/online-anonymity.md` (sekce `## Where it stands`)

**Interfaces:**
- Consumes: výsledky Tasků 3–6, zejména **the cheaper-not-possible shift**, **the visibility asymmetry**, **the keyholder question**.
- Produces: verdikt, z něhož Task 11 destiluje jednu větu do `README.md`.

Tohle je autorův hlas. Draftovat návrh, ale formulace je jeho.

- [x] **Step 1: Projít proceduru ze specu, v tomto pořadí**

1. U každé ze **the three legs** zapsat, jestli obstála, posunula se, nebo padla.
2. Rozhodnout páteřní otázku jedním z předem stanovených výsledků: **(i)** A obstojí i po oslabení dvou nohou; **(ii)** A se udrží jen pro část spektra (nejspíš `network-blind`, ne `pseudonymity`) — pak je verdiktem C nebo D, ne A; **(iii)** A padá a zbývá spor B vs. E.
3. Explicitně napsat, co by změnilo názor — u každého výsledku jiná falzifikace.
4. **Nepřeklopit se do opačné jistoty.** Pokud rešerše oslabí A, výsledkem není „anonymita je dobro", ale přesnější popis toho, kde bilance leží a kde evidence končí. Tvar „tušení držené jako vkus, ne poznatek" z `reality/determinism.md` je i tady legitimní.
5. U každého argumentu říct, **jak snadno padne** — vyhodnocení pevnosti je obsah poznámky, ne servis autorovi.

- [x] **Step 2: Check**

```bash
command grep -n 'would change my mind\|what would change' society/online-anonymity.md
```

Expected: sekce obsahuje explicitní falzifikaci.

- [x] **Step 3: Schválení autorem** — jeho verdikt; bez souhlasu nepokračovat.

- [x] **Step 4: Commit**

```bash
git fetch --quiet && git status --short
git add society/online-anonymity.md
git commit -m "draft online-anonymity: where it stands"
```

---

### Task 8: Threads to pull

**Files:**
- Modify: `society/online-anonymity.md` (sekce `## Threads to pull`)

**Interfaces:**
- Consumes: otevřené otázky, které vypadly z Tasků 3–7.
- Produces: kandidáty na budoucí poznámky v `society/`, které Task 12 zapíše do `docs/backlog.md`.

- [x] **Step 1: Draft (v dialogu s autorem)**

Odrážky; kandidáti, které už spec zná: svoboda slova a její hranice jako samostatná poznámka; dohled a sledování; moderace obsahu; ochrana osobních údajů jako právní úprava; dopředný odkaz na `mind/` nebo `meaning/`, pokud nějaký vznikl. Co se v Tasku 9 nepodařilo ověřit a je to zajímavé, patří sem jako otevřená otázka, ne do refutací jako tvrzení.

- [x] **Step 2: Schválení autorem** — jako výše.

- [x] **Step 3: Commit**

```bash
git fetch --quiet && git status --short
git add society/online-anonymity.md
git commit -m "draft online-anonymity: threads to pull"
```

---

### Task 9: Konsolidační verifikace + Sources

**Files:**
- Modify: `society/online-anonymity.md` (sekce `## Sources`, statusová řádka, inline opravy)
- Create: podadresář `anonymity-sources/` ve scratchpad adresáři té session, která task spouští (cestu najde ve svém system promptu) - surové stránky k ověřování citátů, mimo repo

**Interfaces:**
- Consumes: všechny markery `[VERIFY]` z Tasků 3–6.
- Produces: sekci Sources seskupenou po argumentech, nulový počet nevyřešených markerů, finální `sources checked` datum; surové stránky na disku pro Task 10.

- [x] **Step 1: Sestavit checklist markerů**

```bash
command grep -n '\[VERIFY\]' society/online-anonymity.md
```

Každý marker dostane řádek v checklistu: tvrzení, co se má ověřit, výsledek.

- [x] **Step 2: Prioritní blok — the Korean experiment**

Ověřit jihokorejský systém ověřování identity: co přesně zákon vyžadoval, kdy platil, proč byl zrušen, a **co měřily studie o jeho efektu na toxicitu komentářů.** V paměti mám, že efekt byl blízký nule nebo nekonzistentní, ale **citaci nemám ověřenou.** Bez dohledaného primárního zdroje tvrzení do poznámky nepatří — buď se najde, nebo jde do Threads to pull jako otevřená otázka. Pokud se najde, je to nejpevnější empirický podklad celé poznámky.

- [x] **Step 3: Stáhnout surové stránky pro každou citaci**

```bash
S="$SCRATCHPAD/anonymity-sources"   # $SCRATCHPAD = scratchpad adresar teto session
mkdir -p "$S"
curl -sL '<URL>' | python3 -c 'import sys,re,html; t=sys.stdin.read(); t=re.sub(r"(?s)<(script|style).*?</\1>","",t); t=re.sub(r"(?s)<[^>]+>"," ",t); print(html.unescape(re.sub(r"[ \t]+"," ",t)))' > "$S/<nazev>.txt"
```

Nepoužívat sumarizační nástroj. Konvence repa: u nosného znění se stahuje surový text a čte se vlastními očima.

- [x] **Step 4: Ověřit každou citaci ve svém odstavci**

U každé citace: najít ji ve stáhnutém textu, pak **přečíst odstavec před a po** a ověřit, že nemíří jinam než použití citátu. Doslovnost nestačí — dvě citace v `religion/science-as-religion.md` byly doslovné, ověřené a přesto zavádějící, protože byly odříznuté dvě věty před místem, kde argument otáčí.

- [x] **Step 5: Zapsat Sources a vyřešit markery**

Sekce Sources: **seskupit po argumentech**, u každé položky napsat, co doopravdy podporuje — ne jen název. Předmluva sekce zaznamená:

- zdroje, které šly proti vlastnímu draftu nebo odmítly použití, které se jim chtělo dát;
- tvrzení stažená nebo ponechaná neověřená, s důvodem;
- co verifikace změnila na formulacích.

Pak `command grep -c '\[VERIFY\]'` musí vrátit `0`.

- [x] **Step 6: Aktualizovat statusovou řádku**

`sources checked` na skutečné datum tohoto tasku; `last touched` taktéž.

- [x] **Step 7: Schválení autorem** — zejména co verifikace změnila: opravy, stažená tvrzení, `NOT VERIFIED`.

- [x] **Step 8: Commit**

```bash
git fetch --quiet && git status --short
git add society/online-anonymity.md
git commit -m "verify online-anonymity sources"
```

---

### Task 10: Adversariální refutační průchod

**Files:**
- Modify: `society/online-anonymity.md` (sekce `## Sources` — zápis průchodu; inline opravy podle přijatých nálezů)

**Interfaces:**
- Consumes: hotovou poznámku z Tasků 1–9; surové stránky ze scratchpadu z Tasku 9 Step 3.
- Produces: zápis průchodu v Sources (co rozbil, co se změnilo, co se nepřijalo a proč) — povinná konvence repa.

- [x] **Step 1: Vypravit reviewera ve svěžím kontextu**

Dispatchovat subagenta s instrukcí **„vyvrať tuhle poznámku"**, ne „zkontroluj ji". Dát mu:

- cestu k poznámce a kontrakt, který má splnit (tvar podle `TEMPLATE.md`, konvence z `AGENTS.md`);
- cestu ke stáhnutým surovým stránkám, aby mohl citace ověřit znak po znaku;
- **ne** úvahy, které k závěrům vedly — reviewer, kterému se dají hotové závěry, vrátí jejich potvrzení.

Žádat výstup v pevném tvaru: `tvrzení — proč je vadné — důkaz (soubor:řádek nebo citace)`.

- [x] **Step 2: Rozhodnout o každém nálezu**

Přijaté nálezy opravit v textu. **Nepřijaté nálezy se nezahazují** — zapisují se do Sources s důvodem, proč se nepřijaly. Pokud druhý průchod převrátí první, zaznamenat i to.

- [x] **Step 3: Zapsat průchod do Sources**

Co průchod rozbil, co se kvůli němu změnilo, a které nálezy nebyly přijaty a proč.

- [x] **Step 4: Schválení autorem** — ukázat, co průchod našel a co se s tím stalo.

- [x] **Step 5: Commit**

```bash
git fetch --quiet && git status --short
git add society/online-anonymity.md
git commit -m "revise online-anonymity: refutation pass"
```

---

### Task 11: Složka `society/` + README ×3 + AGENTS + verdikt

**Files:**
- Modify: `README.md`, `README.cs.md`, `README.pl.md`, `AGENTS.md`

**Interfaces:**
- Consumes: Where it stands z Tasku 7 (po případných revizích z Tasku 10).
- Produces: verdikt v jedné větě ve třech jazycích; `society/` zapsaná ve Structure.

- [x] **Step 1: Destilovat verdikt (v dialogu s autorem)**

Jedna věta destilovaná z Where it stands. **Pravidla:** žádné nové tvrzení, nic ostřejšího než poznámka sama, nic perishable (žádná čísla, žádné „as of").

- [x] **Step 2: `README.md`**

Přidat sekci složky `society/` na správné místo abecedního pořadí (mezi `religion/` a `war/`) a pod ni odrážku s odkazem na poznámku a verdiktem v kurzivě. Formát okopírovat z existujících řádků.

- [x] **Step 3: `AGENTS.md`**

Přidat řádek do Structure (abecedně, mezi `religion/` a `war/`): `society/` — „How people arrange living together: speech, surveillance, anonymity, and the trade-offs a shared public space forces."

- [x] **Step 4: `README.cs.md` a `README.pl.md`**

Zrcadlit změnu z `README.md`: nová sekce složky, odrážka, přeložený verdikt. **Aktualizovat datum stavu překladu v hlavičce** na datum poslední změny `README.md`.

```bash
git log -1 --format=%cs -- README.md
```

- [x] **Step 5: Check zrcadlení**

```bash
for f in README.md README.cs.md README.pl.md; do echo "$f: $(command grep -c 'online-anonymity' $f)"; done
command grep -n 'k 20\|z 20' README.cs.md README.pl.md | head -4
```

Expected: každý README obsahuje odkaz právě jednou; obě hlavičky nesou stejné datum jako výstup `git log` výše.

- [x] **Step 6: Schválení autorem** — verdikt je jeho, ve všech třech jazycích.

- [x] **Step 7: Commit**

```bash
git fetch --quiet && git status --short
git add README.md && git add README.cs.md && git add README.pl.md && git add AGENTS.md
git commit -m "readme: land online-anonymity verdict and the society folder"
```

---

### Task 12: Závěrečný průchod

**Files:**
- Modify: `society/online-anonymity.md` (jen pokud check něco najde), `docs/backlog.md`

**Interfaces:**
- Consumes: hotovou poznámku a README.
- Produces: zkontrolovaná poznámka, aktualizovaný backlog, pushnuto.

- [x] **Step 1: Strukturní check**

```bash
cd /Users/krato/IdeaProjects/github.com/kratocz/philosophical-conjectures
command grep -c '^## ' society/online-anonymity.md
command grep -n '^# \|^\*Status' society/online-anonymity.md
command grep -c '\[VERIFY\]' society/online-anonymity.md
wc -w society/online-anonymity.md
```

Expected: `6` nadpisů v pořadí podle `TEMPLATE.md`; statusová řádka s oběma daty; `0` markerů; 4000–5500 slov.

- [x] **Step 2: Check odkazů a zalamování**

```bash
command grep -o '](\.\./[^)]*)' society/online-anonymity.md | tr -d '](' | while read p; do test -f "$p" && echo "OK $p" || echo "CHYBÍ $p"; done
awk 'length > 400 {c++} END {print "dlouhych radku (= nezalamovana proza):", c+0}' society/online-anonymity.md
```

Expected: žádné `CHYBÍ`; dlouhé řádky existují (próza se nezalamuje).

- [x] **Step 3: Check stárnutí**

Projít všechna perishable tvrzení (legislativa, čísla, platformní politiky) a ověřit, že nesou `(as of YYYY-MM)`.

- [x] **Step 4: Aktualizovat `docs/backlog.md`**

Přesunout anonymitu z „Rozpracováno" do „Hotovo" se shrnutím: soubor, páteř, co se stalo s autorovou vstupní intuicí (která noha obstála, které se posunuly), odkaz na spec a plán. Přidat nové kandidáty z Threads to pull do „Kandidáti z vláken".

- [x] **Step 5: Commit a push**

```bash
git fetch --quiet && git status --short
git add docs/backlog.md
# plus society/online-anonymity.md, pokud check něco opravil
git commit -m "docs(backlog): online anonymity done"
git push origin main
```

- [x] **Step 6: Nabídnout autorovi další téma** — z `docs/backlog.md`: poznámka k „nothing remains" (rozbor hotový), rozparkování `nuclear-blackmail`, nebo nový kandidát „LLM jako svědek".
