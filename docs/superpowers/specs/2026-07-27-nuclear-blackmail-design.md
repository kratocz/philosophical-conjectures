# Design: poznámka `war/nuclear-blackmail.md`

- **Datum:** 2026-07-27
- **Status:** návrh schválený v brainstormingu, čeká na revizi specu
- **Jazyk poznámky:** angličtina (konvence repa); tento spec je pracovní dokument, proto česky
- **Architektura:** „audit s předregistrací" — poznámka audituje nekrytou směnku z
  [[ukraine-war-justification]] („jaderné riziko omezuje *jak*, nikdy *zda*");
  konjektury A–D jsou soupeři **bez předem vybraného vítěze**, verdikt vznikne až
  v draftu průchodem předepsanou rozhodovací procedurou

## Cíl a kontext

Druhá poznámka složky `war/`, vyrostlá z prvního vlákna ukrajinské poznámky („The
ethics of nuclear blackmail"). Jádro: **smí obránce a třetí strany ustoupit jaderné
koerci — a může jaderná hrozba změnit, co je správné?** Etika odstrašení (Kavkův
paradox) a proliferace (lekce Budapešti) vstupují jako podvrstvy, ne jako rovnocenná
témata.

**Auditovaná směnka.** Ukrajinská poznámka nese svůj verdikt o podpoře na větě,
kterou si nikdy neodpracovala (dva lokusy, citovat doslova):

> "On the nuclear tail: E absorbs it as a constraint on *how* — which capabilities,
> which targets, what pace — never on *whether*; because if nuclear threats can
> defeat a defense outright, nuclear blackmail becomes a master key that opens any
> neighbor, and the lesson every state on a nuclear border learns is: get warheads."
> (Refutations, blok „Against D")

> "And the nuclear tail stays absorbed as a constraint on *how*, never on
> *whether*: the alternative is a world in which warheads are the only sovereignty
> worth having — the proliferation lesson Budapest already teaches once."
> (Where it stands, odstavec o podpoře)

**Klíčová odlišnost od obou předchozích poznámek:** autor jde do tématu **úplně
načisto** — na čtyři polohové otázky (absolutnost zásady neustupování; čára
jak/zda; přípustnost odstrašení; proliferační důsledek Budapešti) odpověděl
„nevím — vypracovat" a odmítl i předvýběr kandidátního kritéria. Spec proto NESMÍ
předepisovat verdikt ani autorovu konjekturu; předepisuje otázku, soupeře,
refutační tlaky a rozhodovací proceduru. Where it stands se píše až po vybojování
refutací v dialogu.

**Předregistrované výsledky auditu** (zapsat do The question, závazně):

- **(i) směnka splacena** — čára „jak/zda" je obhajitelná; vindikace se zapíše do
  této poznámky, ukrajinská se nemění;
- **(ii) splacena s úpravou** — čára drží, ale formulace ukrajinské poznámky se
  musí opravit; revize se provede a viditelně zaznamená v OBOU poznámkách;
- **(iii) směnka propadla** — čára je neudržitelná; verdikt o podpoře v ukrajinské
  poznámce se převáží a revize se zapíše (popperovský pohyb repa: poznámky se
  navzájem omezují, škody se zapisují).

## Umístění a rám

- **Soubor:** `war/nuclear-blackmail.md` (kebab-case, koncept-first jako ostatní).
- **Titulek (H1):** *Can a nuclear threat change what is right?*
- **README + AGENTS.md: beze změn** — řádka `war/` už existuje (rozdíl proti
  ukrajinské poznámce).
- **Statusová řádka:** dle `TEMPLATE.md`, obě data reálná; `sources checked`
  finalizuje verifikační task.
- **Křížové odkazy:** [[ukraine-war-justification]] (těžká vazba — auditovaná
  směnka, revizní hák); [[meaning-without-guarantee]] (lehce — rodina
  strukturálních argumentů, pokud se dveřní tah vynoří u nevratnosti ustoupení).
- **Strategie stárnutí:** lehčí než u Ukrajiny. Base rate Sechser/Fuhrmann je
  historická a stabilní; datovaný je kotevní blok (rekord hrozeb této války, stav
  doktrín) s `(as of YYYY-MM)`; `sources checked` jako expirace.
- **Pevná jména** (užívají všechny fáze beze změn): **the audited sentence / the
  IOU**; konjektury **A — Never yield**, **B — The tail dominates**, **C — There
  is no line**, **D — Build the counter-structure**; bloky **the umbrella
  admission**, **the Jupiter problem**; testy procedury **the salami test**, **the
  Kavka test**, **the endogeneity ledger**, **the umbrella consistency test**,
  **the Jupiter test**; výsledky **(i) paid**, **(ii) paid with amendment**,
  **(iii) defaulted**.

## Architektura poznámky

### The question

1. Ocitovat doslova oba lokusy směnky a říct na rovinu: byla to nekrytá směnka —
   tvrzení neslo verdikt o podpoře, aniž si odpracovalo důkaz. Tato poznámka je
   audit; předregistrovat výsledky (i)/(ii)/(iii) a závazek zapsat důsledek do
   obou poznámek.
2. Jádrová otázka: **může jaderná hrozba změnit, co je správné?** Švy držené
   viditelně: mění *prudenci* vs. mění *dovolení a povinnosti*; hrozba
   *odstrašující* (zachovat status quo) vs. *kompelentní* (změnit ho — vydírání;
   Schellingovo rozlišení, ověřit); povinnosti obránce vs. třetích stran.
3. Kotevní blok **„The nuclear record as of 2026-07"** (bold lead-in, uvnitř The
   question, fakta ověřená in-task): rekord ruských jaderných hrozeb 2022–2026
   a co po nich následovalo — epizody překročení „červených linií" s daty (HIMARS,
   tanky, Storm Shadow, ATACMS, F-16, Kursk) jako přirozené experimenty; podzimní
   krize 2022; změna doktríny 19. 11. 2024; rozmístění v Bělorusku; Oreshnik.
   Base rate: Sechser & Fuhrmann — kompelentní jaderné hrozby historicky téměř
   neuspívají (přesnou tezi a čísla ověřit). Odzbrojovací případy: UA/BY/KZ po
   1991, JAR. Vše s `(as of YYYY-MM)` a větou o expiraci.
4. **The umbrella admission** (ohlásit tady, plně v refutacích): autor žije pod
   jaderným deštníkem NATO — jeho bezpečnost kupují přesně ty podmíněné úmysly,
   které poznámka zkoumá. Analog „daylight asymmetry" a „Mnichova v krvi":
   přiznaná pozice, ze které se nejde vyvázat analýzou.
5. Proč teď: dědictví ukrajinské poznámky (revizní závazek) + živý rekord hrozeb.

### Conjectures

Čtyři soupeři, každý vysloven v nejsilnější formě, **žádný autorův**:

- **A — Never yield.** Ustoupit jaderné kompelenci je vždy špatně: universalizace
  (svět, kde hlavice platí, je svět samých hlavic), pobídková kaskáda (každý
  úspěch kupuje další hrozbu), base rate jako opora. Nejsilnější forma: i
  *započítat* hrozbu do kalkulu je částečná platba — správný kalkul ji ignoruje.
- **B — The tail dominates.** Někdy je ustoupení správné: nenulová P(použití) ×
  téměř nekonečná škoda převáží každou konečnou sázku; odmítat vážit je
  nenumerické hrdinství s cizími městy; Schellingova „hrozba, která nechává něco
  náhodě" — i vzdor hází kostkou za nesouhlasící. Silná forma: zdrženlivé epizody
  této války byly správné a víc ústupků by bylo správnějších.
- **C — There is no line.** „Jak, nikdy zda" je nestabilní: každé omezení „jak"
  (žádná no-fly zóna, odklad ATACMS, žádní vojáci) doručilo část požadavku;
  řízení rizika a částečná kapitulace jsou tytéž akty pod různými popisy; mezi
  „rozumnou opatrností" a „faktickým vetem" není principiální zastávka. **Obstojí-li
  C, směnka propadá.**
- **D — Build the counter-structure.** Dilema je symptom selhané architektury:
  udělat vydírání neživotaschopným ex ante (věrohodné rozšířené odstrašení,
  automatismy, záruky se zuby — to, čím Budapešť nebyla). Kde je vydírání
  kredibilní, někdo už dřív selhal; skutečná povinnost leží na deštníkových
  státech před krizí.

Etika odstrašení a proliferace nejsou samostatné konjektury — vstupují
v refutacích jako tlaky na A a D.

### Refutations & tensions

**Proti A:** Kavkův tlak (odmítání ustoupit stojí na protihrozbě, kterou nikdo
nesmí vykonat — je-li odstrašující úmysl nepřípustný, norma si půjčuje z mravně
insolventního účtu; řešení „blaf" podkopává kredibilitu — ověřit Kavkovy
formulace); čistá forma se podvrací (ignorovat katastrofický kalkul nelze splnit);
agregační problém recyklovaný z Ukrajiny (norma utrácí konkrétní města za
systémová dobra — dveře řežou obousměrně); endogenita base rate poctivě na obě
strany (selhávání kompelence je produkt vzdoru → norma je sebenaplňující, ale
citovat base rate jako nezávislý důkaz je kruhové).

**Proti B:** struktura Pascalova přepadení (aritmetika s téměř nekonečnem je
unesitelná kýmkoli, kdo řekne „nebo všechno" — B tiskne licenci každému budoucímu
vyděrači); endogenita P(použití) (pravděpodobnost reaguje na pobídky; statická
očekávaná hodnota ignoruje dynamický člen); selektivní konsent (ustoupení hází
kostkou za budoucí cíle precedentu); empirie přirozených experimentů (červené
linie překračovány bez jaderné odpovědi — P(použití|vzdor) soustavně
nadhodnocena; epizody ověřit s daty).

**Proti C:** čáru lze vést u **doručení požadavku** (zdrženlivost rozkládající
riziko, kterou vyděrač nežádal ≠ doručení žádané položky; těžké případy neruší
rozdíl — sorites); C dokazuje příliš (pak je kapitulací i odstrašení a pojem
ztrácí kontrast); **zapsat, co z C přežívá:** střední cesta musí svá zastavení
UKÁZAT — auditovaná věta, jak byla napsaná, byla gesto (ožívá výsledek (ii)).

**Proti D:** mění téma na účet oběti (rada minulosti; otázka zní, co teď,
s architekturou, kterou jsme nepostavili); automatismy kupují blackmail-proofing
za riziko nehody (kubánské near-misses — D musí nacenit vlastní ocásek);
rozšířené odstrašení JE podmíněný úmysl na druhou (D dědí Kavku krát spojenci).

**Průřezové bloky:** **the umbrella admission** (shledá-li autor odstrašení
nepřípustným, konzistence vystaví účet jemu — vystoupit zpod deštníku?; shledá-li
přípustným, dluží argument); **the Jupiter problem** (Kuba 1962: vlajková loď
vzdoru skončila tichým ústupkem — Jupitery z Turecka; co to dělá s A: veřejná
norma + soukromá flexibilita jako „fungující pokrytectví"? fakta ověřit).

### Where it stands

**Procedura místo verdiktu.** Sekce se píše až po vybojování refutací; spec
předepisuje testy, kterými musí projít, a formát výsledku:

1. **The salami test** (proti C): čára „jak/zda" musí říct svá zastavení
   konkrétně pro skutečné epizody (no-fly zóna, načasování ATACMS, žádní vojáci)
   — pravidlem, ne gestem.
2. **The Kavka test** (proti A): potřebuje „never yield" přípustný odstrašující
   úmysl, a existuje nějaký?
3. **The endogeneity ledger** (A↔B): přebijí dynamické členy statický ocásek?
   Za jakých předpokladů — vypsat je.
4. **The umbrella consistency test:** závěr musí autor unést jako obyvatel státu
   pod rozšířeným odstrašením.
5. **The Jupiter test:** podporuje Kuba 1962 normu, nebo fungující pokrytectví —
   a co z toho pro čáru plyne?

Sekce vyhlásí **(i) paid / (ii) paid with amendment / (iii) defaulted**
s odůvodněním a vykoná důsledek (viz revizní hák v procesu). Připustit i poctivé
„nerozhodnuto mezi X a Y, a tady je proč" — ale i to je výsledek auditu a musí
říct, co by rozhodlo. **What would change my mind:** ≥ 4 body, formulované podle
výsledku.

### Threads to pull

- Plná etika odstrašení (Kavka, Finnis/Boyle/Grisez, Ramsey) — kandidát na vlastní
  poznámku ve `war/`.
- Proliferační pokračování Budapešti (napojení na vlákno „co dluží signatáři
  ujištění" z ukrajinské poznámky).
- Kuba 1962 jako vlajkový případ pro epistemologii analogií (napojení na vlákno
  Mnichov vs. Finsko).
- Rodina strukturálních kritérií: má „test doručení požadavku" stejný tvar jako
  vstupní/výstupní asymetrie a jednosměrné dveře? (meta-poznámka)
- Kolektivní konsent pod existenčním rizikem: kdo smí házet kostkou, kterou
  nikdo z ohrožených nehodil (navazuje na „kdo vyslovuje volbu Ukrajiny").

### Sources — verifikační plán

Laťka ukrajinské poznámky: **nikdy z paměti; inline `[VERIFY]` flagy; dvoustupňová
verifikace** (fakta při draftování sekce, texty v konsolidačním průchodu);
neověřené → **NOT VERIFIED** s důvodem; opravy viditelně do Sources (i „nic" je
záznam).

| Blok | Co se z něj ověřuje |
|---|---|
| Schelling, *The Strategy of Conflict* (1960); *Arms and Influence* (1966) | rozlišení deterrence/compellence; „the threat that leaves something to chance" — které dílo co říká, přesná znění |
| Kavka, „Some Paradoxes of Deterrence", *Journal of Philosophy* (1978) | přesná formulace paradoxu podmíněného úmyslu; co Kavka skutečně tvrdí o řešeních |
| Sechser & Fuhrmann, *Nuclear Weapons and Coercive Diplomacy* (2017) | přesná teze; dataset: kolik kompelentních jaderných hrozeb, kolik uspělo |
| Walzer (kapitola o odstrašení, supreme emergency) | přesné pasáže pro/proti přípustnosti |
| Finnis/Boyle/Grisez, *Nuclear Deterrence, Morality and Realism* (1987) | deontologická pozice proti odstrašení — jen v rozsahu použití |
| Rekord hrozeb 2022–2026 | podzimní krize 2022; změna ruské doktríny 19. 11. 2024 (text dekretu); Bělorusko 2023; Oreshnik 11/2024; epizody linií s daty: HIMARS 2022, tanky 1/2023, Storm Shadow 5/2023, ATACMS (dodání/povolení dosahu), F-16 2024, Kursk 8/2024 — každá epizoda: hrozba → akce → (žádná) jaderná odpověď |
| Kuba 1962 | Jupiterský obchod — National Security Archive či ekvivalent |
| Budapešť/NPT; UA/BY/KZ, JAR | zděděné zdroje z ukrajinské poznámky + fakta odzbrojení JAR |
| Doktríny k 2026-07 | aktuální stav ruské deklaratorní doktríny; případné změny 2025–2026 dohledat |

### Proces psaní

1. Spec (tento dokument) → commit → revize autorem.
2. `superpowers:writing-plans` → plán do `docs/superpowers/plans/` → commit.
3. Draft po sekcích v pořadí šablony; **konjektury a refutace vznikají v dialogu
   — autor jde načisto, takže dialog je tu ještě důležitější než u Ukrajiny**;
   každou sekci schvaluje autor; Where it stands se píše POSLEDNÍ z obsahových
   sekcí (po refutacích), teprve pak Threads a Sources.
4. Dvoustupňová verifikace; nálezy do Sources včetně oprav.
5. **Revizní hák:** padne-li výsledek (ii) nebo (iii), přibude task: editovat
   `war/ukraine-war-justification.md` (větu / verdikt o podpoře), aktualizovat
   její `last touched`, zapsat křížovou revizi viditelně do obou poznámek
   (v ukrajinské: co se změnilo a proč, s odkazem [[nuclear-blackmail]]);
   commit `revise ukraine-war-justification: pay the nuclear IOU`.
6. Commit poznámky: `add nuclear-blackmail conjecture` (krátce, přítomný čas);
   další tasky `draft nuclear-blackmail: <sekce>`, verifikace `verify
   nuclear-blackmail sources; record corrections`, závěr `revise
   nuclear-blackmail: final pass`.

## Mimo rozsah

- Úplné pojednání o etice odstrašení (jen v rozsahu tlaku na A/D; plné téma je
  vlákno).
- Jiné jaderné dyády (KLDR, Írán, Indie–Pákistán) nad rámec konzistenčních zmínek.
- Policy advocacy (rozmisťování, sdílení hlavic, výdaje) nad rámec otázky
  oprávněnosti.
- Revize ukrajinské poznámky nad rámec revizního háku (jen směnka / verdikt
  o podpoře).

## Kritéria hotovosti

- `war/nuclear-blackmail.md` existuje, drží pořadí sekcí `TEMPLATE.md` a tón repa
  (thinking-in-progress, anglicky).
- Oba lokusy směnky citovány doslova; výsledky auditu předregistrovány v The
  question; Where it stands vyhlašuje (i)/(ii)/(iii) — nebo poctivé nerozhodnuto
  s rozhodovacím kritériem — a prošel všemi pěti testy procedury.
- Revizní hák vykonán, padl-li výsledek (ii)/(iii); křížová revize zapsána v obou
  poznámkách.
- Každé jmenovité či číselné tvrzení ověřené, nebo **NOT VERIFIED**; rychle
  stárnoucí tvrzení s `(as of YYYY-MM)`; po verifikaci `grep VERIFY` = 0.
- The umbrella admission přítomna (The question + refutace); konjektury A–D bez
  předvybraného vítěze — Where it stands se na žádnou z nich předem neodvolává
  jako na autorovu.
- Autor schválil každou sekci; commity dle konvence.
