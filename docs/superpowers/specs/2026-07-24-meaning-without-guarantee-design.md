# Design: poznámka `meaning/meaning-without-guarantee.md`

- **Datum:** 2026-07-24
- **Status:** návrh schválený v brainstormingu, čeká na revizi specu
- **Jazyk poznámky:** angličtina (konvence repa); tento spec je pracovní dokument, proto česky
- **Architektura:** „vrstvený argument" — dvě otázky držené odděleně, konjektury jako stanice oblouku

## Cíl a kontext

První poznámka do dosud prázdné složky `meaning/`. Páteřní otázka je prakticko-existenciální:
**„Jak žít bez záruky smyslu?"** — přesně to, co pro `meaning/` slibuje README („how to live
without a guarantee that any of it means anything").

Autorův výchozí náklon (z dialogu, stane se konjekturou E a sekcí Where it stands):
kombinace **deflace požadavku záruky** („požadavek je zmatený"), **Wolfové angažmá
v objektivně hodnotném** a **camusovského postoje**. Autor nevybral čistý subjektivismus —
chce aspoň trochu objektivity a nemyslí si, že se otázka rozpustí beze zbytku.

Nosným původním příspěvkem autora je **argument jednosměrných dveří** (viz Where it stands).

## Umístění a rám

- **Soubor:** `meaning/meaning-without-guarantee.md` (kebab-case, jako ostatní poznámky).
- **Titulek (H1):** *How should I live if nothing guarantees that any of it matters?*
- **Statusová řádka:** `*Status: open · last touched YYYY-MM-DD · sources checked YYYY-MM-DD*`
  — obě data podle dne, kdy se ta která práce reálně stane (prose vs. verifikace).
- **Struktura sekcí:** přesně podle `TEMPLATE.md` — The question → Conjectures →
  Refutations & tensions → Where it stands → Threads to pull → Sources.
- **Křížové odkazy:** `[[immortality-desirability]]` (kategorické touhy = palivo angažmá;
  pokud je nesmrtelnost vyčerpá, umře nejdřív smysl), `[[bible-veracity]]` a
  `[[religion-risk]]` u konjektury A (náboženská záruka je v repu zkoumána jinde),
  dopředná zmínka na budoucí poznámky v `mind/` (vazba smyslu na vědomí).
- **README/AGENTS se nemění** — popis složky `meaning/` už tuhle poznámku pokrývá.

## Architektura poznámky

### The question

Dvě otázky, které se běžně slévají, držené od sebe (vzor: personal-identity):

1. **Diagnostická:** Co přesně by „záruka smyslu" byla? Co chybí, když chybí — a je
   požadavek na ni vůbec koherentní?
2. **Praktická:** Co z odpovědi na (1) plyne pro to, jak žít?

Motivace v textu: cluster `continuity/` tiše předpokládá, že na přetrvání záleží; tahle
poznámka se ptá, co dělá přetrvávání hodným chtění. Camusova úvodní věta o sebevraždě jako
jediném vážném filosofickém problému otevírá praktickou otázku v nejostřejší podobě.

### Conjectures

- **A — Záruku obnovit.** Bůh / kosmický účel / řád dějin. Uvést férově a v nejsilnější
  verzi (bez transcendentní kotvy hodnoty visí ve vzduchu). Odkaz na `religion/`.
- **B — Smysl se tvoří, ne nachází.** Subjektivismus (Sartre; Taylorova subjektivistická
  pointa). Záruka nikdy nebyla potřeba; stesk po ní je nostalgie.
- **C — Revolta.** Camus: absurdno = konfrontace lidského požadavku s mlčením světa;
  neřešit leapem ani rezignací, nést — „žít bez odvolání". Revolta, svoboda, vášeň.
- **D — Angažmá v objektivně hodnotném.** Wolf: smysl vzniká, kde se subjektivní zaujetí
  potká s objektivní hodnotností („subjective attraction meets objective attractiveness").
- **E — Deflace-a-rekonstrukce (autorova pozice).** Požadavek vnější záruky je zmatený;
  po rozpuštění otázky zbývá D nesené postojem C. Není to čistá deflace — něco přežívá.

### Refutations & tensions

Palba na každou konjekturu, plus vnitřní pnutí autorovy kombinace:

- **Proti A:** eutyfrovský regres (proč *Boží* účel uděluje smysl? čí účel dává smysl
  Božímu životu?); Baierova cena záruky — smysl udělený zvenčí dělá z člověka nástroj
  cizího projektu, což není smysl, ale degradace.
- **Proti B:** smysluplnost fiatem — Taylorův Sisyfos s injektovanou touhou valit kámen.
  Pokud smysl dá cokoli chtěné, slovo „smysluplný" nekoná žádnou práci.
- **Proti C:** Nagelova ironie jako rivalský postoj k revoltě; Nagelova výtka Camusovi
  (romantická sebelítost — **ověřit doslovné znění**, necitovat z paměti). Pnutí E×C:
  rozpouští-li se požadavek, proti čemu se bouřit? Revolta potřebuje, aby absurdno
  přežilo diagnózu.
- **Proti D (nejsilnější vlastní refutace poznámky):** nestabilita mezi B a A — rozředí-li
  se „objektivní hodnotnost" na intersubjektivní shodu, D kolabuje do B; vezme-li se
  vážně, potřebuje kotvu, kterou slibovalo A. Wolf sama teorii objektivní hodnoty odmítá
  dodat (ověřit, kde to říká). Regres „a proč na TOM záleží?" se u D vrací.
- **Proti E:** deflace jako anestezie — prohlásit otázku za zmatenou je podezřele
  pohodlné pro toho, kdo se chce přestat trápit (motivovaný krok, přiznat po vzoru
  personal-identity).
- **Proti argumentu jednosměrných dveří** (viz níže): (a) *pašování hodnoty* — odkud se
  bere hodnota svobody volby, je-li vše bezsmyslné? (odpověď: minimální strukturální
  hodnota post-deflace — přiznat, ne zamlčet); (b) *epikurejská námitka* — mrtvému nic
  nechybí, není subjekt deprivace (kontr: Nagelova deprivační teorie z eseje „Death");
  (c) *ekvivokace* — argument dává důvod pokračovat; je důvod-pokračovat totéž co smysl?
  Rozdíl držet viditelný; (d) v stavech nevratného utrpení se option value může obrátit —
  převaha života je pak podmíněná, ne strukturální. Téma sebevraždy držet filosoficky
  a abstraktně, jako Camus.
- **Empirický protipříklad:** Tolstoj (*Zpověď*) — život plný Wolfové statků (dílo,
  sláva, rodina), který se přesto zhroutil. Dvě čtení: D něco přehlíží, nebo šlo
  o patologii, ne o vhled. Nechat obě.
- **Asymetrie denního světla:** diagnóza „zmatený požadavek" přesvědčuje v poledne
  a selhává ve tři ráno. Přiznat jako data o autorovi (stejný tah jako „I still *feel*
  like a further-fact believer" v personal-identity).

### Where it stands

Provizorní pozice autora:

1. **Diagnosticky:** požadavek vnější záruky je v obvyklé podobě zmatený — smysl nemůže
   vzniknout udělením zvenčí (Baier/Euthyfro). Ale deflace nerozpouští všechno: přežívá
   reálná otázka *co za to stojí* (D) a reálné reziduum — mezera mezi hloubkou požadavku
   a každou dostupnou odpovědí. Mezi camusovským vzdorem a nagelovskou ironií nerozhodnuto
   — to je vědomé oslabení konjektury E (která postoj C tvrdí odvážně) poté, co refutace
   C×Nagel proběhne; konjektura smí být silnější než verdikt, to je popperovský tvar repa.
2. **Argument jednosměrných dveří (autorův nosný tah).** Autorova formulace (překlad do
   angličtiny při draftu, význam zachovat přesně): smrt i život jsou obě bez smyslu, ale
   život je cennější, protože přechod mezi stavy je jednosměrný — dokud žijeme, držíme
   volbu, zda žít dál; mrtvý nedrží nic. Vzdát se života znamená vzdát se i samotné
   svobody volit, a zahazovat nástroj volby nedává smysl. Z čehož ironicky plyne, že
   život má navrch právě o hodnotu té svobody: **převaha života se nezakládá na jeho
   smyslu, ale na option value při jednosměrných dveřích.** Je to přímá odpověď na
   Camusovu úvodní otázku sebevraždy.
3. **Prakticky:** angažmá v tom, co by stálo za péči i bez kosmického potvrzení, nesené
   s přiznáním, že justifikační regres není uzavřen.

**What would change my mind:**

- Obhajitelná teorie objektivní hodnoty bez teismu → D se stabilizuje, půlka refutací padá.
- Argument, že zmatená je sama deflace — kosmická otázka je koherentní a nezodpovězená →
  absurdno se vrací v plné síle a A dostává novou šanci.
- Doklad, že option value argumentu jednosměrných dveří se hroutí (např. nevratné
  utrpení) systematičtěji, než poznámka připouští → převaha života přestává být
  strukturální.
- Doklad, že „asymetrie tří hodin ráno" je artefakt nálady, ne data o pojmu.

### Threads to pull

- Metzova teorie fundamentality (*Meaning in Life*, 2013) — třetí cesta mezi B a D?
- Rozlišení meaning *in* life vs. meaning *of* life — historie a nosnost.
- Nozickův regres smyslu a kde smí legitimně skončit.
- Frankl jako praktický protipól (smysl hledaný v odpovědnosti) — držet koncepčně,
  bez empirických tvrzení logoterapie.
- Vazba na budoucí `mind/`: může něco záležet bez vědomí? Smysl a fenomenalita.
- Zpět na `[[immortality-desirability]]`: pokud nekonečný život vyčerpá kategorické
  touhy, umírá nejdřív smysl — obě poznámky se vzájemně omezují.

### Sources — verifikační plán

Laťka personal-identity: **psát první, ověřovat druhé, škody zapsat.** Nikdy necitovat
z paměti; co se neověří z dostupného textu, označit **NOT VERIFIED** místo tichého
vypuštění; co verifikace vyvrátí, nechat v poznámce viditelné i s důvodem.

| Zdroj | Co se z něj ověřuje |
|---|---|
| Camus, *The Myth of Sisyphus* (1942, angl. O'Brien 1955) | úvodní věta o sebevraždě (přesné znění); definice absurdna jako konfrontace/rozvodu; „living without appeal"; revolta–svoboda–vášeň; „one must imagine Sisyphus happy" |
| Nagel, „The Absurd", *Journal of Philosophy* 68 (1971) | ironie jako doporučený postoj; výrok o Camusovi (romantism/sebelítost — přesné znění); tah „if nothing matters, that doesn't matter either" |
| Nagel, „Death" (1970; *Mortal Questions* 1979) | deprivační teorie zla smrti — opora proti epikurejské námitce |
| Wolf, *Meaning in Life and Why It Matters* (Princeton UP 2010; též „Happiness and Meaning" 1997) | formule subjective attraction / objective attractiveness; Fitting Fulfillment; její přiznané odmítnutí dodat teorii objektivní hodnoty; její příklady (ověřit, které jsou skutečně její) |
| Taylor, „The Meaning of Life", in *Good and Evil* (1970) | Sisyfos s injektovanou touhou; subjektivistická pointa |
| Baier, „The Meaning of Life" (1957) | účel udělený zvenčí degraduje na nástroj; přesná formulace |
| Tolstoj, *Zpověď* (1882) | „zastavení života" navzdory statkům; klíčový citát v ověřeném překladu |
| Epikúros, *List Menoikeovi* | „smrt se nás netýká" — přesné znění ve standardním překladu |
| Metz, „The Meaning of Life", SEP | mapa terénu; sekundární opora atribucí |

Empirických rychle stárnoucích tvrzení se poznámka záměrně zdrží (je koncepční);
kdyby nějaké přibylo, dostane `(as of YYYY-MM)`.

## Proces psaní

1. **Drafty po sekcích** v pořadí šablony; každou sekci schvaluje autor, než se jede dál
   — konjektury i refutace musí být autorovy (README: „written by me"). Role asistenta:
   struktura, formulace, protiargumenty k úvaze, verifikace.
2. **Verifikační průchod až po celém draftu** (WebSearch/WebFetch na primární texty a SEP);
   nálezy se zapíší do Sources včetně toho, co verifikace opravila.
3. **Statusová řádka** dostane skutečná data obou činností.
4. **Commit:** `add meaning-without-guarantee conjecture: how to live unguaranteed`
   (krátký, přítomný čas, podle konvence repa).

## Mimo rozsah

- Téma **oprávněnosti současné války na Ukrajině** — další ve frontě, samostatný
  brainstorming (bude silně empirické, pravděpodobně nová složka; zaznamenáno v paměti).
- Změny README/AGENTS/CONTRIBUTING, další poznámky do `mind/`.

## Kritéria hotovosti

- `meaning/meaning-without-guarantee.md` existuje, drží pořadí sekcí `TEMPLATE.md`
  a tón repa (thinking-in-progress, anglicky).
- Každé jmenovité tvrzení o filosofovi je ověřené proti dostupnému textu, nebo nese
  **NOT VERIFIED**.
- Sources poctivě zaznamenávají, co verifikace opravila (i „nic nenašla" je záznam).
- Argument jednosměrných dveří je uveden jako autorův, s refutacemi (a)–(d) proti sobě.
- Křížové odkazy na `[[immortality-desirability]]`, `religion/` poznámky a dopřednou
  zmínku o `mind/` jsou na místě.
- Autor schválil každou sekci; commit zprávou podle konvence.
