# Analyse SafeMarket Store

## Anforderungen

Für die Details bitte die [Anforderungsspezifikation](https://github.com/SafeMarket-WirVsVirus/orga/blob/master/anforderungsspezifikation.md) anschauen. Es gibt Anforderungen die manche Kompnenten nicht erfüllen müssen (z.B. Tutorial und Backend), dann schreibt einfach Nicht erfüllbar rein. Bei Teilweise, bitte kurz erläutern was geht und was nicht.

### Funktional

|ID|Anforderung|Erfüllt?|Notizen|
|:-|:-|:-|:-|
|001|Das System bietet die Funktion für den Einkauf einen Termin (Zeitpunkt + Dauer) zu reservieren. Zusätzlich zeigt es an, welche Geschäfte aktuell stark besucht sind.|Ja|Gesamt Slots <br> Time Slots für Reservierung <br> Können durch den Inhaber eingetragen werden.
|002|Das System plant Kapazitäten für Laufkunden bzw. technische nicht versierte Benutzer ein.|Teilweise| Kann errechnet werden aus Gesamt Slots - Time Slots für Reservierung = Slots für Laufkundschaft <br> Zähler für Doorman noch nicht implementiert|
|003|Das System berücksichtigt die knappe Zeit bestimmter Gruppen und ermöglicht diesen optimale Termine.|Nein||
|004|Das System ermöglicht es für Freunde und Verwandte Termine zu buchen. Außerdem kann per Telefon ein Termin vereinbart werden.|Nicht relevant||
|005|Das System erinnert einen Kunden an seinen Termin.| Nicht relevant||
|006|Das System bietet die Funktion, die Markt Eigenschaften (Kapazität/Termindauer..) zu konfigurieren / anpassen und nie zu viele Kunden in das Geschäft zu lassen.|Teilweise| Termin Dauer durch Store einstellbar <br> Zähler für Doorman noch nicht implementiert |
|007|Das System bietet (Inhabern) die Möglichkeit, Endkunden einen frei wählbaren Status zu präsentieren.|Nein||
|012|Das System bietet bei freien Kapazitäten Kunden aktiv Termine an.| Nicht relevant ||
|014|Das System kann die Authentizität von Geschäften durch manuellen Abgleich und/oder mit externen Daten bestimmen.|Teilweise| Läden können angelegt werden in Frankreich|
|009|Es können nur Läden angelegt/ verwaltet werden, wenn der Nutzer als Ladeninhaber bestätigt wurde.|Nein||
|013|Das System bietet die Möglichkeit eine prozentuale Einschätzung (“Ampel”) über die Auslastung abzugeben.|Nein||
|015|Das System zeigt in der App/Website teilnehmende Geschäfte an.|Nicht relevant||
|016|Das System informiert per Telefon über teilnehmende Geschäfte.|Nein||
|017|Das System bietet die Möglichkeit Termine zu verifizieren.|Teilweise| QR Code kann gescannt und geprüft werden , Liste der Geheimwörter fehlt! |
|018|Das System führt den Nutzer durch ein Tutorial und informiert über den Verhaltenskodex und Ablauf.|Nein||
|019|Das System präsentiert dem Inhaber eine Übersicht vergangener Daten.|Nein||
|020|Das System ermöglicht es einem Geschäft seine Mitarbeiter zu konfigurieren.|Nein||

### Nicht-funktional

Bitte eine kurze Aussage zu:

Eintragungen wurden aus dem Gedächtnis hinzugefügt, daher keine Gewehr auf Komplette Richtigkeit!

Effizienz/Performance:
vue.js leider kann ich hier keine aussage zu treffen

Kompatibilität(Schnittstellen zu anderen Systemen):
Gegeben

Benutzbarkeit(für Endnutzer):
Noch nicht vollständig

Zuverlässigkeit: nicht wirklich

Sicherheit: Keine

Wartbarkeit(Modularität/Dokumentation): Gut

Portabilität(Abhängigkeiten zu Frameworks, Betriebssystem, Programmiersprache): vue.js