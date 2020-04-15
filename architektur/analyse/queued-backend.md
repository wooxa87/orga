# Queued-Backend

## Anforderungen

Für die Details bitte die [Anforderungsspezifikation](https://github.com/SafeMarket-WirVsVirus/orga/blob/master/anforderungsspezifikation.md) anschauen. [Repo](https://github.com/Nuckal777/queued/tree/master/backend)

### Funktional

|ID|Anforderung|Erfüllt?|
|:-|:-|:-|
|001|Das System bietet die Funktion für den Einkauf einen Termin (Zeitpunkt + Dauer) zu reservieren. Zusätzlich zeigt es an, welche Geschäfte aktuell stark besucht sind.|Ja|
|002|Das System plant Kapazitäten für Laufkunden bzw. technische nicht versierte Benutzer ein.|Nein|
|003|Das System berücksichtigt die knappe Zeit bestimmter Gruppen und ermöglicht diesen optimale Termine.|Nein|
|004|Das System ermöglicht es für Freunde und Verwandte Termine zu buchen. Außerdem kann per Telefon ein Termin vereinbart werden.|Nein|
|005|Das System erinnert einen Kunden an seinen Termin.|Nein|
|006|Das System bietet die Funktion, die Markt Eigenschaften (Kapazität/Termindauer..) zu konfigurieren / anpassen und nie zu viele Kunden in das Geschäft zu lassen.|Nein|
|007|Das System bietet (Inhabern) die Möglichkeit, Endkunden einen frei wählbaren Status zu präsentieren.|Teilweise (Status wird ausgeliefert, kann aber nicht festgelegt werden)|
|012|Das System bietet bei freien Kapazitäten Kunden aktiv Termine an.|Nein|
|014|Das System kann die Authentizität von Geschäften durch manuellen Abgleich und/oder mit externen Daten bestimmen.|Nein|
|009|Es können nur Läden angelegt/ verwaltet werden, wenn der Nutzer als Ladeninhaber bestätigt wurde.|Nein|
|013|Das System bietet die Möglichkeit eine prozentuale Einschätzung (“Ampel”) über die Auslastung abzugeben.|Nein|
|015|Das System zeigt in der App/Website teilnehmende Geschäfte an.|Ja|
|016|Das System informiert per Telefon über teilnehmende Geschäfte.|Nein|
|017|Das System bietet die Möglichkeit Termine zu verifizieren.|Nein|
|018|Das System führt den Nutzer durch ein Tutorial und informiert über den Verhaltenskodex und Ablauf.|Nicht erforderlich|
|019|Das System präsentiert dem Inhaber eine Übersicht vergangener Daten.|Nein|
|020|Das System ermöglicht es einem Geschäft seine Mitarbeiter zu konfigurieren.|Nein|

### Nicht-funktional

Bitte eine kurze Aussage zu:

Effizienz/Performance: Python als interpretierte Programmiersprache ist nicht so schnell, wie statisch kompilierte

Kompatibilität(Schnittstellen zu anderen Systemen): Abfragen können per HTTP mit JSON-Payloads durchgeführt werden. ALs Datenbank können alle von SQLalchemy unterstüzten eingesetzt werden (SQLite, Postgresql, MySQL, Oracle, MS-SQL, Firebird, Sybase).

Benutzbarkeit(für Endnutzer): Derzeit 4 API Endpunkte

Zuverlässigkeit: Stabil

Sicherheit: Kann HTTPS nutzen, keine Authentifizierung, Sicherheit der Daten hängt an Datenbank

Wartbarkeit(Modularität/Dokumentation): Einige Kommentare, rund 200 Zeilen, leicht verständlich

Portabilität(Abhängigkeiten zu Frameworks, Betriebssystem, Programmiersprache): Flask, SQLalchemy, Python, Windows, Linux, MacOS