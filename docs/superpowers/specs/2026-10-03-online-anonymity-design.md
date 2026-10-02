# Design: poznámka `society/online-anonymity.md`

- **Datum:** 2026-10-03
- **Status:** návrh schválený v brainstormingu, čeká na revizi autorem
- **Jazyk poznámky:** angličtina (konvence repa); tento spec je pracovní dokument, proto česky
- **Architektura:** etická páteř (bilance anonymity) s technickou kotvou uvnitř refutací a politickým závěrem o držiteli klíče

## Cíl a kontext

Téma přinesl autor 2026-09-14 po videu o VPN. Pracovní název „Anonymita na internetu: dobro nebo zlo?" autor výslovně označil za **jen pracovní** — rámec dobro/zlo není závazný a poznámka ho má právo rozebrat.

**Vstupní intuice autora, zapsaná před rešerší jako testované tvrzení:** anonymita na internetu je **mírně zlo**. Tři důvody, jeho slovy: (1) skrývá nelegální činnost, a ta ubližuje nevinným lidem; (2) umožňuje šíření dezinformací; (3) umožňuje farmy botů.

**Účel, který autor uvedl:** potřebuje to **zvenčí, pro diskuze s kamarády** — ne jako vodítko pro vlastní chování na internetu. To má dva tvrdé designové důsledky:

- **Žádný osobní dovětek.** Poznámka neřeší „mám používat VPN / psát pod jménem". Praktická část, pokud bude, míří na uspořádání společnosti, ne na autorovu konfiguraci prohlížeče.
- **Nejcennější výstup je rozlišení silných a slabých argumentů, na obou stranách.** Munice, která se v diskuzi rozstřílí, je horší než žádná — kdo přijde s napadnutelným důvodem, ztratí kredit i pro ty pevné. Poznámka tedy musí u každého argumentu říct, jak snadno padne a čím.

Autor se v brainstormingu zeptal, proč se vůbec zapisuje vstupní intuice, když cílem je objektivní posouzení („nemůžeme posuzovat věci objektivně, že budeme mít vždy tvrzení a protitvrzení?"). Odpověď, na které stojí celá konvence: bez zapsané vstupní pozice nelze zjistit, že se závěr změnil — po rešerši má člověk silnou tendenci myslet si, že to tak viděl celou dobu. Determinismus je důkaz: protože ve specu stálo „QM ⇒ ne", mohla poznámka doložit, co padlo a čím. Riziko konfirmačního zkreslení z deklarované pozice je reálné a nese ho protitlak — povinný pokus závěr vyvrátit a zápis toho, co rešerše vlastnímu tvrzení ublížila, do Sources.

## Páteř

Autor označil za nejzajímavější **(b) etickou** otázku, se zájmem i o (a) technickou a (c) politickou. Poznámka o všech třech ve stejné váze by byla rešerše, ne konjektura, takže schváleno rozvržení **páteř + kotva + závěrečná část**, stejný tvar, který se osvědčil u determinismu:

- **Páteř — (b) etická:** má být anonymita dostupná, když z ní těží i svinstvo? Tohle je tvrzení, které se dá držet a napadnout.
- **Kotva — (a) technická, uvnitř refutací:** etický spor o nedosažitelnou (nebo neodebratelnou) věc je planý, takže se nejdřív musí vyjasnit, co je vůbec na stole. Sem patří i vyřízení toho videa: VPN neodstraňuje sledovatelnost, jen přesouvá důvěru od poskytovatele připojení k provozovateli VPN — pro většinu hrozeb nulový posun.
- **Závěrečná část — (c) politická:** „zrušit anonymitu" v praxi nikdy neznamená zrušit ji, nýbrž dát někomu moc ji prolomit. Skutečná volba tedy není mezi anonymitou a jejím opakem, ale mezi tím, kdo drží klíč a kdo kontroluje jeho.

Zvažovaná a zamítnutá alternativa: páteř na dvou nesouměřitelných asymetriích (anonymita chrání slabé před mocnými a zároveň slabé před slabými), tvar ukrajinské poznámky. Elegantnější, ale míň odpovídá tomu, co autor chce do diskuzí.

## Umístění

- **Nová složka `society/`** — „how people arrange living together": jak je zařízené soužití, jaké kompromisy vynucuje společný veřejný prostor. Budoucí sourozenci: svoboda slova a její hranice, dohled, moderace obsahu, důvěra v institucích.
- **Řez vůči existujícím složkám:** `war/` je o ozbrojeném násilí mezi státy a povinnostech třetích stran; `religion/` o víře zkoumané zvenčí (včetně toho, čím je nebezpečná společnosti — ale východiskem je víra, ne uspořádání); `society/` o pravidlech společného soužití mezi lidmi, kteří si nevybrali, že spolu budou žít. Třídicí test: „je východiskem instituce nebo norma soužití, ne příroda, víra ani válka?"
- **Soubor:** `society/online-anonymity.md` — ne `anonymity.md`, protože anonymita obecně (anonymní dárcovství, anonymní recenzní řízení) je jiné téma s jinou bilancí.
- Zásahy do `README.md` (+ oba překlady) a `AGENTS.md` (řádek složky) až po dopsání poznámky, v jedné dávce s verdiktem — stejně jako u determinismu.

## Titul a The question

- **H1 (návrh):** *Does online anonymity do more harm than good — and is less of it even on the table?*
- Dvoudílný tvar drží obě poloviny: první část je autorova otázka (b), druhá vtahuje (a) i (c) a předem signalizuje, že odpověď „méně anonymity" nemusí být dostupná volba.
- **The question musí rozplést, že „anonymita" není jedna věc.** Tři stupně, které se v debatách splývají a jejichž bilance se liší:
  - **pseudonymita** — vystupuji pod jménem, které není občanské, ale provozovatel platformy (a tedy po soudním příkazu i stát) moji identitu zná;
  - **nedohledatelnost pro protistranu** — ani provozovatel identitu nezná, ale provoz jde přes identifikovatelné připojení;
  - **nesledovatelnost** — ani metadata nespojí obsah s osobou (Tor, mixnety).
- Dál rozplést, co anonymita **není**: soukromí (to je o obsahu, ne o autorství), šifrování (chrání obsah, ne identitu), beztrestnost (anonymita zvyšuje cenu dohledání, neruší právo).
- Otevřeně přiznaná vstupní intuice autora včetně tří důvodů, jako testované tvrzení.
- Zmínka, že téma přinesl autor po videu o VPN; bez jmenování konkrétního videa, dokud autor neřekne jinak.
- Účel „do diskuzí" se do poznámky **nepíše** — je to kontext práce, ne obsah.
- Statusová řádka podle konvence repa (last touched / sources checked).

## Konjektury (5)

- **A — Net harm.** Anonymita působí celkově víc škody než užitku: zlevňuje trestnou činnost ubližující nevinným, zaplavuje veřejný prostor manipulací a umožňuje provoz botích sítí. Svět s menší anonymitou by byl lepší. *Tohle je autorova vstupní pozice.* V poznámce držet její **nejsilnější** verzi, ne tu nejsnáze porazitelnou (konvence „refute the organized defence") — tedy verzi opřenou o nejlépe dokumentované škody, ne o botí farmy.
- **B — Shield of the weak.** Anonymita je nutná podmínka toho, aby mohli mluvit lidé, kteří mají co ztratit: whistlebloweři, disidenti, oběti domácího násilí, novinářské zdroje, lidé pronásledovaní za identitu. Náklady jsou reálné a jsou cenou za to, že vůči moci vůbec může existovat opozice.
- **C — Not a dial.** Otázka „má být anonymita dostupná" je špatně položená, protože anonymita není nastavitelná vlastnost systému. Buď technická možnost nesledovatelné komunikace existuje — a pak ji nelze odebrat jen zlým aktérům — nebo neexistuje, a pak ji nemají ani ti ohrožení. Mezistupeň není; je jen otázka, komu dáme klíč. *Technická kotva (a).*
- **D — The middle rung.** Většinu užitku anonymity dodá pseudonymita s dohledatelností u provozovatele, a většinu škod dělá až úplná nesledovatelnost. Správná odpověď tedy není ani jedno z krajních, ale posun systému o jeden stupeň.
- **E — Who holds the key.** Skutečná otázka není kolik anonymity, ale kdo ji smí prolomit, za jakých podmínek a pod jakou kontrolou. Každý návrh na „zrušení anonymity" je ve skutečnosti návrh na přidělení moci, takže bilanci anonymity nelze spočítat bez identity držitele klíče. *Politická závěrečná část (c); paralela k verdiktu `religion/religion-risk.md`, kde moc je spoušť.*

## Refutace a tenze — linie tlaku

Refutace jsou hlavní obsah poznámky. Předem ohlášené linie (autorovi sděleny v brainstormingu, aby výsledek nebyl překvapení):

1. **Proti A, rozklad tří důvodů podle pevnosti.** Očekávaný výsledek: nestejná pevnost.
   - *Botí farmy* anonymitu v silném smyslu nepotřebují — běží na kupovaných, kradených a často plně verifikovaných účtech; verifikace je pro ně vstupní náklad, ne překážka. Tlak posune tvrzení z „anonymita to umožňuje" na „anonymita to zlevňuje", což je slabší.
   - *Dezinformace* se nejúčinněji šíří pod skutečnými jmény a přes státní média, protože jméno dodává autoritu, kterou anonym nemá. Totéž posunutí jako výše, možná silnější.
   - *Nelegální činnost ubližující nevinným* je nejpevnější noha a materiál pro ni existuje. I tady ale ověřit, nakolik je anonymita **nutnou** podmínkou: velké případy padly na operačních chybách a běžné vyšetřovací práci, ne na prolomení anonymizační technologie.
2. **Proti B.** Je anonymita nutná podmínka, nebo jen užitečná? Whistleblowing často probíhá přes identifikované kanály s právní ochranou, a nejznámější případy šly přes novináře, který zdroj znal. Pokud je B jen „užitečná", oslabuje to její váhu proti A.
3. **Proti C.** Mezistupně existují a fungují asymetricky: ověřování věku, KYC u platforem, povinné uchovávání provozních dat. Zvednou cenu pro náhodného trolla, ne pro odhodlaného aktéra — takže „není to kohoutek" je možná přehnané a správnější je „kohoutek, který účinkuje jen na ty, kterých se nejvíc nebojíme".
4. **Proti D.** Pseudonymita s dohledatelností u provozovatele dělá z provozovatele jediný bod selhání — a ten se dá hacknout, koupit, podrobit nebo prostě vyměnit majitele. Pro disidenta je „provozovatel zná mou identitu" totéž jako žádná anonymita. D tedy funguje pro trolling, ne pro to, co B chrání.
5. **Proti E.** Přesouvá otázku, ale neodpovídá na ni. I dobře kontrolovaný klíč mění chování lidí už svou existencí (chilling effect), takže bilanci nelze uzavřít poukazem na kvalitu kontroly.
6. **Napříč — asymetrie, kterou je třeba pojmenovat:** škody z anonymity jsou viditelné a spočitatelné (případy, oběti, čísla), užitek je z definice neviditelný (projev, který se uskutečnil, protože autor nebyl dohledatelný, nelze spočítat ani identifikovat). To systematicky zkresluje intuici ve prospěch A a je to samo o sobě argument proti důvěře ve vlastní pocit z té bilance.

## Where it stands — procedura

Předem stanovené vyhodnocení (čte se po refutacích, nevymýšlí se podle výsledku):

1. **Projít tři nohy autorovy vstupní intuice** a u každé zapsat, jestli obstála, posunula se („umožňuje" → „zlevňuje"), nebo padla.
2. **Rozhodnout páteřní otázku** jedním ze tří výsledků: (i) A obstojí i po oslabení dvou nohou; (ii) A se udrží jen pro část spektra anonymity (nejspíš nesledovatelnost, ne pseudonymitu) — pak je verdiktem C nebo D, ne A; (iii) A padá a zbývá spor B vs. E.
3. **Explicitně říct, co by změnilo názor** — u každého výsledku jiná falzifikace.
4. **Nepřeklopit se do opačné jistoty.** Pokud rešerše oslabí A, výsledkem není „anonymita je dobro", ale přesnější popis toho, kde bilance leží a kde evidence končí; determinismus skončil u „tušení držené jako vkus, ne poznatek" a tenhle tvar je i tady legitimní.
5. **U každého argumentu říct, jak snadno padne.** Vyhodnocení pevnosti je obsah poznámky, ne servis autorovi: text, který nerozliší pevný důvod od napadnutelného, nesplnil zadání. Patří do Where it stands, případně do Threads to pull — ne do samostatné sekce mimo šablonu.

## Co ověřit (vše zatím z paměti, nic necitovat bez kontroly)

Prioritní, protože by to byl nejsilnější empirický materiál:

- **Jihokorejský zákon o reálných jménech** (systém ověřování identity u větších portálů, zaveden ~2007, zrušen Ústavním soudem ~2012) — reálný přírodní experiment se zrušením anonymity. Ověřit: co přesně zákon vyžadoval, proč byl zrušen, a **co měřily studie o jeho efektu na toxicitu komentářů** (vybavuji si práci, která našla efekt blízký nule nebo nekonzistentní, ale **nemám ověřenou citaci** — bez dohledání primárního zdroje do poznámky nepatří).
- **Kdo šíří dezinformace** — studie o koncentraci šíření (Twitter/X v kampani 2016, případné novější) a role účtů pod reálnými jmény a státních médií. Ověřit konkrétní práce, nespoléhat na obecně kolující tvrzení.
- **Jak fungují botí farmy a troll farmy** — podíl verifikovaných, kupovaných a kradených účtů; dokumentace k ruské Internet Research Agency a jejím personám pod reálně vypadajícími jmény.

Dále:

- **VPN:** co technicky mění na threat modelu, co znamenají tvrzení „no logs" a které z nich byly nezávisle auditované; jak se marketing rozchází se skutečností.
- **Tor:** metriky užití, odhady podílu nelegálního provozu (ověřit metodologii, tahle čísla jsou notoricky sporná), a jak padly velké případy (Silk Road, AlphaBay) — operační chyby vs. prolomení protokolu.
- **Whistleblowing:** právní ochrana (EU směrnice o whistleblowingu, americká úprava) vs. anonymita jako cesta; jak u známých případů běžel kanál ke zdroji.
- **Chilling effect:** měření po roce 2013 (změny v chování při vyhledávání a čtení citlivých témat). Mám v paměti jednu práci o provozu na Wikipedii, **citaci neověřenou** — dohledat, nebo vypustit.
- **Politiky reálných jmen na platformách** a dokumentovaná škoda na skupinách, které jméno ohrožuje.
- **Aktuální legislativa** — ověřování věku a návrhy na skenování obsahu v EU a Británii. **Silně perishable:** všechno označit `(as of YYYY-MM)`.
- **Vyšetřování zneužívání dětí:** jakou roli hraje anonymizace v obou směrech (ukrývání i ochrana oznamovatelů a vyšetřovatelů).

## Mimo rozsah

- Jakýkoli návod, jak se anonymizovat — tohle není technický manuál.
- Kryptografické vnitřnosti (onion routing, mixnety) nad rámec toho, co unese kotva.
- Svoboda slova a její hranice jako samostatné téma → budoucí poznámka v `society/`.
- Dohled a sledování jako samostatné téma → budoucí poznámka v `society/`.
- Ochrana osobních údajů jako právní úprava → nanejvýš odstavec a Threads to pull.

## Rozsah, tón, proces

- Cíl 350–450 řádků, srovnatelně s `determinism` a `ukraine-war-justification`.
- Tón: thinking-in-progress; refutace jsou hlavní obsah; vstupní intuice se **testuje, nehájí**.
- Draft po sekcích, autor reaguje na hotový text; **žádné formulářové dotazníky** (potvrzená preference, platí i zde).
- Po schválení specu: implementační plán (writing-plans), pak drafty po sekcích.
- Nová složka `society/` vzniká spolu s poznámkou; řádek v `AGENTS.md` a verdikt v `README.md` + oba překlady jedinou dávkou po dopsání.

## Rizika

- **Všechny empirické podklady jsou zatím z paměti.** U tématu, kde kolují nepřesná čísla (podíl nelegálního provozu v Toru, efekt zákonů o reálných jménech), je riziko konfabulace vyšší než obvykle. Důsledek: žádné číslo bez dohledaného primárního zdroje, a co se nedohledá, buď vypadne, nebo se označí jako neověřené.
- **Téma je politizované a rychle stárne** — legislativa se mění v řádu měsíců. Perishable tvrzení označovat `(as of YYYY-MM)` důsledněji než u jiných poznámek.
- **Riziko „pro a proti" místo konjektury.** Páteří musí být tvrzení o bilanci a jeho refutace, ne vyvážený přehled. Pojistka: Where it stands musí skončit pozicí, ne shrnutím.
- **Riziko příliš rychlého rozstřílení autorovy pozice.** Dvě ze tří nohou vypadají slabě už před rešerší, což svádí k tomu podat A v její nejslabší formě. Konvence „refute the organized defence" to zakazuje: A dostane svou nejsilnější verzi, postavenou na nejlépe dokumentovaných škodách.
- **Riziko, že užitek anonymity zůstane abstraktní.** Škody mají jména a čísla, užitek je neviditelný. Pokud se nenajdou konkrétní dokumentované případy, kde anonymita umožnila projev, který by jinak nebyl, bude B slabší, než jaká je — a tohle zkreslení je třeba přiznat v Sources, ne obejít.
