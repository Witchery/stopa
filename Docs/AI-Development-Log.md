# STOPA – evidencia využitia AI

Tento súbor dokladá, ako tím pri vývoji používal AI: čo AI navrhla, čo tím prijal, upravil alebo odmietol a ako sa správnosť overila. Návrh AI nie je správny len preto, že ho vytvorila AI; za výsledok zodpovedá tím.

## Pravidlá

- Jeden riadok = jedna významná práca s AI (kód, texty, grafika, testy, plánovanie). Drobné otázky sa nezapisujú.
- Každý člen zapisuje svoje použitie AI sám, najneskôr do konca týždňa.
- Commit s kódom alebo obsahom od AI má v správe ID záznamu, napr. `AI-012`.
- Pri kóde sa uvádza, kto ho preveril a akým testom. Bez testu je výsledok „neoverené“.
- Odmietnuté návrhy sa zapisujú tiež, aj s dôvodom.
- Plné zadanie (prompt) sa uloží ako odkaz na konverzáciu alebo ako príloha v `Docs/`; v tabuľke je len skratka.

## Záznamy

| ID | Dátum | Člen | Nástroj | Zadanie (skrátene) | Výstup AI | Prijaté / upravené / odmietnuté | Ako overené | Výsledok |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| AI-001 | 22. 11. 2026 | Zuzka | Claude (claude.ai, projekt STOPA) | Analýza projektových dokumentov: požiadavky MoSCoW, riziká, prototyp, architektúra, harmonogram, prvé úlohy | Dokument „STOPA – Úvodná analýza a plán na schválenie“ | Prijaté: prototyp na M08, opatrenia na kapacitu programátora a zúženie R1 – R5, doplnenie pravidiel kyberindexu, definícia exportu telemetrie. Upravené: verzia Unity 6.3 LTS, ADD = Art Design Document. Odmietnuté: harmonogram na Whiteboard (nepotrebný popri Trelle). | Kontrola PM proti MoSCoW tabuľke a dokumentu kyberindexu; údaj NCSI overený na ncsi.ega.ee | Schválené PM 22. 11. 2026 |
| AI-002 | 22. – 23. 11. 2026 | Zuzka | Claude (claude.ai, projekt STOPA) | STOPA-01: postup inštalácie Unity a založenia projektu v repozitári | Postup krok za krokom (verzia, moduly, umiestnenie projektu, kontrola .gitignore a LFS) | Prijaté: Unity 6.3 LTS (6000.3.29f1), šablóna Universal 2D, VS Code namiesto Visual Studia. Odmietnuté: Unity 6.6, ktorú Hub ponúkol ako predvolenú; Unity Version Control a GitHub provider v Hube; vypnutie Smart App Control | `git status` po vytvorení projektu: žiadne Library/, Temp/, Logs/ | OK, prvý commit projektu |
| AI-003 | 22. 11. 2026 | Zuzka | Claude (claude.ai, projekt STOPA) | STOPA-09: texty scenára M08 v SK a EN, karta „Ako sa chrániť“, dôkazy a tip pre ukazovateľ 2.1 | `m08-sk.json` a `m08-en.json`, 50 kľúčov | Prijaté na kontrolu tímu. Vynechaný odkaz bezpecnenanete.eset.com (nepodarilo sa ho overiť) | Kontrola platnosti JSON a zhody kľúčov SK/EN skriptom; Linka detskej istoty 116 111 overená vo verejných zdrojoch | Čaká na kontrolu tímu do 26. 11. |

## Súhrn (doplní Zuzka na konci projektu)

Počet záznamov podľa člena tímu a typu práce (kód, texty, grafika, testy, plánovanie).
