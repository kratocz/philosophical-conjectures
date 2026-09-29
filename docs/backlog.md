# Backlog témat

- **Stav k:** 2026-09-29
- **K čemu to je:** jediná verze toho, která témata jsou hotová, rozpracovaná, zaparkovaná a která čekají. Aktualizovat, když téma změní stav. Do 2026-09-29 tohle žilo jen v paměti agenta mimo git; přesunuto sem, protože paměť není verzovaná a zapisuje do ní víc session naráz.

## Hotovo

1. **Smysl života** — 2026-07-24: `meaning/meaning-without-guarantee.md` (páteř „Jak žít bez záruky smyslu?", autorův one-way-door argument, plně ověřené zdroje). Spec a plán v `docs/superpowers/`.
2. **Oprávněnost současné války na Ukrajině** — 2026-07-25: `war/ukraine-war-justification.md` („Who could end the war in Ukraine tomorrow — and what justifies not doing it?", nová složka `war/`). Páteř: dvě asymetrie (vstupní/výstupní) + standing argument + Mnichov s přiznanými mezemi; Sources s předmluvou oprav (Orwellovo odvolání 1944, Terijoki, ICJ 2024, Istanbul „at one remove"). Spec a plán v `docs/superpowers/`.
3. **Determinismus vesmíru** — 2026-09-10: `reality/determinism.md` („Is the universe deterministic — and could we ever know?", nová složka `reality/` = „how the world is wired", řez vůči `cosmos/`: rozhodnutelné pozorováním vs. ne). Páteř epistemická (rozhodnutelnost) + fyzikální kotva + dovětek „no a co"; konjektury A–E. Vstupní intuice autora „QM ⇒ vesmír není deterministický" nepřežila: kvantová mechanika nerozhodla ani jedním směrem (Bohm/Everett jsou empiricky ekvivalentní kolapsovým čtením), poctivá pozice je tušení ke soukolí držené jako vkus, ne poznatek. Commit f4ec230 stáhl neověřitelnou Bellovu citaci a opravil misattribuci Pereboomovi. Verdikt v README a překladech (e3a1d56). Spec a plán v `docs/superpowers/`.

## Rozpracováno

4. **Anonymita na internetu** — brainstorming začal 2026-09-14, téma přinesl autor po videu o VPN. Pracovní název „Anonymita na internetu: dobro nebo zlo?" je jen pracovní, rámec dobro/zlo není závazný. Vstupní námitka agenta (autorovi sdělená): dichotomie dobro/zlo je falešná, repo stejnou past už obešlo u `religion/religion-risk.md` („hodnotit nelze náboženství v abstraktu, jen konkrétní konfiguraci") — anonymita je spektrum (pseudonymita ≠ nedohledatelnost ≠ nesledovatelnost) a bilance se obrací podle toho, kdo ji drží proti komu. **Další krok:** čeká se na autorovu vstupní intuici, pak volba páteře, umístění (nová složka?) a spec.
5. **Záleží na tom, co děláme, když za tisíc let nic nezbude?** — rozbor hotový a commitnutý 2026-09-23 jako `docs/analyses/2026-09-23-nothing-remains.md` (bf9356d); poznámka zatím nezaložena. Jádro: skrytá premise „na něčem záleží, jen když to trvá" je to, co padá — Nagelova symetrie (1971, s. 716) a bezprahovost („jak dlouho stačí?") → Epikúros („bude nám jedno" nemá subjekt) → Agathón/EN VI.2 (minulost se nedá odestát; nezbude jméno, ne účinek) → přeživší forma: Scheffler (kolektivní posmrtný život; premise „nebude nikdo" by byla silnější než „nebudeme my") → Marcus Aurelius a Kazatel 1:11 jako důkaz, že premisy nezavazují k nihilismu. Autor reagoval „To je skvělé", o anglickou poznámku zatím nepožádal. **Další krok:** pokud autor chce poznámku, napsat ji do `meaning/` podle `TEMPLATE.md` (pracovní název „Does it matter what we do, if nothing of us will remain?", páteř z rozboru), ověřit Frankla („having been is the surest kind of being" — zatím jen citátové agregátory) a Nagela s. 716 v čitelném primárním zdroji, přidat verdikt do `README.md` a obou překladů.

## Zaparkováno

6. **Etika jaderného vydírání** — zaparkováno 2026-07-27 na branchi `nuclear-blackmail`. Jak obnovit a jak s autorem pracovat, popisuje sekce Parked work v `AGENTS.md`; tady jen to, co tam není. Na branchi jsou schválené konjektury A–G (Never yield / Tail dominates / No line / Counter-structure / Better red than dead / Taboo is the shield / Supreme emergency). Plán pokračuje Taskem 3, refutacemi proti A, B a E. Where it stands má předepsanou pětitestovou proceduru (salami/Kavka/endogeneity/umbrella/Jupiter) a revizní hák do ukrajinské poznámky při výsledku (ii)/(iii).

## Kandidáti z vláken

- epistemologie historických analogií
- jus in bello
- meta-poznámka o rodině asymetrických argumentů
- plná etika odstrašení
- svobodná vůle a odpovědnost (dovětek E determinismu na ni dopředně odkazuje; patří do `mind/`)
- šipka času a simulační hypotéza (sourozenci v `reality/`)
