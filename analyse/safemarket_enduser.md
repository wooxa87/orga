# Analyse SafeMarket Enduser

## Anforderungen

Für die Details bitte die [Anforderungsspezifikation](https://github.com/SafeMarket-WirVsVirus/orga/blob/master/anforderungsspezifikation.md) anschauen. Es gibt Anforderungen die manche Kompnenten nicht erfüllen müssen (z.B. Tutorial und Backend), dann schreibt einfach Nicht erfüllbar rein. Bei Teilweise, bitte kurz erläutern was geht und was nicht.

### Funktional

|ID|Anforderung|Erfüllt?|Notizen|
|:-|:-|:-|:-|
|001|Das System bietet die Funktion für den Einkauf einen Termin (Zeitpunkt + Dauer) zu reservieren. Zusätzlich zeigt es an, welche Geschäfte aktuell stark besucht sind.|Teilweise|:white_check_mark: Termin buchen, Anzeige von Auslastung aktuell und zukünftig<br>:x: kein Telefonsupport, kein Termin-Absagen, kein Multi-Geräte-Support, keine Termin-Buchungsrestriktionen|
|002|Das System plant Kapazitäten für Laufkunden bzw. technische nicht versierte Benutzer ein.|Ja|:white_check_mark: Termin für andere buchen|
|003|Das System berücksichtigt die knappe Zeit bestimmter Gruppen und ermöglicht diesen optimale Termine.|Nein||
|004|Das System ermöglicht es für Freunde und Verwandte Termine zu buchen. Außerdem kann per Telefon ein Termin vereinbart werden.|Teilweise|:white_check_mark: Termin für andere buchen<br>:x: Telefonsupport|
|005|Das System erinnert einen Kunden an seinen Termin.|Ja|:white_check_mark: Notification 30 min vor Beginn der Reservierung, muss aktiviert werden|
|006|Das System bietet die Funktion, die Markt Eigenschaften (Kapazität/Termindauer..) zu konfigurieren / anpassen und nie zu viele Kunden in das Geschäft zu lassen.|-||
|007|Das System bietet (Inhabern) die Möglichkeit, Endkunden einen frei wählbaren Status zu präsentieren.|Nein||
|012|Das System bietet bei freien Kapazitäten Kunden aktiv Termine an.|Nein||
|014|Das System kann die Authentizität von Geschäften durch manuellen Abgleich und/oder mit externen Daten bestimmen.|-|Backend|
|009|Es können nur Läden angelegt/ verwaltet werden, wenn der Nutzer als Ladeninhaber bestätigt wurde.|-|Backend|
|013|Das System bietet die Möglichkeit eine prozentuale Einschätzung (“Ampel”) über die Auslastung abzugeben.|Ja|:white_check_mark: App zeigt Ampel an|
|015|Das System zeigt in der App/Website teilnehmende Geschäfte an.|Teilweise|:white_check_mark: Native Apps<br>:x: Webseite|
|016|Das System informiert per Telefon über teilnehmende Geschäfte.|Nein||
|017|Das System bietet die Möglichkeit Termine zu verifizieren.|Ja|:white_check_mark: QR-Code<br>:x: Code Words zwar implementiert aber werden noch nicht vom Backend gesendet|
|018|Das System führt den Nutzer durch ein Tutorial und informiert über den Verhaltenskodex und Ablauf.|Teilweise|Tutorial aktuell in development|
|019|Das System präsentiert dem Inhaber eine Übersicht vergangener Daten.|-|Backoffice|
|020|Das System ermöglicht es einem Geschäft seine Mitarbeiter zu konfigurieren.|-||

### Nicht-funktional

Bitte eine kurze Aussage zu:

Effizienz/Performance: 
- Bisher stabil auf iOS und Android

Kompatibilität(Schnittstellen zu anderen Systemen):
?

Benutzbarkeit (für Endnutzer):
- Nutzertests aktuell laufend

Zuverlässigkeit:
- In unseren Tests bisher gut

Sicherheit:
- Speicherung der Daten in NSUserDefaults/SharedPreferences (nur Zugriff durch unsere App)
- Sensitive Daten, die verarbeitet werden: letzte Nutzerposition, Device-ID

Wartbarkeit (Modularität/Dokumentation):
- geringe Dokumentation
- Code separiert in UI- und Repository-Layer
- Unit-Tests für die wichtigsten Funktionen, keine Integration-Tests

Portabilität (Abhängigkeiten zu Frameworks, Betriebssystem, Programmiersprache):
- gering, stark abhängig von Flutter / Dart
- Web geht prinzipiell, aber:
  - nur im letzten flutter-master (also keinem stable Flutter release)
  - Anpassungen nötig für Karte und Device-ID
  - Cross-Plattform-Wechsel benötigt eine Form von Login
