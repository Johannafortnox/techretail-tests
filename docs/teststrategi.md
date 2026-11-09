Johanna Söderström 2026-11-01


# Teststrategi för TechRetail AB

> Den här filen är en del av inlämningen. Du fyller på den under kursen – börja i lektion 1 och skriv klart i lektion 9.
> Skriv kort och konkret. Motivera dina val med TechRetails situation, inte med allmänna påståenden.

**Författare:**
**Senast uppdaterad:**

## 1. Nuläge och mognad

*Hur testar TechRetail AB i dag? Var ligger företaget i kursens mognadsmodell (Strategi och styrning, Verktyg och arkitektur, Kompetens och organisation, Process och CI/CD, Mätning och resultat), och vilken nivå siktar ni på?*
| Dimension | Nivå | Bevis och motivering | 

|---|---|---| 

| Strategi och styrning | | | 1, 2, Ingen gemensam teststrategi, personberoende. (9, Karins svit) 

| Verktyg och arkitektur | | | 4, 8, 9, Saknas gemensam teststrategi och verktyg. (3, tidigare försök) 

| Kompetens och organisation | | | 1, 3, 6, 7, 8, finns viss kompetens 

| Process och CI/CD | 1 | Inga tester körs när koden ändras. Regressionen görs för hand | 

| Mätning och resultat | | | 7, 8, 9: ingen följer upp resultat, finns krav från ledningen som vi inte vet om det följs upp, vet bara att Karins svit hittar fel 

 

Målnivå: 3. Störst kulturell risk: Den kulturfaktor som hotar mest och vårt förslag: _Tid och förväntningar__ Konkret förslag: Avsätt lite tid (med utvecklarna) i varje spring för att utveckla automation.

## 2. Vad automatiseras och vad inte

*Bedöm automationskandidater med kriterierna frekvens, stabilitet, risk, determinism, kostnad att underhålla och värde av snabb återkoppling. Klassa varje fall i Karins manuella regressionssvit (MT-01 – MT-25) som ersätts, kompletteras eller behålls manuellt, och motivera.*

| Testfall | Klass (ersätts / kompletteras / behålls manuellt) | Nivå | Motivering |
|---|---|---|---|
| MT-01 |3, 3, 3, 3, 3, 3 = 18 | | |
MT-03 3, 3, 3, 3, 3, 3 = 18 Nu 
MT-06 3, 3, 2, 1, 2, 3 = 14 Senare 
MT-08 3, 3, 3, 3, 3, 3 = 18
MT-11 3, 3, 3, 3, 3, 3 = 18 
MT-13 3, 3, 3, 1, 3, 3 = 16 
MT-14 3, 3 Köpflöde automatiseras, känslan testas manuellt 
MT-19 
MT-20 3
MT-22 

## 3. Testnivåer och verkty

MT-01 
GUI + API 
Verifiera kundnamn och ”Mina ordrar” i GUI. API kan man testa inloggning: användarnamn + lösenord. 

MT-04 
GUI + API 
Verifiera att skruvdragaren visas på hemsidan efter sökning fyllts i sökfältet. 

MT-08 
GUI 
Används ingen sökning utan sköts genom att manuellt trycka på hemsidan. 

MT-11 
API + Komponent 
Direktreglering sköts av komponent, kundvagnen kontrolleras av API. 

MT-13 
Komponent 
Direktreglering sköts av komponent 

MT-25 
GUI + API 
Produkt slut visas i GUI, API att det inte går att lägga till i kundvagn. 

Verktyg för GUI-tester: Playwright. Det avgörande kriteriet var väntan och stabilitet: Playwright väntar automatiskt på element, medan Selenium kräver egna väntningar. Felsökning vägde också tungt. Behöver vi stöd för fler webbläsare skulle vi välja Selenium.

Fall som testas i webbläsaren: MT-01 (inloggning), MT-04 (sökning), MT-08 (lägg i kundvagn) och MT-25 (slutsåld produkt), flera av dem kompletterade med API-tester. MT-11 och MT-13 testas på lägre nivå, eftersom reglerna sköts i komponenten.

Kvar för Karin: Test på riktig mobil, eftersom Playwright bara emulerar mobila enheter.


*Hur fördelar du testerna på testpyramidens nivåer komponent (enhet), API och GUI? Ge exempel ur ditt eget repo för varje nivå. Vilka verktyg använder du, och vad körs vid varje push respektive nattligt?*


## 4. AI-användning

*Hur använder du AI för att ta fram och förbättra tester? Hur granskar du resultatet med GRANSKA-kortet? Hänvisa till poster i `ai/AI-logg.md`.*

## 5. Icke-funktionella tester – prestanda och säkerhet

*Vilken prestandabudget gäller (till exempel p95 och felandel), och hur kontrollerar du den? Vilka säkerhetsrisker testar du, och med vilka verktyg?*

## 6. Hållbarhet – mätning före och efter

*Vilken resursbesparande åtgärd har du gjort (till exempel kortare körtid, färre CI-minuter, smartare testurval)? Vad visade mätningen före och efter? Vad kostade AI-användningen?*
