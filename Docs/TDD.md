# TDD – Technical Design Document: STOPA

**Verzia:** 0.1 · **Dátum:** · **Autor:** Matúš

## 1. Vývojové prostredie
- Engine: Unity <!-- presná verzia -->
- Render pipeline / šablóna:
- IDE:
- Verzionovanie: Git + Git LFS, GitHub

## 2. Cieľové platformy
| Platforma | Min. požiadavky | Poznámky |
|---|---|---|
| WebGL | | Compression: Disabled / Decompression Fallback (GitHub Pages) |
| Android | API level: | sken zariadenia bez povolení |

## 3. Architektúra
<!-- scény, hlavné skripty/manažéri, tok dát; ideálne diagram -->

## 4. Použité balíčky a knižnice
| Balíček | Verzia | Na čo |
|---|---|---|
| | | |

## 5. Lokalizácia (SK/EN)
Texty v JSON: `Assets/_Stopa/Localization/sk.json`, `en.json`
<!-- formát kľúčov, prepínanie jazyka -->

## 6. Dáta a telemetria
<!-- JSON štruktúra, kde sa ukladá, ako sa exportuje; nič sa neodosiela -->

## 7. Optimalizácia

## 8. Build a nasadenie
1. WebGL → GitHub Pages
2. Android → APK v GitHub Releases

## 9. Známe obmedzenia
