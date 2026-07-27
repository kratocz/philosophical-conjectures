# Design: verdikty poznámek v README + česká verze rozcestníku

- **Datum:** 2026-07-27
- **Status:** návrh schválený v brainstormingu, čeká na revizi specu
- **Jazyk výstupů:** README.md a AGENTS.md anglicky (konvence repa), README.cs.md česky; tento spec je pracovní dokument, proto česky

## Cíl a kontext

Dva schválené požadavky autora:

1. **Stručné závěry** jednotlivých poznámek viditelné přímo v README — dnes README na
   žádnou poznámku ani neodkazuje, jen popisuje složky.
2. **Česká verze vstupu do repa** pro autorovy české přátele, s tím, že návrhy změn
   směřují do anglického originálu (issue/PR nad `main`).

Stav repa: 9 poznámek v pěti složkách (`continuity/` 3, `cosmos/` 2, `meaning/` 1,
`religion/` 2, `war/` 1), složka `mind/` je zatím bez poznámek. Každá poznámka má sekci
„Where it stands" — závěry tedy existují; jde o to, kam a jak stručně je zrcadlit.

## Rozhodnutí z brainstormingu

- **Česky bude jen vstup** — nový `README.cs.md`. Poznámky samotné zůstávají anglicky;
  cílové publikum anglické poznámky přečte, česky potřebuje rozcestník a verdikty.
- **Verdikty se integrují do sekce „How it's organized"** jako jednovětné kurzívní
  destiláty s odkazy na poznámky. README se tím stane skutečným rozcestníkem.
- **CONTRIBUTING.md se nepřekládá.** README.cs.md dostane krátkou sekci „Jak
  nesouhlasit" (shrnutí, kam mířit) + odkaz na plný anglický návod.
- **Žádný branch ani samostatné repo pro překlad.** Branch by se rozjel s `main` a
  návštěvník GitHubu ho nevidí; druhé repo tříští issues. Překlad žije jako soubor
  v `main`, standardní pattern `README.<lang>.md`.
- **Angličtina je canonical.** Obsahové změny se dělají jen v `README.md`; překlady se
  po každé změně aktualizují. Konvence počítá s možnými dalšími jazyky v budoucnu.

## Změny v README.md

1. **Řádek s překlady pod H1** — schválená podoba:
   `*Česky: [README.cs.md](README.cs.md)*`
   Formát snese přidání dalších jazyků (oddělovač ` · `).
2. **Sekce „How it's organized":** pod odrážkou každé složky přibudou pod-odrážky
   jejích poznámek ve tvaru `[Titulek poznámky](cesta) — *jednovětný verdikt.*`
   Složka `mind/` zůstane bez pod-odrážek (nemá poznámky).
3. **Úvod sekce** se doplní o jednu větu: verdikty jsou provizorní snapshoty; zdrojem
   pravdy je vždy poznámka — její „Where it stands" a caveaty okolo.
4. Ostatní sekce README beze změny.

## Nový soubor README.cs.md

- **Plný český překlad README.md** — všechny sekce, počeštěné verdikty, český H1
  („Filozofické konjektury").
- **Hlavička pod H1** (před vlastním obsahem):
  - Toto je překlad [anglického originálu](README.md); **originál je závazný a jediný
    se edituje**. Návrhy změn (issue/PR) směřujte na originál — **můžete je psát
    i česky**.
  - Drift-marker: „Překlad odpovídá stavu originálu k YYYY-MM-DD." Datum se přepisuje
    při každém syncu překladu.
- **Odkazy na poznámky vedou na anglické soubory** (jiné neexistují).
- **Navíc sekce „Jak nesouhlasit":** pár vět shrnujících CONTRIBUTING — mířit na
  „What would change my mind", na položky **NOT VERIFIED** a na staré datum „sources
  checked"; oprava s dohledatelným zdrojem je nejcennější příspěvek; issue lze napsat
  česky. Odkaz na plný [CONTRIBUTING.md](../../../CONTRIBUTING.md) — v souboru
  samozřejmě jako relativní odkaz `CONTRIBUTING.md`.

## Konvence v AGENTS.md

Do sekce Conventions přibude:

- `README.md` (a veškerý obsah poznámek) je anglicky a je canonical. Soubory
  `README.<lang>.md` jsou překlady-zrcadla; obsahové změny se v nich nedělají.
- Po každé změně `README.md` se aktualizují **všechny existující překlady** včetně
  jejich sync data.
- Změní-li se „Where it stands" některé poznámky, aktualizuje se její jednovětný
  verdikt v `README.md` — a tím i v překladech (předchozí bod).

## Pravidla formulace verdiktů

- Jedna věta na poznámku; **destilát sekce „Where it stands"**, žádný nový claim ani
  zpřesnění nad rámec poznámky.
- Zachovat provizorní tón originálu („lean", „provisional", „no verdict" je také
  legitimní verdikt).
- **Žádné pomíjivé údaje** — čísla, procenta, „as of" — verdikt nesmí mít vlastní
  expirační datum.
- U citlivých poznámek (`religion-risk`, `ukraine-war-justification`,
  `bible-veracity`) držet přesnost a opatrnost formulace originálu; verdikt nesmí být
  ostřejší než poznámka.
- Anglické znění v `README.md`, český překlad téhož v `README.cs.md`.
- Konkrétní znění všech 9 verdiktů vznikne v implementačním plánu a schvaluje je autor
  vcelku.

## Údržba a rizika

- **Drift verdikt ↔ poznámka:** řeší konvence v AGENTS.md + zákaz pomíjivých údajů ve
  verdiktech.
- **Drift překlad ↔ originál:** řeší sync datum v hlavičce a konvence „po každé změně
  aktualizovat všechny překlady".
- **Vytržení z kontextu:** řeší úvodní věta sekce a kurzíva signalizující snapshot.
- **Žádné build tooling** — repo zůstává čistý Markdown bez závislostí (v souladu
  s AGENTS.md); sync je ruční, vynucovaný konvencí.

## Mimo rozsah

- Překlad poznámek samotných (může přijít později, po jedné a na vyžádání).
- Překlad CONTRIBUTING.md a AGENTS.md.
- Založení dalších jazykových verzí (konvence s nimi počítá, žádná teď nevzniká).
- Jakákoli automatizace synchronizace.

## Akceptační kritéria

- `README.md`: odkaz na českou verzi pod H1; všech 9 poznámek vypsáno pod svými
  složkami s funkčním relativním odkazem a jednovětným verdiktem; úvodní věta
  o provizornosti verdiktů.
- `README.cs.md`: plný český překlad s plnou diakritikou; hlavička s odkazem na
  originál, pravidlem „edituje se jen originál, návrhy klidně česky" a sync datem;
  sekce „Jak nesouhlasit" s odkazem na CONTRIBUTING.md.
- `AGENTS.md`: konvence o canonical angličtině, zrcadlových překladech a aktualizaci
  verdiktů.
- Verdikty splňují pravidla výše a autor je schválil.
- Commit messages podle konvence repa (krátké, present-tense).
