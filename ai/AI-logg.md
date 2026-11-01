# AI-logg

Här skriver du ner varje gång du använder en AI-assistent i kursen. Loggen är en del av inlämningen och visar att du granskar det AI:n ger dig.

Granska varje gång med GRANSKA-kortet:

| Steg | Fråga |
|---|---|
| **Bad** | Vad bad du om? Klistra in prompten.
| **Fick** | Vad gav AI:n dig? Kort sammanfattning eller länk till commit.
| **Kör** | Gick koden att köra? Vad blev resultatet? 
| **Bryt** | Ändrade du koden eller appen så att testet borde bli rött? Blev det rött av rätt anledning? |
| **Data** | Skickade du någon persondata eller hemlighet? (Svaret ska vara nej.) |
| **Kostnad** | Ungefär hur många tokens, hur lång tid, vilken kostnad? |
| **Beslut** | Accepterade, ändrade eller kastade du resultatet – och varför? |

Tumregel: lägg mer tid på att granska än på att generera.

---

## Mall – kopiera för varje ny post

### ÅÅÅÅ-MM-DD · Lektion X · Verktyg: (till exempel Copilot Free)

- **Bad:**
- **Fick:**
- **Kör:**
- **Bryt:**
- **Data:**
- **Kostnad:**
- **Beslut:**

---

## Mina poster 

### 2026-11-01 · Lektion 1 · Verktyg: Copilot Free

| **Bad** | Vad bad du om? Klistra in prompten. |Föreslå ett pytest-test för apply_discount i src/techretail/pricing.py som prövar ett gränsvärde jag inte redan har. Följ AAA. Ändra inga filer.
| **Fick** | Vad gav AI:n dig? Kort sammanfattning eller länk till commit. |Ett nytt gränsvärde är exakt en halv öre: 0,15 kr med 50 % rabatt ger 0,075 kr, som enligt reglerna ska avrundas uppåt till 0,08 kr i pricing.py.
| **Kör** | Gick koden att köra? Vad blev resultatet? Den passerades och blev grönt|tests/unit/test_pricing.py::test_halvt_ore_avrundas_uppat PASSED.
| **Bryt** | Ändrade du koden eller appen så att testet borde bli rött? Blev det rött av rätt anledning? | Jag ändrade förväntat värde från 0.08 till 0.07. Testet blev rött eftersom koden gav 0.08, alltså av rätt anledning.
| **Data** | Skickade du någon persondata eller hemlighet? (Svaret ska vara nej.) |Nej, jag skickade bara kod från repot.
| **Kostnad** | Ungefär hur många tokens, hur lång tid, vilken kostnad? | En prompt, cirka 10 minuter, gratis med Copilot Free.
| **Beslut** | Accepterade, ändrade eller kastade du resultatet – och varför? |Accepterade testet. Jag kontrollerade i pricing.py att halva ören ska avrundas uppåt.

---

## Summering (fylls i före inlämningen)

| | Antal / värde |
|---|---|
| Antal AI-poster | |
| Accepterade utan ändring | |
| Ändrade | |
| Kastade | |
| Ungefärlig total kostnad (tokens eller kronor) | |
| Vad lärde du dig om att granska AI-genererade tester? | |
