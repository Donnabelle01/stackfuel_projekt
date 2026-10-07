# Lieferkettenrisiken und Lieferunterbrechungen

In diesem Projekt untersuche ich Lieferkettenrisiken und mögliche Zusammenhänge mit Lieferunterbrechungen. Ziel ist es, operative Muster zu erkennen und zu prüfen, wie einfache Regeln und statistische Modelle zur Risikoeinschätzung beitragen können.

## Forschungsfrage

Welche Faktoren stehen im Datensatz mit Lieferunterbrechungen und längeren Lieferzeiten in Zusammenhang?

## Datengrundlage

- **Quelle:** Kaggle – Global Supply Chain Risk and Logistics
- **Zeitraum:** 2024–2025
- **Umfang:** 5.000 Lieferungen
- **Variablen:** 14
- **Zielvariable:** `Disruption_Occurred`

Die Daten enthalten unter anderem Informationen zu Wetterbedingungen, geopolitischem Risiko, Transportart, Zuverlässigkeit des Transportdienstleisters, Lieferzeit, Entfernung und Kraftstoffpreisindex.

## Vorgehensweise

Das Projekt besteht aus fünf Analyse-Schritten:

1. **Daten verstehen und prüfen**
2. **Daten bereinigen**
3. **Explorative Datenanalyse**
4. **Risikoanalyse**
5. **Regelbasierte Risikoeinschätzung und Logistic Regression**

Für die Logistic Regression wird ein zeitbasierter Ansatz verwendet:

- **2024:** Entwicklung und Training
- **2025:** zeitlicher Test

Die regelbasierte Methode wird anschließend ebenfalls auf die Lieferungen des Jahres 2025 angewendet.

## Zentrale Ergebnisse

### Lieferunterbrechungen

61,26 % der Lieferungen sind im Datensatz als unterbrochen gekennzeichnet.

Unterbrochene Lieferungen haben außerdem eine höhere mediane Lieferzeit:

- **Keine Unterbrechung:** 6,24 Tage
- **Unterbrechung:** 10,69 Tage

### Geopolitisches Risiko

Die beobachtete Unterbrechungsrate steigt über die definierten geopolitischen Risikogruppen:

- **Niedrig:** 47,2 %
- **Mittel:** 62,4 %
- **Hoch:** 73,1 %

Die Grenze von 6,67 entspricht dabei der zuvor definierten Grenze für die Gruppe mit hohem geopolitischem Risiko.

### Wetterbedingungen

Bei extremen Wetterbedingungen wurden besonders hohe Unterbrechungsraten beobachtet.

Bei Hurrikanen wurden in diesem Datensatz sogar alle Lieferungen als unterbrochen erfasst.

## Regelbasiertes Frühwarnsystem

Für ein einfaches Frühwarnsystem wurde folgende Regel verwendet:

- Geopolitisches Risiko **≥ 6,67**
- **ODER** Wetterbedingung = Sturm / Hurrikan

Die Regel wurde anschließend auf die Lieferungen des Jahres 2025 angewendet.

### Ergebnisse im Testjahr 2025

- **Accuracy:** 73,71 %
- **Precision:** 77,93 %
- **Recall:** 78,99 %
- **F1-Score:** 78,45 %

Die regelbasierte Methode verbessert die Accuracy gegenüber der Baseline um **13,12 Prozentpunkte**.

Das Frühwarnsystem soll potenziell riskante Lieferungen erkennen und für eine genauere Prüfung priorisieren. Es ist nicht als automatische Entscheidungsregel gedacht.

## Logistic Regression

Zusätzlich wurde eine Logistic Regression als statistisches Modell verwendet.

Das Modell berücksichtigt mehrere Einflussfaktoren gleichzeitig, darunter:

- Entfernung
- Gewicht
- Kraftstoffpreisindex
- geopolitisches Risiko
- Zuverlässigkeit des Transportdienstleisters
- extreme Wetterbedingungen
- Transportart

### Ergebnisse im Testjahr 2025

- **Accuracy:** 74,58 %
- **Precision:** 78,02 %
- **Recall:** 80,80 %
- **F1-Score:** 79,39 %

Die Logistic Regression erzielt damit die beste Performance. Der Unterschied zur regelbasierten Methode ist jedoch relativ klein.

Die Logistic Regression zeigt besonders deutliche statistische Zusammenhänge für:

- extreme Wetterbedingungen
- geopolitisches Risiko
- Zuverlässigkeit des Transportdienstleisters

Die Ergebnisse beschreiben Zusammenhänge in den vorliegenden Daten und beweisen keine kausalen Beziehungen.

## Empfehlungen

- Lieferungen mit hohem geopolitischem Risiko frühzeitig überwachen.
- Wetterbedingungen bei der Planung und Überwachung berücksichtigen.
- Die Zuverlässigkeit von Transportdienstleistern bei der Auswahl und Planung berücksichtigen.
- Besonders riskante Kombinationen von Faktoren genauer prüfen.
- Regelbasierte Analyse und statistische Modelle als Unterstützung für die Priorisierung verwenden und nicht als automatische Entscheidung.

## Einschränkungen

Die Ergebnisse zeigen Zusammenhänge innerhalb dieses Datensatzes, aber keine Ursache-Wirkungs-Beziehungen.

Die Regel basiert auf Mustern aus der vorherigen Risikoanalyse. Die Auswertung für 2025 ist daher eine zeitliche Validierung und keine vollständig unabhängige Prüfung der Regelentwicklung.

Die Ergebnisse gelten für den vorliegenden Datensatz und können nicht automatisch auf zukünftige Lieferungen übertragen werden.

## Verwendete Werkzeuge

- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- statsmodels
- Jupyter Notebook
- Visual Studio Code

## Projektstruktur

```text
supply_chain/
│
├── Data/
│
├── Notebooks/
│   ├── 01_Data_Understanding.ipynb
│   ├── 02_Data_Cleaning.ipynb
│   ├── 03_Exploratory_Analysis.ipynb
│   ├── 04_Risk_Analysis.ipynb
│   └── 05_Rule_Based_Risk_Model.ipynb
│
├── Visuals/
│
└── README.md
