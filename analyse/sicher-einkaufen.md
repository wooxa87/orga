# Sicher-einkaufen

## Anforderungen

Für die Details bitte die [Anforderungsspezifikation](https://github.com/SafeMarket-WirVsVirus/orga/blob/master/anforderungsspezifikation.md) anschauen. Es gibt Anforderungen die manche Kompnenten nicht erfüllen müssen (z.B. Tutorial und Backend), dann schreibt einfach Nicht erfüllbar rein. Bei Teilweise, bitte kurz erläutern was geht und was nicht.

### Funktional

|ID|Anforderung|Erfüllt?|
|:-|:-|:-|
|001|Das System bietet die Funktion für den Einkauf einen Termin (Zeitpunkt + Dauer) zu reservieren. Zusätzlich zeigt es an, welche Geschäfte aktuell stark besucht sind.|Nein|
|002|Das System plant Kapazitäten für Laufkunden bzw. technische nicht versierte Benutzer ein.|Ja aber nur für Laufkunden|
|003|Das System berücksichtigt die knappe Zeit bestimmter Gruppen und ermöglicht diesen optimale Termine.|Nein|
|004|Das System ermöglicht es für Freunde und Verwandte Termine zu buchen. Außerdem kann per Telefon ein Termin vereinbart werden.|Nein|
|005|Das System erinnert einen Kunden an seinen Termin.|Nein|
|006|Das System bietet die Funktion, die Markt Eigenschaften (Kapazität/Termindauer..) zu konfigurieren / anpassen und nie zu viele Kunden in das Geschäft zu lassen.|Ampelsystem|
|007|Das System bietet (Inhabern) die Möglichkeit, Endkunden einen frei wählbaren Status zu präsentieren.|Ja|
|012|Das System bietet bei freien Kapazitäten Kunden aktiv Termine an.|Nein|
|014|Das System kann die Authentizität von Geschäften durch manuellen Abgleich und/oder mit externen Daten bestimmen.|Ja/Teilweise(durch imports bekannter Märkte aus OSM)|
|009|Es können nur Läden angelegt/ verwaltet werden, wenn der Nutzer als Ladeninhaber bestätigt wurde.|Ja/Teilweise(Accounts können nur änderungen an Märkten vornehmen wenn sie durch einen admin bestätigt sind, ist aber nicht ausreichend implementiert. zz nur das in der db ne column existiert und das standardmäßig diese False ist)|
|013|Das System bietet die Möglichkeit eine prozentuale Einschätzung (“Ampel”) über die Auslastung abzugeben.|Ja|
|015|Das System zeigt in der App/Website teilnehmende Geschäfte an.|Teilweise(Es zeigt zz alle an, ist aber nen aufwand von ca 5min)|
|016|Das System informiert per Telefon über teilnehmende Geschäfte.|Nein|
|017|Das System bietet die Möglichkeit Termine zu verifizieren.|Nein|
|018|Das System führt den Nutzer durch ein Tutorial und informiert über den Verhaltenskodex und Ablauf.|Nein|
|019|Das System präsentiert dem Inhaber eine Übersicht vergangener Daten.|Nein/Bedacht|
|020|Das System ermöglicht es einem Geschäft seine Mitarbeiter zu konfigurieren.|Es sind mehere Acc per Markt möglich aber es ist nicht implementiert das einer die anderen verwaltet|

### Nicht-funktional

Bitte eine kurze Aussage zu:

Effizienz/Performance:Api seitig Python 3.6 mit fastapi+gunicorn anstatt vorher flask(auf einem Niveau mit go und Nodejs,theoretisch ca 4-5k Anfragen pro Kern pro s) , [schnellstes framework in python](https://www.techempower.com/benchmarks/#section=data-r18&hw=ph&test=query&l=zijzen-7)

Kompatibilität(Schnittstellen zu anderen Systemen): Rest api via json payloads mit openapi und swagger. Datenbankschnittstelle sqlalchemy core fürs query bauen und ein async driver für postgresql/mysql

Benutzbarkeit(für Endnutzer):Webseite(https://sicher-einkaufen.info), 5 endpoints die per ui via swagger aufgerufen werden können(https://controlservice.sicher-einkaufen.info/docs) 

Code: https://github.com/fachinformatiker/wirvsvirus_project_17/tree/development/control_service

Zuverlässigkeit:sehr zuverlässig da error handling zu 80-90% durch das framework gemacht werden, (5xx,4xx Fehler etc), Input validation,autorestarts via Docker und gunicorn

Sicherheit: Authentifizierung via Oauth2, ssl via letsencrypt und traefik. 

Wartbarkeit(Modularität/Dokumentation):auto Doku via Swagger, pro Endpoint eine funktion,ca 300 Zeilen,

Portabilität(Abhängigkeiten zu Frameworks, Betriebssystem, Programmiersprache): Docker/Python 3.6+,Plattformunabhängig,[Fastapi](https://pypi.org/project/fastapi/),[databases](https://pypi.org/project/databases/),[sqlalchemy](https://pypi.org/project/SQLAlchemy/)
