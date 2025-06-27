## 📊 Dataset and Preprocessing

We gebruiken drie datasets van de Wereldbank:

1. **Adult Mortality Rate (mannen)**  
   - Jaarlijkse sterftecijfers per 1.000 volwassen mannen  
   - [Link naar dataset](https://data360.worldbank.org/en/indicator/WB_HNP_SP_DYN_AMRT?recentYear=false&sex=M)

2. **Life Expectancy at Birth (male)**  
   - Levensverwachting van mannen bij geboorte per land en jaar  
   - [Link naar dataset](https://data360.worldbank.org/en/indicator/WB_WDI_SP_DYN_LE00_MA_IN)

3. **GDP per country (Current US$)**  
   - Jaarlijkse GDP per land  
   - [Link naar dataset](https://data.worldbank.org/indicator/NY.GDP.MKTP.CD?end=2023&start=2023&utm_source=chatgpt.com&view=map&year=1960)

Alle datasets zijn in `.csv` formaat en bevatten waarden van 1960 tot 2022 voor vrijwel alle landen.

---

### 🧾 Variabelenoverzicht

| Variabele              | Type      | Beschrijving                                 |
|------------------------|-----------|----------------------------------------------|
| `Country`              | Nominaal  | Land van observatie                          |
| `Year`                 | Interval  | Jaar van observatie (1960–2022)              |
| `Life Expectancy`      | Ratio     | Levensverwachting bij geboorte (mannen)      |
| `Adult Mortality`      | Ratio     | Sterfte per 1.000 volwassen mannen           |
| `GDP per capita (log)` | Ratio     | Logaritme van het BBP per hoofd              |

Deze variabelen vormen de ruggengraat van onze analyses. Ze bieden een rijk perspectief op gezondheid, ongelijkheid en economische ontwikkeling door de tijd heen.

---

### ⚙️ Hoe we met de data zijn omgegaan

Om beter te begrijpen hoe levensverwachting en sterftecijfers zich wereldwijd ontwikkelen, zijn we begonnen met het verzamelen van relevante gegevens van de Wereldbank. We maakten gebruik van drie datasets die samen een breed beeld geven van gezondheid en sociaaleconomische ontwikkeling bij mannen.

De ruwe datasets zijn omvangrijk en soms wat onoverzichtelijk – met jaren als kolommen en landen als rijen. Daarom hebben we ze eerst omgevormd naar een lang formaat, waarbij elke regel staat voor een specifieke combinatie van land en jaar. Zo konden we trends in de tijd veel beter volgen.

Vervolgens hebben we de datasets samengevoegd. Door 'land' en 'jaar' als gemeenschappelijke sleutels te gebruiken, ontstond één geïntegreerd databestand waarin we per land en jaar de levensverwachting, sterftecijfers en economische situatie naast elkaar kunnen analyseren.

Zoals vaak bij wereldwijde data, bleek niet elk land in elk jaar volledige informatie te hebben. Om te zorgen dat onze analyse representatief blijft, hebben we kritisch gekeken naar ontbrekende waarden. In sommige gevallen hebben we die weggelaten; in andere gevallen gebruikten we eenvoudige methodes, zoals interpolatie, om gaten op te vullen zonder de trends te vertekenen.

Tot slot hebben we de economische data (GDP) bewerkt met een log-transformatie. Dit maakt het makkelijker om landen eerlijk te vergelijken, aangezien de verschillen in bruto binnenlands product soms extreem groot zijn.

Met deze verwerkte dataset konden we aan de slag: visualisaties maken, trends blootleggen en zoeken naar verbanden. Want alleen met schone en goed gestructureerde data kunnen we een eerlijk verhaal vertellen over gezondheid, ongelijkheid en vooruitgang in de wereld.
