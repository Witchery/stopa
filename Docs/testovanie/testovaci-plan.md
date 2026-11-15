# Testovací plán

**Tester:** Adam

## Rozsah
Platformy: WebGL (prehliadače: ), Android (zariadenia: ) · Jazyky: SK, EN

## Techniky
- **Black-box** – testovanie podľa testovacích prípadov bez znalosti kódu
- **Grey-box** – s čiastočnou znalosťou logiky (napr. telemetria, uloženie dát)
- **White-box** – kontrola kódu s Matúšom pri kritických častiach
- **Family & Friends** – hranie nezúčastnenými ľuďmi, pozorovanie

## Kedy sa testuje
- Priebežne: každá Trello karta v stĺpci **Testing** → po overení do **Done**
- Na konci šprintu: regresný test na novom Release → [protokol](protokoly/)

## Závažnosť chýb
| Úroveň | Význam |
|---|---|
| Kritická | pád, nedá sa pokračovať |
| Vysoká | funkcia nefunguje, existuje obchádzka |
| Stredná | chyba vzhľadu / textu, ruší hranie |
| Nízka | kozmetika |
