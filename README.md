# STOPA

Edukačná hra o kybernetickej bezpečnosti pre 8. ročník ZŠ a gymnázia (inovovaný ŠVP).
Semestrálny tímový projekt z predmetu **Multimediálne systémy**.

| | |
|---|---|
| **Kanban (Trello)** | _doplniť odkaz na Trello tabuľu_ |
| **Hrať (WebGL)** | _doplniť odkaz na GitHub Pages_ |
| **Buildy (WebGL, APK)** | [Releases](../../releases) |
| **Unity verzia** | _doplniť, napr. 6000.0.xxf1 — všetci MUSIA mať rovnakú_ |
| **Platformy** | WebGL, Android (APK) |
| **Jazyky** | slovenčina, angličtina |

## Tím

| Rola | Meno | Zodpovedá za |
|---|---|---|
| Scrum Master / manažér | Zuzka | Trello, termíny, `Docs/`, odovzdanie |
| Programovanie | Matúš | `Unity/` – kód, scény, buildy, Releases |
| Grafika | Alex | `Grafika-zdroje/`, exporty do `Unity/Assets/_Stopa/Art/`, ADD |
| Testovanie | Adam | `Docs/testovanie/`, stĺpec Testing → Done |

## Štruktúra repozitára

```
.github/            šablóna pull requestu
Unity/              Unity projekt (otvárať cez Unity Hub → Add project from disk)
  Assets/_Stopa/    Scripts/ Scenes/ Prefabs/ Art/ Audio/ Localization/
Grafika-zdroje/     zdrojové súbory grafiky a zvuku (PSD, Krita, moodboard, storyboard)
Docs/               GDD, ADD, TDD, testovanie, overenie, zápisnice, odovzdanie
```

## Ako začať

1. Nainštaluj **Git LFS** (GitHub Desktop ho má v sebe) a **Unity Hub** s verziou Unity uvedenou vyššie.
2. Naklonuj repo cez **GitHub Desktop** (*File → Clone repository*).
3. Unity: *Unity Hub → Add → Add project from disk →* priečinok `Unity/`.
4. Pred prácou vždy **Fetch / Pull**, po práci **Commit + Push**.

> Grafiku a zvuk nahrávaj **iba cez GitHub Desktop**, nie cez web — inak sa súbory neuložia do LFS.

## Kanban (Trello)

`Backlog → To Do → In Progress → Testing → Done`

| Stĺpec | Kto presúva | Kedy |
|---|---|---|
| Backlog | ktokoľvek | nový nápad, požiadavka alebo bug |
| To Do | Zuzka | výber úloh do šprintu na týždennom stretnutí |
| In Progress | riešiteľ | priradí si kartu; **max. 2 karty naraz na človeka** |
| Testing | riešiteľ | po zmergovaní PR / nahratí do hry |
| Done | **iba Adam** | po overení v builde |

Každý pull request má v popise odkaz na Trello kartu a ku karte je pripojený cez GitHub Power-Up.

## Pravidlá práce

- `main` je vždy spustiteľný. Zmeny idú cez **pull request**.
- Vetva na každú úlohu: `sken-zariadenia`, `ikony-ui`, `fix-en-preklad`, `docs-gdd` — krátko žijúca (pár dní).
- **Jednu scénu upravuje naraz iba jeden človek** — kto ju drží, napíše to do Trello karty. Čo sa dá, rob v prefaboch.
- Commituj aj súbory `.meta`.
- Unity nastavenia (už v projekte): *Project Settings → Editor → Version Control: Visible Meta Files, Asset Serialization: Force Text*.

## Build a vydanie

Na konci šprintu: Matúš spraví build **WebGL** + **Android APK**, vytvorí **Release** `v0.x.0` so zoznamom zmien a WebGL nasadí na GitHub Pages.

- WebGL pre GitHub Pages: *Player Settings → Publishing Settings → Compression Format: Disabled* (alebo zapnúť *Decompression Fallback*).
- Buildy sa necommitujú do gitu — patria do Releases.

## Ochrana súkromia

Hra neodosiela žiadne údaje. Telemetria sa ukladá iba lokálne v zariadení ako anonymný export a výsledky vidí iba žiak.
