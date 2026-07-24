# Design: poznámka `war/ukraine-war-justification.md`

- **Datum:** 2026-07-24
- **Status:** návrh schválený v brainstormingu, čeká na revizi specu
- **Jazyk poznámky:** angličtina (konvence repa); tento spec je pracovní dokument, proto česky
- **Architektura:** „dvě asymetrie jako páteř" — konjektury A–E jako soupeřící verdikty o oprávněnosti prodlužování války; tři vrstvy z fronty témat (invaze / obrana / podpora) jako důsledky asymetrií, ne jako osnova

## Cíl a kontext

První poznámka do nové složky `war/`. Téma z fronty („oprávněnost současné války na
Ukrajině") autor v brainstormingu zaostřil: zajímavá otázka není „smí se Ukrajina bránit?"
— to je špatně adresovaný dotaz na oběť — ale **„je Putinovo odmítání válku ukončit
podložené něčím, co obstojí?"**

Autorovy formulace z dialogu (kotvy pro draft, význam zachovat přesně):

> „Beru jako základ, že Ukrajina je napadená, protože jsou ruští vojáci na Ukrajině a ne
> naopak. Kdykoliv může válka skončit stažením ruských vojáků, takže řešení to má, ale
> Putin ho odmítá — a zajímavá je otázka oprávněnosti jeho odmítání (prodlužování války),
> zda je něčím podložené."

> „Kdyby na světě každá země dělala preventivní útoky, protože si něco myslí, tak by svět
> byla jedna válka vedle druhé. Nelze stavět fyzický útok jen na podezření — jak u lidí,
> tak u států. Nemohu jít po ulici, někoho zmlátit a pak být osvobozený obhajobou, že jsem
> měl pocit, že mi ten člověk chtěl ublížit."

Z toho tři pilíře autorovy pozice (nosný tah poznámky):

1. **Vstupní asymetrie.** Kdo fyzicky zaútočil první přes hranici, je ověřitelný fakt, ne
   názor. Podezření útok nelicencuje: universalizační test (svět preventivních útoků =
   permanentní válka) + analogie s jednotlivcem. Autor tím nezávisle došel k Walzerově
   *domestic analogy* a ke standardu Caroline testu / čl. 51 Charty — poznámka konvergenci
   přizná.
2. **Výstupní asymetrie.** Válka má kdykoli dostupné jednostranné řešení — ruské stažení;
   obrácené „řešení" (ukrajinská kapitulace) neukončuje válku, ale stát. Břemeno
   zdůvodnění každého dalšího dne nese ten, kdo drží klíč od východu.
3. **Standing argument.** Cenu svobody smí vážit jen ten, kdo ji platí; vnější tlak na
   ústupky oceňuje cizí svobodu. Historická opora: Mnichov 1938 jako česká epistemická
   kotva („o nás bez nás") — s poctivě přiznanými mezemi analogie.

Autorovy náklony (z dialogu): ruský případ steelmanovat a vyvrátit; obrana bez vnější
povinnosti ustoupit; podpora oprávněná a „spíš jí je málo". Konjektury smí být silnější
než výsledný verdikt — popperovský tvar repa.

Autor v dialogu zdůraznil: **toto téma bude hlavně chtít dobře zdrojovat.** Zdrojovací
disciplína je proto samostatná část designu (níže), přísnější než u předchozích poznámek.

## Umístění a rám

- **Soubor:** `war/ukraine-war-justification.md` (neutrální, dohledatelné jméno — vzor
  `bible-veracity`: neutrální název, odvážný obsah). Nová složka `war/`.
- **Titulek (H1):** *Who could end the war in Ukraine tomorrow — and what justifies not
  doing it?*
- **README + AGENTS.md:** přibude řádka složky, návrh: *"**war/** — The ethics of war,
  tested on the one running now: who started it, who keeps it going, and what bystanders
  owe."* (Finální znění při draftu.)
- **Statusová řádka:** dle `TEMPLATE.md`, obě data reálná (prose vs. verifikace).
- **Křížové odkazy:** [[meaning-without-guarantee]] — příbuznost strukturálních asymetrií
  (jednosměrné dveře ↔ kapitulace jako jednosměrné dveře); jinak střídmě, dopředné zmínky
  ve vláknech.
- **Strategie stárnutí:** nejrychleji stárnoucí poznámka repa. Filosofická páteř psaná
  tak, aby platila i po posunu fronty; empirie soustředěná do kotevní podsekce „The war
  as of 2026-07" **uvnitř sekce The question** (fakta, na nichž poznámka stojí, na
  jednom datovaném místě); každé rychle stárnoucí tvrzení inline `(as of YYYY-MM)`;
  `sources checked` slouží jako datum expirace.

## Kontext k datu návrhu (2026-07, ověřit znovu při draftu)

Válka běží; krátká příměří (duben a květen 2026) nevydržela; americká mediace v březnu
uvázla, diplomacie se oživuje (Umerov–USA v Miami; výzva Koalice ochotných z Paříže
13. 7. 2026 k okamžitému příměří); Rusko pomalu postupuje (~31 km² za 30 dní k 30. 6.
2026 dle Economistu) a jeho ztráty od března 2026 převyšují nábor (ISW/Critical Threats,
Russia Matters). Otázka „smí Ukrajina odmítnout špatný mír" je tedy živá přesně teď.

## Architektura poznámky

### The question

Otázku ukotví dva ověřitelné fakty (vstupní a výstupní asymetrie) a jeden metodický tah
(domestic analogy + universalizace). Plné znění: vzhledem k oběma asymetriím — je
Putinovo odmítání válku ukončit podložené něčím, co obstojí? A co z odpovědi plyne pro
meze ukrajinské obrany a povinnosti třetích stran?

Švy držené viditelně (půl práce poznámky, vzor meaning-without-guarantee):

- legálnost ≠ morálnost (Charta a rezoluce vs. teorie spravedlivé války),
- zahájení (2014/2022) ≠ pokračování (2026) ≠ vedení války (jus in bello — vědomě mimo
  záběr, jen s ukazateli),
- fakt ≠ standard (asymetrie jsou fakta; filosofická práce je ukázat, proč jsou
  rozhodující).

Motivace: proč to řeší Čech (Mnichov, malé národy vedle velkých) a proč teď (tlak na
Kyjev v běžící diplomacii, červenec 2026).

### Conjectures

Pět soupeřících verdiktů, každý vysloven odvážně (hedging až v refutacích):

- **A — Ruský případ (steelman).** Pokračování je oprávněné: expanze NATO jako existenční
  hrozba (Bukurešť 2008), ochrana rusky mluvících a Donbasu, kosovský precedent +
  „pozvání" uznaných republik; specificky pro 2026: anektované oblasti ústavně ruské,
  západním zárukám nelze věřit, bez vyřešení „root causes" je válka jen odložená a horší
  — pokračovat je cesta k trvalému míru. Formulovat tak silně, aby vyvrácení něco vážilo.
- **B — Oprávněný není nikdo (pacifistický verdikt).** Válka jako metoda je
  neobhajitelná; nemorální je každý den pokračování všemi stranami; jediný morální
  požadavek je okamžité příměří; západní zbraně přikládají pod kotel (proxy-war čtení
  jako morální bratranec).
- **C — Realistická disoluce.** Kategorie oprávněnosti na mezinárodní anarchii nesedí:
  státy sledují bezpečnost, morální slovník je dekorace; reálné otázky jsou jen
  prudenciální. Nejostřejší forma: Mearsheimerovo „je to vina Západu".
- **D — Obrana ano, ale mez se blíží (nejsilnější rival autorovy pozice).** Invaze
  neoprávněná, obrana zprvu oprávněná — ale proporcionalita se přepočítává průběžně (jus
  ex bello): padlí, demografie, destrukce, jaderné riziko a globální dopady mohou převážit,
  co ještě lze bojem získat; od toho bodu je vyjednávání povinnost a povinnost třetích
  stran se překlápí ze zbrojení na tlak k dohodě. Empirický exponát: „lepší mír byl
  k mání dřív" (Istanbul 2022).
- **E — Autorova pozice.** Agresi fixuje vstupní asymetrie (první fyzický přeshraniční
  útok; podezření nelicencuje — universalizace + domestic analogy). Prodlužování je
  každodenní ruská volba (výstupní asymetrie) a nic z A neobstojí — neoprávněné právně
  i morálně. Obrana oprávněná bez vnější povinnosti ustoupit (standing argument). Podpora
  oprávněná, spíš povinná a fakticky nedostatečná — Mnichov 1938 jako epistemická kotva,
  Budapešťské memorandum jako závazkový háček.

### Refutations & tensions

**Proti A:**

- Chronologie zabíjí bezpečnostní narativ: Krym (únor 2014) předchází každému údajnému
  spouštěči z 2022; Ukrajina neměla MAP. Historiografii „slibu o nerozšiřování" vzít
  poctivě (Kramer „mýtus" 2009 vs. Sarotte *Not One Inch* 2021 — ověřit, co prameny
  unesou).
- Ochranné zdůvodnění selhává empiricky: civilní oběti na Donbasu před invazí klesaly, po
  invazi vzrostly o řády — „ochrana", která násobí škodu, na niž se odvolává (OHCHR,
  ověřit čísla). „Genocida" bez důkazů (stav řízení u ICJ ověřit).
- Právní lešení: Nikaragujský precedent (pozvání loutkových entit nelegalizuje
  intervenci), ES-11/1 (141:5), ES-11/4 (143:5); Kosovo je disanalogie — a kdyby bylo
  Kosovo špatně, nelicencuje to nic (dvě křivdy).
- Specificky k pokračování: požadavky rostly s válečným štěstím (důkaz, že cíle nejsou
  obranné); anexe oblastí, které Rusko nekontroluje; „nedůvěra v záruky" je symetrická —
  ruský vlastní rejstřík (Budapešť, Minsk) ji diskvalifikuje jako důvod pokračovat.

**Proti B:** „přestaňte střílet" znamená pro každou stranu něco jiného — agresorovo
zastavení končí válku, obráncovo končí obránce; příměří-hned zmrazuje dobytí → odměňuje
agresi → zvyšuje pravděpodobnost dalších válek; poctivá cena pacifismu: práva existující
jen z milosti agresorů. (Orwell 1942 — použít jen s ověřeným zněním.)

**Proti C:** sklouznutí z deskripce do normy; performativní rozpor (i Rusko zdůvodňuje);
„buffer state" myšlení upírá Ukrajině agenci — přesně to, co standing argument odhaluje;
Mearsheimerovy konkrétní výroky ověřit z primárních textů. Zaznamenat, co z C přežívá:
opatrnost vůči eskalační pýše je reálná constraint, kterou E vstřebává.

**Proti D — nejdřív plná síla** (padlí v řádech statisíců napříč stranami, demografie,
destrukce, jaderný ocásek rizika, Istanbul 2022 — vše ověřit s rozptylem odhadů), **pak
odpovědi E a kde se E poctivě ohýbá:**

- Standing argument je **dvojsečný**: pokud ukrajinská většina začne preferovat dohodu
  (trendy KIIS/Gallup 2022→2026 ověřit), E musí dohodu podpořit. E ≠ „bojovat věčně";
  E = „volba patří platícím". Zbytkový spor s D se zužuje na otázku: smí třetí strany
  podmiňovat podporu tlakem na jednání?
- **Rekurze jednosměrných dveří:** kapitulace je kvazi-nevratná (okupovaná země a lidé
  východ nemají), obrana volbu drží — ale **dveře řežou obousměrně: mrtví taky nemají
  opce.** Reálné pnutí uvnitř E, zapsat jako pnutí, ne odbýt.
- Istanbul 2022: jádrem krachu nedotažené bezpečnostní záruky (ověřit u
  Charap/Radchenko, FA 2024); ruský rejstřík dodržování dělá z „lepšího míru tehdy"
  nefalzifikovatelnou hypotézu.
- Jaderné riziko: absorbovat jako omezení *jak* eskalovat podporu, ne *zda* se bránit —
  jinak se jaderné vydírání stává universálním paklíčem (universalizace podruhé; inverze
  poučení z Budapešti: proliferační pobídka).

**Proti E specificky:**

- **Kursk (srpen 2024 – jaro 2025):** kritérium „čí vojáci kde" je moc hrubé. Oprava:
  kritérium míří na *iniciaci* síly přes hranici bez doložené bezprostřední hrozby;
  přeshraniční operace obránce uvnitř běžící války je pokračování téže války, ne nová
  agrese (jus ad bellum se váže k válce, ne ke každé operaci); Ukrajina Kursk
  neanektovala.
- **Zrcadlový tah** („Ukrajina to taky může ukončit — přijetím reality"): ta dvě
  „ukončení" se liší druhem — stažení obnovuje status quo ante a právo, ústupek
  ratifikuje dobytí; loupež ≠ odpor. Ale steelman tvrději: **„skončit zítra" potřebuje
  definovaný koncový bod** (stažení kam — předinvazní linie z 24. 2. 2022? hranice 1991
  včetně Krymu?), jinak je výstupní asymetrie fuzzy. E specifikuje ve Where it stands.
- **Zpřesnění vstupního kritéria:** ani u jednotlivců neplatí „kdo první udeřil", nýbrž
  „útok nesmí stát na pouhém podezření; bezprostřednost musí být doložená" (kdo tasí,
  na toho reagovat smíš — Rusko žádné tasení nedoložilo, jeho kauza byla otevřeně
  preventivní; Caroline test).
- **Meze Mnichova:** 1938 bez jaderných zbraní; Hitlerova sériová agrese doložená ex
  post vs. inference o Putinovi (esej 7/2021 jako doklad záměru — ověřit); **Finsko 1940
  jako protimodel** — postoupilo část území a přežilo svobodné (po tvrdém boji, za cenu
  dekád finlandizace; podíl území ověřit). Souboj analogií Mnichov vs. Finsko → kdy
  analogie licencuje závěr (epistemologické vlákno).
- **„Podpory je málo" musí přežít čísla,** ne dojem: Kiel tracker, % HDP, munice/PVO
  (as of 2026, ověřit).
- **Konzistence:** vstupní kritérium odsuzuje i Irák 2003 — kousnout nahlas; nezávislost
  ad bellum / in bello (verdikt o obraně nebílí případná ukrajinská porušení vedení
  války — zmínit s ukazateli, neadjudikovat).
- **Motivovaná kognice přiznaná:** autor je Čech s Mnichovem v krvi — anti-appeasementový
  prior předchází důkazům, které pro něj cituje (stejný tah jako daylight asymmetry
  u smyslu).

### Where it stands

Provizorní verdikt (draft se k němu musí dopracovat, ne ho předpokládat):

1. **Invaze a prodlužování: neoprávněné, vysoká konfidence.** Obě asymetrie + selhání
   všech větví A. Součástí je definice koncového bodu: minimální „konec" = zastavení
   palby + stažení aspoň za předinvazní linie z 24. 2. 2022 (vyvrací „řešení
   neexistuje"); spravedlnostní nárok = hranice 1991. E unese obojí naráz, drží-li ty
   dvě roviny oddělené.
2. **Obrana: oprávněná, bez vnější povinnosti ustoupit** — s přiznanou dvojsečností
   standing argumentu: zvolí-li dohodu Ukrajina, zavazuje to vnější moralisty v obou
   směrech (jestřáby i holubice).
3. **Podpora: oprávněná; „spíš povinná a nedostatečná" s nižší konfidencí,** podmíněná
   trvající ukrajinskou vůlí; jaderné riziko jako omezení *jak*, ne *zda*.
4. **Zapsaná pnutí:** dveře řežou obousměrně (mrtví opce nemají) → argument zakládá
   silný default, ne absolutno — stejná poctivost jako „default, not a law" u smyslu.

**What would change my mind:**

- doložená trvalá ukrajinská preference ústupků přehlasovávaná zvenčí (standing se
  obrací proti E),
- ověřitelná změna ruského rejstříku dodržování dohod (např. reálně provedené
  monitorované stažení),
- kvantifikace jaderného rizika, v níž ocásek dominuje (ohýbá podporu k D),
- historiografický důkaz, že vymahatelná dohoda typu Istanbul byla reálně na stole,
- kolaps kritérií na konzistenčních testech (Irák, Gaza, Karabach).

### Threads to pull

- Etika jaderného vydírání (universalizace jaderné koerce; proliferační poučení
  z Budapešti) — kandidát na vlastní poznámku.
- Epistemologie historických analogií (Mnichov vs. Finsko; problém referenční třídy).
- Jus in bello samostatně (zprávy COI OSN; obě strany).
- Kolektivní agence: kdo vyslovuje „volbu Ukrajiny" (volby za martial law, mandát).
- Rodina asymetrických argumentů napříč repem ([[meaning-without-guarantee]]) —
  strukturální asymetrie jako tiebreaker při hodnotové nejistotě; kandidát na
  meta-poznámku.
- Co dluží signatáři bezpečnostních ujištění (Budapešť 1994).
- Konzistenční testy kritérií na dalších konfliktech.

### Sources — verifikační plán

Laťka meaning-without-guarantee, zpřísněná (téma je empirické a rychle stárne): **psát
s inline flagy, ověřovat dvoustupňově, škody zapsat.** Nikdy necitovat z paměti; co se
neověří, označit **NOT VERIFIED**; co verifikace vyvrátí, nechat viditelné s důvodem.

Dvoustupňová verifikace: (1) fakta se ověřují už při draftování příslušné sekce
(WebSearch/WebFetch na primární dokumenty), (2) závěrečný konsolidační průchod před
commitem poznámky. I „nic jsem nenašel" je záznam.

| Blok | Co se z něj ověřuje |
|---|---|
| Charta OSN čl. 2(4), 51 | přesný text obou článků |
| Rezoluce VS OSN ES-11/1 (2. 3. 2022), ES-11/4 (12. 10. 2022) | poměry hlasů (141:5, 143:5) a formulace |
| ICJ Ukrajina v. Rusko (Úmluva o genocidě): opatření 16. 3. 2022 + navazující rozsudky | co přesně soud řekl a jaký je stav k 2026 |
| ICJ Nicaragua v. USA (1986) | precedent: intervence „na pozvání" nestátních entit nelegalizuje použití síly |
| Kosovo 1999 (jedna solidní reference) | fakta pro disanalogii (doložené zločiny, vyčerpaná cesta OSN) — jen v rozsahu, v jakém se v refutacích použije |
| ICC: zatykače 17. 3. 2023 (Putin, Lvova-Belova) | přesný rozsah obvinění |
| OHCHR: civilní oběti (Donbas 2018–2021 trend; kumulativně po 2022) | čísla s rozptylem, `(as of …)` |
| Mediazona/BBC (jmenné počty), západní odhady ztrát, UNHCR | řády a rozptyl, atribuce odhadů |
| Kiel Institute Ukraine Support Tracker | objemy podpory, % HDP — test tvrzení „je jí málo" |
| ISW/Critical Threats; Economist | stav fronty k 2026-07; postup Ruska |
| KIIS, Gallup 2022→2026 | trend ukrajinské preference jednání; výhrada znění otázek |
| Charap & Radchenko, Foreign Affairs 2024 | co se v Istanbulu 2022 skutečně nabízelo a proč to padlo |
| Budapešťské memorandum 1994; Minsk I/II | texty závazků; ruský rejstřík dodržování |
| Walzer, *Just and Unjust Wars* | domestic analogy; teorie agrese; appeasement |
| Moellendorf (jus ex bello), příp. Rodin | standard pro D; přesná díla dohledat |
| Caroline test (Webster 1841–42) | standardní formulace anticipační sebeobrany |
| Mearsheimer 2014 (FA) + pozdější výroky | steelman C; citovat jen ověřené |
| Kramer 2009 vs. Sarotte 2021 | historiografie „slibu o nerozšiřování" |
| Putin, „On the Historical Unity…" (12. 7. 2021) | doklad záměru; přesné pasáže |
| Girkin — výrok o „spuštění války" (2014) | přesné znění a zdroj, jinak nepoužít |
| Orwell, „Pacifism and the War" (1942) | přesné znění, jinak nepoužít |
| Mnichov 1938 (jedna solidní historie); Moskevský mír 1940 | fakta obou analogií; podíl postoupeného finského území |

### Proces psaní

1. Spec (tento dokument) → commit → revize autorem.
2. `superpowers:writing-plans` → implementační plán do `docs/superpowers/plans/` → commit.
3. Draft po sekcích v pořadí šablony (The question → Conjectures → Refutations → Where it
   stands → Threads → Sources); každou sekci schvaluje autor — konjektury i verdikt jsou
   autorovy, role asistenta: struktura, formulace, protiargumenty, verifikace.
4. Verifikace dvoustupňově (viz výše); nálezy do Sources včetně oprav.
5. README + AGENTS.md: řádka složky `war/`. Statusová řádka poznámky s reálnými daty.
6. Commit poznámky: `add ukraine-war-justification conjecture` (krátce, přítomný čas).

## Mimo rozsah

- Adjudikace jus in bello (jen zmínka s ukazateli).
- Vojenské predikce a policy advocacy nad rámec otázky oprávněnosti.
- Jiné konflikty nad rámec konzistenčních zmínek (Irák, Gaza, Karabach).
- Další poznámky do `war/` (jaderné vydírání, epistemologie analogií) — jen jako vlákna.

## Kritéria hotovosti

- `war/ukraine-war-justification.md` existuje, drží pořadí sekcí `TEMPLATE.md` a tón
  repa (thinking-in-progress, anglicky).
- Každé jmenovité či číselné tvrzení je ověřené proti dostupnému zdroji, nebo nese
  **NOT VERIFIED**; rychle stárnoucí tvrzení mají `(as of YYYY-MM)`.
- Sources poctivě zaznamenávají, co verifikace opravila (i „nic nenašla").
- Tři pilíře (vstupní asymetrie, výstupní asymetrie, standing argument) uvedeny jako
  autorovy; pnutí E viditelná: dvojsečnost standingu, obousměrné dveře, Kursk, zrcadlový
  tah, meze Mnichova, přiznaná motivovaná kognice.
- README a AGENTS.md mají řádku `war/`.
- Autor schválil každou sekci; commity zprávou podle konvence.
