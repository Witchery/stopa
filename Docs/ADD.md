# ADD – Art Design Document: STOPA

**Verzia:** 0.2 (návrh) · **Dátum:** 24. 11. 2026 · **Autor:** Alex

**STOPA-04** · návrh na piatok 27. 11. 2026 · 4 h. **STOPA-05** · exporty do nedele 6. 12. 2026 · 4 h.

Wireframe vychádza zo schváleného prototypového scenára **M08 – Kód od kamaráta** a jeho textov v SK/EN. Scenár odlišuje konverzáciu v chatovej appke od SMS na známom čísle. [Rozhodnutie o M08](AI-Development-Log.md#záznamy) · [texty SK](../Unity/Assets/_Stopa/Localization/sk.json) · [texty EN](../Unity/Assets/_Stopa/Localization/en.json)

## 1. Vizuálny štýl
Plochá 2D grafika, svetlý displej, tmavý rám a jednoduché geometrické ikony. Na domovskej ploche jemný motív prerušených kružníc. V chate čisté pozadie, aby vynikli správy a rozhodnutia. Chat má fialový podpis, SMS petrolejový. Kanál vždy označuje aj názov a ikona.

## 2. Moodboard a inšpirácie
<!-- obrázky z Grafika-zdroje/moodboard/ -->

## 3. Farebná paleta
| Názov | HEX | Použitie |
|---|---|---|
| Rám a hlavný text | `#19182B` | Rám, nadpisy, telo správ a popisy ikon |
| Vedľajší text | `#56536C` | Čas, podtitulok a metadáta |
| Papier | `#F5F3FA` | Domovská plocha, vonkajšie pozadie telefónu |
| Displej | `#FFFFFF` | Chat, SMS a biele symboly na tmavých ikonách |
| Prijatá správa | `#ECEAF2` | Ľavá bublina s hlavným textom |
| Odoslaná správa | `#E8E0FF` | Pravá bublina s hlavným textom |
| Chat a fokus | `#552CC9` | Ikona Bodkruhu, obrys fokusu na svetlých plochách |
| SMS | `#12685D` | Ikona a označenie kanála Správy |
| Výstraha | `#8D351C` na `#FFEEE3` | Výstražný text s ikonou v príslušnom stave scenára |

Kontrast navrhnutých párov: text na bielej **17,40 : 1**, vedľajší text na papieri **6,70 : 1**, text v bublinách **14,60 : 1** a **13,70 : 1**, biela na fialovej **8,11 : 1**, biela na petrolejovej **6,64 : 1**, výstražný text **6,99 : 1**. Pri voľbách rovnaká vizuálna váha. Pre hover jemná levanduľová výplň `#F5F3FA`, pre stlačenie `#E8E0FF`, pre fokus viditeľný fialový obrys.

## 4. Typografia
| Font / rez | Veľkosť / riadok | Použitie |
|---|---:|---|
| Inter SemiBold 600 | 64 / 76 | Názov obrazovky |
| Inter SemiBold 600 | 52 / 64 | Meno kontaktu |
| Inter Regular 400 | 48 / 64 | Text správy |
| Inter SemiBold 600 | 46 / 60 | Text rozhodnutí a overenia |
| Inter SemiBold 600 | 42 / 54 | Názvy appiek |
| Inter Regular 400 | 36 / 48 | Čas a podtitulok kanála |

Hodnoty sú jednotky návrhu pri 1080 × 1920. Pri zobrazení v šírke 360 px vychádza text správy na 16 px. Pre TextMesh Pro použiť statické rezy Regular a SemiBold. Pri importe zaregistrovať font v `Grafika-zdroje/LICENSES.md`, priložiť jeho licenciu a overiť glyfy oboch JSON-ov vrátane `ľ ĺ ŕ ô ť ď ň ä „ “ …`. [Oficiálny zdroj fontu Inter](https://github.com/rsms/inter) · [SIL Open Font License 1.1](https://github.com/rsms/inter/blob/master/LICENSE.txt)

## 5. Postavy
<!-- Pre každú: prvotný náčrt → finálny návrh, stavy/animácie -->

## 6. Prostredie a grafické prvky

### STOPA-05 – exporty do Unity

Editovateľné SVG sú v [`Grafika-zdroje/ui/`](../Grafika-zdroje/ui/). Každý asset má vlastný SVG s rovnakým názvom ako príslušné PNG. SVG možno otvoriť v Inkscape alebo importovať do Figmy. PNG a ich Unity `.meta` sú v [`Unity/Assets/_Stopa/Art/`](../Unity/Assets/_Stopa/Art/).

| PNG | Rozmer | Obsah |
|---|---:|---|
| `ui_phone_frame.png` | 1080 × 1920 | Tmavý rám, vonkajšie rohy R96, priehľadný otvor displeja podľa kót nižšie |
| `ui_phone_home_bg.png` | 992 × 1800 | Pozadie displeja s jemným kruhovým motívom, appky sa skladajú v Unity |
| `ui_icon_chat.png` | 256 × 256 | Fialová dlaždica, biely prerušený kruh s bodkou pri otvore |
| `ui_icon_sms.png` | 256 × 256 | Petrolejová dlaždica, biela obálka |
| `ui_icon_settings.png` | 256 × 256 | Svetlosivá dlaždica, tmavé ozubené koleso (tretia ikona) |
| `ui_bubble_incoming.png` | 144 × 144 | Prijatá správa, R32, bez chvostíka, 9-slice |
| `ui_bubble_outgoing.png` | 144 × 144 | Odoslaná správa, R32, bez chvostíka, 9-slice |

- PNG v sRGB. Rám, ikony a bubliny s alfa kanálom, pozadie môže byť nepriehľadné. Ikony majú rovnaký tvar dlaždice (R56) a približne 136 × 136 px plochu symbolu uprostred.
- Texty, čas, mená, čísla, odznaky a voľby vykresľuje Unity. Lokalizované texty číta zo `sk.json` a `en.json`.
- Import v `.meta` je `Sprite (2D and UI)`, `Sprite Mode: Single`, `Mesh Type: Full Rect`, `Pixels Per Unit: 100`. Bubliny majú `L/R/T/B: 36 px`. V uGUI nastaviť pri bublinách `Image Type: Sliced`, `Fill Center` zapnutý a `Pixels Per Unit Multiplier: 1`. Rám položiť navrch a vypnúť jeho `Raycast Target`, aby prepustil kliky k appkám. Pri zmene zobrazenej veľkosti škálovať celý telefón spolu s obsahom. [Unity uGUI Image](https://docs.unity3d.com/Packages/com.unity.ugui@2.0/manual/script-Image.html)
- Lokálne overené: rozmery, alfa kanál, prekrytie rámu a pozadia, 9-slice pri zmene šírky a výšky. Unity import a kontrola v builde zostávajú na integráciu. PNG pridať spolu s `.meta` cez GitHub Desktop (Git LFS).

## 7. UI

### STOPA-04 – názov chatovej appky

**Bodkruh**. Vymyslené meno z „bod“ a „kruh“ odkazuje na spojenie s vlastným okruhom ľudí. Rovnaký názov v SK aj EN. Vyhľadanie presného názvu 24. 11. 2026 nenašlo zhodnú chatovaciu appku. Po dohode tímu zmeniť `app.chat.name` aj výskyty v správach, oznámeniach a dialógoch. V SK použiť napr. „v Bodkruhu“ a „do Bodkruhu“.

### STOPA-04 – wireframe telefónu a chatu

**Návrh pre Matúša:** simulovaný telefón **1080 × 1920 na výšku (9 : 16), vrátane rámu**. Otvor displeja `x: 44, y: 60, š: 992, v: 1800, R64`. Súradnice v tabuľke merané od ľavého horného rohu telefónu. Na Androide telefón umiestniť do bezpečnej oblasti displeja. Vo WebGL vycentrovať celý telefón a zachovať pomer strán aj v širokom okne. Referenciu potvrdiť pred kreslením exportov. Aktuálny `CanvasScaler` v `Main.unity` používa `Constant Pixel Size` a má uloženú referenciu `800 × 600`. [Unity uGUI Canvas Scaler](https://docs.unity3d.com/Packages/com.unity.ugui@2.0/manual/script-CanvasScaler.html)

```text
DOMOV / výber appky                    CHAT / prvá voľba v M08
┌────────────────────────────────┐    ┌────────────────────────────────┐
│ 08:42                          │    │ 08:42                          │
│                                │    │ [Späť]  Dominik                │
│                                │    │         Bodkruh                │
│ [  ◌  ]   [  ✉  ]   [  ⚙  ]    │    ├────────────────────────────────┤
│ Bodkruh    Správy  Nastavenia  │    │ ╭───────────────────────╮      │
│                                │    │ │ Omylom poslaný kód    │      │
│                                │    │ ╰───────────────────────╯      │
│                                │    │ ╭───────────────────────╮      │
│        (motív pozadia)         │    │ │ Žiadosť o kód z SMS   │      │
│                                │    │ ╰───────────────────────╯      │
│                                │    │      posuvná konverzácia       │
│                                │    ├────────────────────────────────┤
│                                │    │ [ Over iným kanálom          ] │
│                                │    │ [ Poslať kód                 ] │
│                                │    │ [ Odmietnuť / odpoveď        ] │
└────────────────────────────────┘    └────────────────────────────────┘
```

| Časť | Kóty a správanie |
|---|---|
| Spoločný okraj obsahu | `x: 104`, šírka `872`. Stavový riadok `y: 112`, výška `64`. Čas je ilustračný údaj. |
| Domov – ikony | Dlaždice `216 × 216`, `y: 352`, stredy `x: 236 / 540 / 844`. Popis pod ikonou od `y: 592`. Klikateľná je celá plocha ikony aj popisu funkčných appiek. |
| Chat – hlavička | `y: 200`, výška `132`. Samostatný dotykový cieľ Späť, meno a názov kanála. |
| Chat – správy | Posuvná plocha od `y: 364` po 32 px nad voľbami. Bublina max. `704` px široká, vnútorný okraj `40` vodorovne a `28` zvisle. Prijaté vľavo, odoslané vpravo. |
| Chat – voľby | Stĺpec široký `872`, spodná hrana v `y: 1800`. Tlačidlá min. `144` vysoké, medzera `24`. Pri zalomení rastú nahor, konverzácia zostáva posuvná. |

- **Domov → Bodkruh → Dominik.** „Späť“ vedie na domovskú plochu telefónu. Ikona Správy odlišuje bežné SMS od Bodkruhu. Nastavenia sú návrh tretej ikony. Funkciu v M08 potvrdí tím.
- **Over iným kanálom → Správy → Dominik (mobil).** SMS pohľad využíva rovnaké rozloženie, vlastný názov a ikonu. Po návrate má byť jasné, že hráč je opäť v chate na Bodkruhu. Použiť už pripravené `tools.other_channel.*`, `contact.dominik.*` a `m08.v.*` podľa scenára.
- V ukážke sú skrátené výplňové texty. Pre Unity použiť `m08.n1.msg1`, `m08.n1.msg2`, `m08.n1.send` a `m08.n1.refuse`. Voľby sa menia podľa uzla scenára.

### Odovzdanie a kontrola

> Ahoj Matúš, sedí ti simulovaný telefón 1080 × 1920 na výšku vrátane rámu? Otvor displeja má 992 × 1800. Rátam s tým, že na Androide aj vo WebGL zachováme celý telefón v pomere 9 : 16. Potvrdíš mi to pred exportom? Ako tretiu ikonu navrhujem Nastavenia. Pasuje ti to do prototypu?

- **STOPA-04:** Matúš potvrdí referenciu a tím vyberie názov a tretiu appku. Alex odovzdá paletu, typografickú stupnicu a oba wireframy.
- **STOPA-05:** Alex odovzdá editovateľný zdroj a PNG. Matúš po importe skontroluje vrstvenie a bubliny, Adam v builde overí SK/EN, krátke aj dlhé správy a voľby, čitateľnosť a dostupnosť ovládania na portrétnom Androide aj širokom WebGL.

## 8. Audio
### Zvukové efekty (SFX)
### Hudba na pozadí

## 9. Storyboard
| Scenár | Hrubý náčrt scény |
|---|---|
| | |
