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

## Pre vývojárov: ako si stiahnuť a otvoriť projekt

**Verzia Unity: 6000.3.29f1 (Unity 6.3 LTS).** Používajte presne túto verziu. S inou Unity ponúkne upgrade projektu a v gite vzniknú zbytočné zmeny.

### Prvé spustenie

1. Nainštaluj Git a Git LFS a raz na počítači spusti `git lfs install`. GitHub Desktop podporuje LFS automaticky.
2. Naklonuj repozitár. Bez LFS sa namiesto obrázkov a zvukov stiahnu len textové odkazy (LFS pointery).
3. Unity Hub → Installs → Install Editor → verzia **6000.3.29f1** (ak nie je v zozname, nájdeš ju v Archive). Moduly:
   - Web Build Support
   - Android Build Support + OpenJDK + Android SDK & NDK Tools
   - Visual Studio Community nie je povinné, stačí VS Code.
4. Unity Hub → Projects → Add → Add project from disk → vyber priečinok **`Unity/`** v repe, nie koreň repa.
5. Prvé otvorenie trvá niekoľko minút, Unity si vytvára priečinok `Library/`.
6. Editor kódu: Edit → Preferences → External Tools → External Script Editor → VS Code alebo Visual Studio. Pre VS Code nainštaluj rozšírenie **Unity** od Microsoftu.

### Ak Windows hlási blokované DLL (Smart App Control)

V Unity: Jobs → Burst → odškrtni **Enable Compilation**. Nastavenie je lokálne, každý si ho robí sám. Smart App Control nevypínajte.

### Pravidlá práce v projekte

- Všetky naše súbory patria do `Assets/_Stopa/`. `Assets/Settings/` a `Assets/TextMesh Pro/` sú zo šablóny, nemeňte ich bez dohody.
- Hlavná scéna je `Assets/_Stopa/Scenes/Main`.
- Súbory v `Assets/` presúvajte a premenúvajte **iba v Unity**, nie v Prieskumníkovi. Unity si ich pamätá cez súbory `.meta`.
- Každý súbor commitujte spolu s jeho `.meta`.
- Používateľské texty patria len do `Assets/_Stopa/Localization/sk.json` a `en.json`, nie do grafiky ani do kódu.
- Buildy ukladajte do `Unity/Builds/` (git ho ignoruje), nikdy do `Assets/`.
- Pred prácou vždy pull. Jednu scénu alebo prefab naraz upravuje len jeden človek, dohodnite sa na Discorde.
- Kód alebo obsah od AI: v správe commitu uveďte ID záznamu z `Docs/AI-Development-Log.md` (napr. `AI-012`).

### Nastavenia projektu (už nastavené, nemeniť bez dohody)

- Editor: Asset Serialization Mode **Force Text**, Version Control Mode **Visible Meta Files**
- Web: kompresia **Gzip**, **Decompression Fallback** zapnutý
- Android: minimálne **API 30 (Android 11)**, **IL2CPP**, **ARM64**, orientácia **na výšku**, package name `sk.stopa.app`

### Voliteľne: Unity Smart Merge

Menej konfliktov v scénach a prefaboch. Spusti raz v koreni repa (cestu uprav, ak máš Unity nainštalované inde):

```
git config merge.unityyamlmerge.name "Unity SmartMerge"
git config merge.unityyamlmerge.driver "'C:/Program Files/Unity/Hub/Editor/6000.3.29f1/Editor/Data/Tools/UnityYAMLMerge.exe' merge -p %O %B %A %A"
git config merge.unityyamlmerge.recursive binary
```