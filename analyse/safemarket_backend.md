# Ist-Zustand SafeMarket-Backend

## Anforderungen

Für die Details bitte die [Anforderungsspezifikation](https://github.com/SafeMarket-WirVsVirus/orga/blob/master/anforderungsspezifikation.md) anschauen. Es gibt Anforderungen die manche Kompnenten nicht erfüllen müssen (z.B. Tutorial und Backend), dann schreibt einfach Nicht erfüllbar rein. Bei Teilweise, bitte kurz erläutern was geht und was nicht.

### Funktional

|ID|Anforderung|Erfüllt?|Notizen|
|:-|:-|:-|:-|
|001|Das System bietet die Funktion für den Einkauf einen Termin (Zeitpunkt + Dauer) zu reservieren. Zusätzlich zeigt es an, welche Geschäfte aktuell stark besucht sind.|Ja|
|002|Das System plant Kapazitäten für Laufkunden bzw. technische nicht versierte Benutzer ein.|Nein|Es wäre möglich, wenn man einen solchen Endpunkt bereitstellen würde (Gesamt - Slots = Laufkundschaft)
|003|Das System berücksichtigt die knappe Zeit bestimmter Gruppen und ermöglicht diesen optimale Termine.|Nein|
|004|Das System ermöglicht es für Freunde und Verwandte Termine zu buchen. Außerdem kann per Telefon ein Termin vereinbart werden.|Teilweise|:white_check_mark: Verwendung von Codewörtern, die weitergegeben werden können. :x: Keine Telefon-Anbindung.|
|005|~~Das System erinnert einen Kunden an seinen Termin.~~|Nicht erfüllbar|Ist Aufgabe des FE|
|006|Das System bietet die Funktion, die Markt Eigenschaften (Kapazität/Termindauer..) zu konfigurieren / anpassen und nie zu viele Kunden in das Geschäft zu lassen.|Ja|:white_check_mark: Kapazität, Slot-Size und -Dauer (Unterschied?!) können konfiguriert werden.|
|007|Das System bietet (Inhabern) die Möglichkeit, Endkunden einen frei wählbaren Status zu präsentieren.|Ja|
|012|Das System bietet bei freien Kapazitäten Kunden aktiv Termine an.|Nein|Zu klären ist, ob das BE Benachrichtigung senden soll oder das FE pollt
|014|Das System kann die Authentizität von Geschäften durch manuellen Abgleich und/oder mit externen Daten bestimmen.|Nein|Zu klären
|009|Es können nur Läden angelegt/ verwaltet werden, wenn der Nutzer als Ladeninhaber bestätigt wurde.|Nein|Jeder kann verwalten
|013|Das System bietet die Möglichkeit eine prozentuale Einschätzung (“Ampel”) über die Auslastung abzugeben.|Ja|siehe 007
|015|Das System zeigt in der App/Website teilnehmende Geschäfte an.|Ja|
|016|Das System informiert per Telefon über teilnehmende Geschäfte.|Nein|
|017|Das System bietet die Möglichkeit Termine zu verifizieren.|Ja|Mit manuellem Codeabgleich. 
|018|~~Das System führt den Nutzer durch ein Tutorial und informiert über den Verhaltenskodex und Ablauf.~~|Nicht erfüllbar|
|019|Das System präsentiert dem Inhaber eine Übersicht vergangener Daten.|Nein| Es gibt noch keinen Endpunkt, ob ein Termin genutzt wurde.
|020|Das System ermöglicht es einem Geschäft seine Mitarbeiter zu konfigurieren.|Nein|Gibt es noch nicht in der Datenstruktur. Fehlender FK User<->Location

### Nicht-funktional

Bitte eine kurze Aussage zu:

Effizienz/Performance:
Aktuell Frontfacing Kestrel -> gute Performance.

Kompatibilität (Schnittstellen zu anderen Systemen):
Gegeben (ASPNetCore3)

Benutzbarkeit (für Endnutzer): Nicht erfüllbar
NA

Zuverlässigkeit:
Hoch

Sicherheit:
Hoch, wenn man richtig programmiert

Wartbarkeit (Modularität/Dokumentation):
Modularität gegeben, da jeder Controller eine Klasse und jeder Request eine Funktion

Portabilität (Abhängigkeiten zu Frameworks, Betriebssystem, Programmiersprache):
Abhängigkeit zu .NET-Core. Wird betriebssystemunabhängig Supported.