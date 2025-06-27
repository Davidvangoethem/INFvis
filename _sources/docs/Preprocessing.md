# Dataset and Preprocessing

Voor dit project hebben we drie datasets van de Wereldbank gebruikt:

1. **Adult Mortality Rate (mannen)**  
   Jaarlijkse sterfte per 1.000 volwassen mannen  
   [Bekijk dataset](https://data360.worldbank.org/en/indicator/WB_HNP_SP_DYN_AMRT?recentYear=false&sex=M)

2. **Life Expectancy at Birth (male)**  
   Levensverwachting van mannen bij geboorte  
   [Bekijk dataset](https://data360.worldbank.org/en/indicator/WB_WDI_SP_DYN_LE00_MA_IN)

3. **GDP per capita (Current US$)**  
   Bruto binnenlands product per hoofd per land per jaar  
   [Bekijk dataset](https://data.worldbank.org/indicator/NY.GDP.MKTP.CD?end=2023&start=2023&utm_source=chatgpt.com&view=map&year=1960)

Alle datasets beslaan de periode 1960–2022 en zijn in `.csv`-formaat.

### Variabelenoverzicht

| Variabele             | Type     | Beschrijving                          |
|-----------------------|----------|---------------------------------------|
| `Country`             | Nominaal | Land van observatie                   |
| `Year`                | Interval | Jaar van observatie (1960–2022)       |
| `Life Expectancy`     | Ratio    | Levensverwachting bij geboorte        |
| `Adult Mortality`     | Ratio    | Sterfte per 1.000 volwassen mannen    |
| `GDP per capita (log)`| Ratio    | Log van het BBP per hoofd             |

### Preprocessing

De ruwe datasets zijn getransformeerd naar long format, waarbij elke rij één land-jaar combinatie beschrijft. Zo konden we trends in de tijd eenvoudiger visualiseren.

Na conversie hebben we de datasets samengevoegd op `land` en `jaar`, zodat per observatie de drie indicatoren beschikbaar waren. Ontbrekende waarden zijn kritisch beoordeeld: in sommige gevallen verwijderd, in andere gevallen ingevuld via eenvoudige interpolatie.

Omdat GDP-waarden sterk uiteenlopen tussen landen, hebben we een log-transformatie toegepast. Dit maakte vergelijkingen eerlijker en visuele patronen duidelijker.

Deze opgeschoonde dataset vormt de basis voor onze visualisaties en analyses.
