Supply Chain Risk Analysis

Projektübersicht

In diesem Projekt untersuche ich Lieferkettenrisiken und mögliche Zusammenhänge mit Lieferunterbrechungen. Ziel ist es, operative Muster zu erkennen und zu prüfen, wie einfache Regeln zur Risikoeinschätzung beitragen können.

Geschäftsfrage

Welche Faktoren stehen im Datensatz mit Lieferunterbrechungen und längeren Lieferzeiten in Zusammenhang?

Datensatz

Quelle: Kaggle – Global Supply Chain Risk and Logistics

Zeitraum der vorhandenen Daten: 2024–2025

Umfang: 5.000 Lieferungen

Zielvariable: Disruption_Occurred

Vorgehensweise

Daten verstehen und prüfen

Daten bereinigen

Explorative Datenanalyse

Risikoanalyse nach Wetter, geopolitischem Risiko und Zuverlässigkeit des Transportdienstleisters

Regelbasierte Risikoeinschätzung und Vergleich mit einer einfachen Baseline

Zentrale Ergebnisse

61,26 % der Lieferungen sind im Datensatz als unterbrochen gekennzeichnet.

Die Unterbrechungsrate steigt über die definierten geopolitischen Risikogruppen.

Bei Hurrikanen wurden im Datensatz alle Lieferungen als unterbrochen erfasst.

Die regelbasierte Risikoeinschätzung erreicht auf dem Testdatensatz eine Genauigkeit von 73,80 %.

Einschränkungen

Die Ergebnisse zeigen Zusammenhänge innerhalb dieses Datensatzes, aber keine Ursache-Wirkungs-Beziehungen. Die Regel wurde anhand zuvor untersuchter Datenmuster entwickelt. Die Ergebnisse sind daher ein erster Vergleich und keine unabhängige Prüfung für zukünftige Lieferungen.

Verwendete Werkzeuge

Python

pandas

Matplotlib

Jupyter Notebook

Visual Studio Code