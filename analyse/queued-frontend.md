# Queued Frontend-Endkunde

## Anforderungen

Für die Details bitte die [Anforderungsspezifikation](https://github.com/SafeMarket-WirVsVirus/orga/blob/master/anforderungsspezifikation.md) anschauen. [Repo](https://github.com/Nuckal777/queued/tree/master/frontend)

### Funktional

|ID|Anforderung|Erfüllt?|
|:-|:-|:-|
|001|Das System bietet die Funktion für den Einkauf einen Termin (Zeitpunkt + Dauer) zu reservieren. Zusätzlich zeigt es an, welche Geschäfte aktuell stark besucht sind.|Ja|
|002|Das System plant Kapazitäten für Laufkunden bzw. technische nicht versierte Benutzer ein.|Nein|
|003|Das System berücksichtigt die knappe Zeit bestimmter Gruppen und ermöglicht diesen optimale Termine.|Nein|
|004|Das System ermöglicht es für Freunde und Verwandte Termine zu buchen. Außerdem kann per Telefon ein Termin vereinbart werden.|Nein|
|005|Das System erinnert einen Kunden an seinen Termin.|Nein|
|006|Das System bietet die Funktion, die Markt Eigenschaften (Kapazität/Termindauer..) zu konfigurieren / anpassen und nie zu viele Kunden in das Geschäft zu lassen.|Nicht erforderlich|
|007|Das System bietet (Inhabern) die Möglichkeit, Endkunden einen frei wählbaren Status zu präsentieren.|Ja (Status wird angezeigt)|
|012|Das System bietet bei freien Kapazitäten Kunden aktiv Termine an.|Nein|
|014|Das System kann die Authentizität von Geschäften durch manuellen Abgleich und/oder mit externen Daten bestimmen.|Nicht erforderlich|
|009|Es können nur Läden angelegt/ verwaltet werden, wenn der Nutzer als Ladeninhaber bestätigt wurde.|Nicht erforderlich|
|013|Das System bietet die Möglichkeit eine prozentuale Einschätzung (“Ampel”) über die Auslastung abzugeben.|Nicht erforderlich|
|015|Das System zeigt in der App/Website teilnehmende Geschäfte an.|Ja|
|016|Das System informiert per Telefon über teilnehmende Geschäfte.|Nein|
|017|Das System bietet die Möglichkeit Termine zu verifizieren.|Nein|
|018|Das System führt den Nutzer durch ein Tutorial und informiert über den Verhaltenskodex und Ablauf.|Nein|
|019|Das System präsentiert dem Inhaber eine Übersicht vergangener Daten.|Nicht-erforderlich|
|020|Das System ermöglicht es einem Geschäft seine Mitarbeiter zu konfigurieren.|Nicht erforderlich|

### Nicht-funktional

Bitte eine kurze Aussage zu:

Effizienz/Performance: Statische Website, die am Ende von einem Webserver ausgeliefert wird. Performance hängt also von Webserver ab. Website an sich ist flüssig.

Kompatibilität(Schnittstellen zu anderen Systemen): Abfragen an das Backend werden per HTTP mit JSON-Payloads realisiert.

Benutzbarkeit(für Endnutzer): Gegeben, derzeit gibt es aber auch nicht sonderlich viele Funktionen.

Zuverlässigkeit: Stürzt nicht ab, Nutzer wird auf unerwarteten Fehler hingewiesen.

Sicherheit: Statische Website => hängt also am Webserver. Abfragen können über HTTPS realisiert werden.

Wartbarkeit(Modularität/Dokumentation): Durch React-Kompoenenten sehr modular. Spährlich kommentiert. Kompoenenten sind allerdings recht klein und dadurch gut nachvollziehbar.

Portabilität(Abhängigkeiten zu Frameworks, Betriebssystem, Programmiersprache): React.js, JavaScript, Kompatibel mit Chrome und Firefox (wahrscheinlich auch Safari).