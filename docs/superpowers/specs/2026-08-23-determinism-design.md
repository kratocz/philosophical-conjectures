# Design: poznámka `reality/determinism.md`

- **Datum:** 2026-08-23
- **Status:** návrh schválený v brainstormingu, čeká na revizi specu
- **Jazyk poznámky:** angličtina (konvence repa); tento spec je pracovní dokument, proto česky
- **Architektura:** epistemická páteř (rozhodnutelnost otázky) s fyzikální kotvou a dovětkem „no a co"

## Cíl a kontext

Otázku „je vesmír deterministický?" přinesl autorovi kamarád. Autor chce, aby ji repo zpracovalo a **objektivně posoudilo** — jeho slova: „pravda je pro mě to nejdůležitější."

Autorova vstupní intuice: **kvůli kvantové fyzice vesmír deterministický není.** Tato intuice je v poznámce otevřeně přiznaná a je jedním z hlavních testovaných tvrzení. Očekávaný (a autorovi předem ohlášený) tlak literatury nevede k „determinismus platí", ale k „kvantová mechanika to nerozhodla ani jedním směrem" — existují deterministické formulace QM (Bohmova, Everettova) empiricky ekvivalentní té „kostkové". Poznámka poctivě zaznamená, zda vstupní intuice přežila, a pokud ne, co ji zlomilo.

Téma jde mimo frontu (nuclear-blackmail zůstává zaparkovaný na své branchi, tato práce se ho nedotýká).

## Páteř

V brainstormingu zvažovány tři možné páteře: *fyzikální* (co o tom fyzika říká), *epistemická* (mohli bychom to vůbec kdy vědět) a *praktická* („no a co" — změnilo by se něco, kdybychom odpověď znali). Schváleno: **epistemická jako páteř, fyzikální jako ověřená kotva uvnitř refutací, praktická jako závěrečný dovětek.** Čistě fyzikální poznámka by byla rešerše, ne konjektura; čistě praktická je stará debata o svobodné vůli. Epistemická má vlastní tvrzení, které se dá držet a napadnout, a přirozeně si obě zbylé zatáhne dovnitř. (Písmena A–E níže značí už jen konjektury, ne páteře.)

## Umístění

- **Nová složka `reality/`** — „how the world is wired": kauzální struktura světa, povaha fyzikálních zákonů, co z toho fyzika umí a neumí rozhodnout. Budoucí sourozenci: šipka času, simulační hypotéza, jemné doladění konstant, realismus vůči zákonům.
- **Řez vůči `cosmos/`:** cosmos = co ve vesmíru **je** a kde v tom jsme my (otázky v principu observačně rozhodnutelné — Fermi, Filter); reality = **čím** vesmír je a podle jakých pravidel běží (otázky, kde pozorování možná v principu nestačí). Třídicí test: „může tuhle otázku v principu rozhodnout pozorování?"
- Autor přiznaně váhal — intuitivně mu téma sedělo do `cosmos/` — a rozhodl se `reality/` **zkusit**. Přesun je levný a vratný (`git mv` + pár řádků v README), kdyby se složka neosvědčila.
- `mind/` zůstává prázdná; čeká na plnohodnotnou poznámku o svobodné vůli / vědomí, na kterou tato poznámka dopředně odkáže z dovětku E.
- **Soubor:** `reality/determinism.md` (kebab-case jako ostatní poznámky).

## Titul a The question

- **H1:** *Is the universe deterministic — and could we ever know?*
- Laplaceovská definice: úplný stav světa v čase t + zákony ⇒ jediná možná budoucnost (a minulost).
- Hned rozplést, co determinismus **není**: předvídatelnost (chaos je deterministický a nepředvídatelný), kauzalita, fatalismus.
- Otevřeně přiznaná autorova vstupní intuice („QM ⇒ ne") jako testované tvrzení.
- Zmínka, že otázku přinesl kamarád — bez jména, dokud autor neřekne jinak.
- Statusová řádka podle konvence repa (last touched / sources checked).

## Konjektury (5)

- **A — Clockwork restored.** Vesmír je deterministický; kvantový „kolaps" je zdání. Nositelé: Bohmova mechanika, Everett (many-worlds).
- **B — The dice are real.** Náhoda je fyzikálně skutečná, kolaps je reálný fyzikální proces. Nositelé: objektivní kolapsové teorie (GRW/CSL). Autorova vstupní intuice je „lidová" verze B — v poznámce ji držet oddělenou od silné verze („chance je reálná" vs. „QM už to dokázala").
- **C — Undecidable from inside.** Deterministické a indeterministické formulace dávají stejné predikce; volba mezi nimi je zevnitř vesmíru trvale nerozhodnutelná — metafyzika, ne empirie. **Páteřní konjektura poznámky.**
- **D — Wrong kind of question.** Determinismus je vlastnost teorií/modelů, ne světa; otázka je špatně položená.
- **E — Nothing hangs on it.** I definitivní odpověď by nezměnila nic, na čem záleží (odpovědnost, svoboda, zásluha). Dovětek — jedna konjektura + dopředný odkaz na budoucí poznámku v `mind/`; tady se nesmí rozrůst.

## Refutační osy

- **Proti „QM ⇒ B" (vstupní intuice autora):** Bellův teorém vylučuje *lokální* skryté proměnné, ne determinismus; Bohm i Everett jsou deterministické a empiricky ekvivalentní standardní QM; „kolaps" možná není fyzikální proces (measurement problem).
- **Proti A:** Bohm platí nelokalitou; Everett problémem s pravděpodobností (odkud Bornovo pravidlo, když se stane „všechno"); superdeterminismus vypadá jako konspirace (vzdát se nezávislosti volby měření).
- **Proti B:** kolapsové modely dávají — na rozdíl od zbytku pole — *odlišné* testovatelné predikce a běžící experimenty je zatím jen ořezávají; žádný signál kolapsu. Empirie zatím spíš proti silné verzi B.
- **Proti C:** tatáž věc z druhé strany — část prostoru rozhodnutelná *je* (právě kolapsové modely), takže nerozhodnutelnost platí nanejvýš pro jádro Bohm/Everett/standard. A klasická fyzika není čistě deterministická (Nortonova kupole, útěky do nekonečna v newtonovské gravitaci) — neplatí školní obrázek „klasika = hodiny, kvantovka = kostky"; determinismus se láme teorie po teorii, ne jedním řezem.
- **Proti D:** pro vědeckého realistu teorie svět popisují — otázka se z modelů vrací zpět na svět.
- **Proti E:** libertariánská svoboda indeterminismus *potřebuje* (bez něj padá); opačným směrem Pereboom — odpovědnost prohrává v obou větvích, takže na odpovědi nezáleží z jiného důvodu, než E tvrdí; a kvantová náhoda možná stejně neškáluje do rozhodování (dekoherence, neuronový šum).

## Where it stands — proces

Nepíše se předem. Vykrystalizuje v dialogu nad hotovým draftem — je to autorův hlas, ne agentův. Závazek už teď: sekce „what would change my mind" bude ukazovat na **reálné běžící experimenty** (detekce signatur spontánního kolapsu → posun k B; konsensuální odvození Bornova pravidla v Everettovi → posun k A), takže poznámka bude falsifikovatelná doslovněji než většina ostatních v repu.

## Zásahy do repa

- Nová složka `reality/` + poznámka `reality/determinism.md`.
- Řádek složky + odrážka poznámky v `README.md`, `README.cs.md`, `README.pl.md` (EN kanonické, překlady zrcadlí) a popis složky v `AGENTS.md`. Všechny tyto zásahy landují **až po dopsání poznámky**, v jedné dávce s verdiktem — odrážka poznámky verdikt vyžaduje, takže dřív nedávají smysl.
- Jednovětý verdikt poznámky do README: destilát z Where it stands; nic rychle kazitelného, žádná čísla.
- Spec a plán česky v `docs/superpowers/`.

## Zdroje — kandidáti k verifikaci

**Nic z tohoto seznamu zatím není citace.** Vše je z paměti a při psaní musí být každý zdroj otevřen a ověřen (pravidlo repa: never cite from memory). Co neprojde, vypadne nebo dostane NOT VERIFIED. Očekávané opravy detailů (přesné roky, názvy, čísla) jsou normální a poznámka je zaznamená.

- SEP „Causal Determinism" (Hoefer) — mapa celého terénu; očekávaná opora pro „otázka je otevřená".
- John Earman, *A Primer on Determinism* (1986) — klasická knižní analýza, determinismus teorie po teorii.
- John Norton — kupole (selhání jednoznačnosti v newtonovské mechanice); ověřit přesnou publikaci.
- J. S. Bell, „On the Einstein Podolsky Rosen Paradox" (1964) + *Speakable and Unspeakable in Quantum Mechanics* — co teorém skutečně vylučuje; Bellovy vlastní komentáře k Bohmovi.
- SEP „Bohmian Mechanics", SEP „Many-Worlds Interpretation", SEP „Collapse Theories" — tři rodiny interpretací.
- Podzemní test kolapsových modelů (Donadi et al., Nature Physics, ~2020–2021) — experimentální ořezávání kolapsu; ověřit přesnou referenci a aktuální stav (perishable → `(as of YYYY-MM)`).
- Saari & Xia, „Off to Infinity in Finite Time" (Notices AMS, ~1995) — noncollision singularities, klasický indeterminismus.
- Dovětek E: P. F. Strawson „Freedom and Resentment" (1962); van Inwagen (consequence argument); Pereboom (hard incompatibilism).
- Kandidáti spíš do Threads to pull: superdeterminismus ('t Hooft, Hossenfelder), Conway–Kochen „free will theorem" (a jeho běžné dezinterpretace), obecná relativita (Cauchyho horizonty, cosmic censorship), odvození Bornova pravidla v Everettovi (Deutsch–Wallace).

## Mimo rozsah

- Plná poznámka o svobodné vůli a morální odpovědnosti → `mind/`, později.
- Hluboká sekce o obecné relativitě → nanejvýš odstavec + Threads to pull.
- Šipka času, simulace, jemné doladění → budoucí poznámky v `reality/`.

## Rozsah, tón, proces

- Cíl 350–450 řádků (mezi `great-filter` a `war`).
- Tón: thinking-in-progress; refutace jsou hlavní obsah; vstupní intuice se testuje, nehájí.
- Draft po sekcích, autor reaguje na hotový text; **žádné formulářové dotazníky** (preference potvrzená u nuclear-blackmail platí i zde).
- Po schválení specu: implementační plán (writing-plans), pak drafty.

## Rizika

- Celá fyzikální kotva je zatím z paměti → verifikace může některé tvrzení posunout (zejména přesný stav experimentů s kolapsovými modely); poznámka pak zaznamená opravu, ne jen výsledek.
- Dovětek E má sklon bobtnat → držet na jedné konjektuře + odkazu.
- Riziko „rešerše místo konjektury" → páteří je teze o rozhodnutelnosti (C) a její refutace, ne přehled interpretací QM.
