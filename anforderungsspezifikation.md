# Anforderungsspezifikation

## Einleitung

Im folgenden Kapitel wird ein Überblick über den grundlegenden Inhalt
dieses Dokuments gegeben. Es werden Begriffe und Abkürzungen erklärt,
sowie der Umfang des Softwareproduktes beschrieben. Im Weiteren gibt es
Einblick in den Umfang der Software Requirements Specification.

### Zweck

Der Zweck dieser Ausführung ist es eine detaillierte Übersicht über die
Funktionalität des “SafeMarket” Gesamtsystems zu geben. Als Ergebnis
entsteht hier mit ein Dokument, welches eine Implementation durch die
Entwickler ermöglichen soll. Produktanforderungen, Abfolgen und
Schnittstellen zu externen Systemen oder Diensten werden dabei
dargestellt.

### Umfang

Das ursprüngliche “Safe Market” Team kam im Rahmen des “WirVsVirus”
Hackathon zusammen. Ziel ist es die Auslastung in verschiedenen Läden
besser zu steuern. Nach der Durchführung des Hackathons schlossen sich
weitere Teams, welche ein ähnliches Thema bearbeiteten, dem “SafeMarket”
Team an.

“SafeMarket” ist der digitale Reservierungsservice für verschiedene
Supermärkte bzw. Läden. Ein Kunde kann einfach und schnell einen
Zeitslot zum Einkaufen buchen. Dabei kann er Auslastungsspitzen erkennen
und so die Warteschlange umgehen. Kunden die “SafeMarket” nutzen
schützen sich selbst, verringern die Ansteckungsgefahr für andere
Kunden und Mitarbeiter und entspannen die Situation in den Läden. “Safe
Market” optimiert die Auslastung in Bezug auf die Kapazitäten der Läden
und berücksichtigt dabei auch die Laufkundschaft. Mit der Gesamtlösung
kann auch per Telefon interagiert werden. “Safe Market” strebt eine
schnelle Verbreitung an, um seine Vorteile schnellstmöglich in der
Gesellschaft zu etablieren. Die Software wird durch das “Safe
Market”-Team geplant, produziert und betreut, solange wie die
Unterstützung gewährleistet ist.

### Verweise auf sonstige Ressourcen und Quellen

- [Devpost des ursprünglichen”Safe Market” Hackathon Projekts:](https://devpost.com/software/17_supermarkt_status_reservation_system)

- [Devpost des “Queued” Hackathon Projekts:](https://devpost.com/software/1_019_92_timeslotmanagement)

- [Devpost des “Sicher einkaufen” Hackathon Projekts:](https://devpost.com/software/17_supermarket_status_platform_live_tracking_user)

### Erläuterungen zu Begriffen und/oder Abkürzungen

- App meint immer iOS, Android und Website.
- Termindauer = Einkaufszeit ist 50 Minuten
- Terminbuchungsintervall = Buchbarer Ticket beginn alle 10 Minuten
- Terminauslastung = Um 18:00 sind noch 5 Tickets verfügbar, berechnet aus - - Einkaufszeit und Interval
- Anforderungen gelten allgemeint als erfüllt, sobald die zugeordneten Funktionen implementiert & getestet sind.

### Übersicht

Im Weiteren wird zunächst die Produktperspektive erläutert. So soll ein
Eindruck vermittelt werden, welche Funktionalität das Softwareprodukt im
Groben mitbringt. Zur Detaillierung werden die Anwendungsfälle
aufgezeigt und diese mit Hilfe von Aktivitätsdiagrammen dargestellt. So
soll definiert werden welche Funktionen die Software im fertigen Zustand
mitbringen wird. Darauf folgt eine Spezifizierung der funktionalen und
nicht-funktionalen Anforderungen der Software.

## Allgemeine Beschreibung

Dieses Kapitel gibt einen Überblick über die Funktionen des Systems und
seine Beziehungen zu seiner Umwelt. Weiterhin werden die Kundengruppen
des Systems erläutert. Aus den zuerst genannten Inhalten werden im
Folgendem Einschränkungen, Abhängigkeiten und weitere Annahmen
abgeleitet.

### Produktperspektive

Die Gesamtlösung dient zur Abstimmung der Kapazität verschiedener Läden
und deren Auslastung. Dafür interagieren die Verbraucher und die
Ladeninhaber mit der Software.

Zur Kontrolle der Einhaltung konfigurierbarer Kapazitätsbeschränkungen
wird auch der Einlasser mit dem System interagieren können. Die Inhaber
von Geschäften können ihre Öffnungszeiten und Kapazitäten für geplante
Kunden und Laufkundschaft mittels einer Software konfigurieren. Der
Verbraucher kann intuitiv mit Hilfe einer App im Geschäft seiner Wahl
einen Termin zum Einkaufen buchen. Das System berücksichtigt besondere
Verbrauchergruppen, wie Personen für die das Coronavirus besonders
gefährlich ist und zur Zeit besonders geforderte Berufsgruppen, und
ermöglicht diesen zeitnahe Termine.

Für die Umsetzung kann der Einlasser die gebuchten Termine kontrollieren
und die aktuelle Auslastung in das System eingeben. Eine
Hardware-Unterstützung für diese Aktivität ist denkbar. Eine Übersicht
über verschiedene externe Elemente mit denen das System interagiert ist
im Folgendem dargestellt:

### Zuordnung der Produktfunktionen zu den betroffenen funktionalen Anforderungen

#### Endkunde

|ID|Produktfunktion|
|:-|:-|
|003|Endkunde kann über eine App oder Website angeben, ob er zu einer Risiko- / besonders geforderten Berufsgruppe angehört und zeitnah Termine erhalten|
|003|Endkunde kann per Telefon angeben, ob er zu einer Risiko- / besonders geforderten Berufsgruppe angehört|
|015|Endkunde kann über eine App oder Website teilnehmenden Läden in seiner Nähe finden|
|016|Endkunde kann per Telefon teilnehmenden Läden in seiner Nähe finden|
|001|Endkunde kann über eine App in teilnehmenden Läden einen Termin buchen und absagen|
|001, 004|Endkunde kann per Telefon in teilnehmenden Läden einen Termin buchen|
|001|Endkunde wird über eine App über die voraussichtliche Auslastung in teilnehmenden Läden informiert|
|001|Endkunde wird per Telefon über die voraussichtliche Auslastung in teilnehmenden Läden informiert|
|005|Endkunde wird über eine App an anstehende Termine erinnert|
|012|Endkunde kann über eine App aktiv über Termine informiert werden, wenn die Auslastung gerade niedrig ist und er es wünscht|
|002, 004|Endkunde kann über eine App für Freunde und Verwandte Termine buchen|
|017|Endkunde kann über eine App nachweisen, dass er einen Termin besitzt|
|017|Endkunde kann mündlich nachweisen, dass er einen Termin besitzt|
|001|Endkunde kann auf einem Gerät ein Termin buchen und auf einem anderen abrufen indem der QR Code mit der Kunden-ID in der App abgescannt/eingetippt werden kann(Frage nach reichen Daten über Termine aus um Person zu rekonstruieren?)|
|001|Anspruch des Endkunden den Laden zu betreten, verfällt bei einigen Minuten Verspätung|
|001|Endkunde darf nur einen Termin pro Laden buchen|
|001|Endkunde darf maximal gleichzeitig eine bestimmte Anzahl an Terminen halten|
|018|Endkunde muss in die App eingeführt werden (Tutorial, Solidarität, Verhaltensguide)|
|003|Endkunde mit speziellem Status (Berufsgruppe etc.) muss sich in App entsprechend verifizieren/bestätigen|
|003|Endkunde mit speziellem Status (Berufsgruppe etc.) muss sich bei Laden verifizieren, dass dieser Status berechtigt ist|

#### Inhaber

|ID|Produktfunktion|
|:-|:-|
|009, 014|Inhaber kann sich über eine Website oder App im System registrieren|
|006|Inhaber kann Öffungszeiten konfigurieren/nachträglich anpassen|
|006|Inhaber kann Max Zeitdauer eines Termins und empfohlene Termin Dauer konfigurieren/nachträglich anpassen|
|002, 006|Inhaber kann die absolute Kapazität für geplante Kunden und Laufkundschaft konfigurieren/nachträglich anpassen|
|007|Inhaber kann begrenzten Freitext angeben, um Kunde mit zusätzlichen Informationen zu versorgen|
|013|Inhaber kann aktuelle Auslastung eingeben für Übersicht beim Endkunden, wo freie Plätze sind|
|019|Inhaber hat Übersicht über die Ticketnutzung|
|020|Inhaber kann mit Hilfer einer E-Mail Mitarbeiter konfigurieren, die die Mitarbeiterrolle innehaben. (Alternativ GUID, z.B. als QR-Code)|

#### Mitarbeiter

|ID|Produktfunktion|
|:-|:-|
|017|Mitarbeiter kann mit einer App und Website verifizieren, ob ein Kunde über einen gebuchten Termin verfügt (mündlich oder per QR-Code)|
|013|Mitarbeiter kann aktuelle Auslastung eingeben für Übersicht beim Endkunden, wo freie Plätze sind|
|003|Mitarbeiter kann Status von speziellen Berufsgruppen bestätigen|

### Benutzermerkmale

**Endkunde bzw. Verbraucher:** Praktisch jede Person, die Einkaufen
gehen muss. Verschiedener Bildungsstand und verschiedenes technisches
Verständnis. Verbraucher können zu einer Risikogruppe und oder
Prioritätsgruppe gehören. Der Verbraucher möchte stressfrei und mit
einem geringen Infektionsrisiko einkaufen. Auf Warteschlangen möchte er
nicht treffen.

**Inhaber:** Besitzer eines/mehrerer Geschäfts stehen derzeit vor der
Herausforderung, dass sie nur eine begrenzte Anzahl an Kunden in ihre
Geschäfte lassen dürfen/wollen und weitere wechselnde gesetzliche
Vorgaben erfüllen müssen. Das führt zu einer geringeren
Kundenzufriedenheit, die es abzuwenden gilt. Ein höherer Bildungsstand
kann neben einem normalen technischem Verständnis angenommen werden. Das
Alter ist von 25 bis 67 gestreut.

**Mitarbeiter:** Personen, die beauftragt sind, die Anzahl an Personen
in einem Geschäft zu kontrollieren. Dabei möchten sie sich nicht
infizieren und die Anzahl der Personen möglichst einfach kontrollieren.
Das Alter ist weit gestreut und der Bildungsstand eher gering.
Grundlegendes technisches Verständnis ist gegeben.

### Einschränkungen

Die App muss mit Android und iOS Geräten kompatibel sein. Die
aktuellsten Versionen jener Betriebssysteme sind nicht sonderlich
verbreitet, daher müssen auch ältere Versionen unterstützt werden. Für
Webapplikationen sind Edge, Chrome, Safari und Firefox zu unterstützen.
Datenschutzrechtliche Bestimmungen sind einzuhalten.

### Annahmen und Abhängigkeiten

Es wird angenommen, dass jede Frontend-Anwendung dauerhaft mit dem Internet verbunden ist. Lediglich Informationen zu konkreten Termin sind beim Endkunden ohne Internet verfügbar.

Termine können nur zu jeder glatten zehnten Minute beginnen (Beginn Minute modulo 10 = 0). Die Dauer eines Termins ist ein Vielfaches von 10 Minuten. Daraus wird die geplannte Auslastung in einem zehnminütigen Intervall ermittelt.

## Anforderungen

Im dritten Kapitel erfolgt eine genaue Darstellung und Beschreibung der
Anforderungen.

### Funktional:

| ID                                      | 001                                                                                                                                                                  |
| --------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Kundenaussage                           | Beim Einkaufen möchte ich (Endkunde) mich nicht anstecken.                                                                                                           |
| Wer muss zur Lösung eingebunden werden? | Ich, andere Kunden, der Einlasser, das Geschäft                                                                                                                      |
| Was ist das Problem?                    | Im/Vor Geschäft sind zu viele Personen                                                                                                                               |
| Warum ist das Problem entstanden?       | Viele Kunden gehen zur gleichen Zeit einkaufen.                                                                                                                      |
| Wann tritt das Problem auf?             | Immer wenn ein Kunde einkaufen geht                                                                                                                                  |
| Wo tritt das Problem auf?               | Im/Vor Geschäft                                                                                                                                                      |
| Wie erkennt man die Lösung?             | Im Geschäft wird eine maximale Personenzahl nicht überschritten (und es bilden sich keine Schlangen vor dem Geschäft.)                                               |
| Anforderung                             | Das System bietet die Funktion für den Einkauf einen Termin (Zeitpunkt + Dauer) zu reservieren. Zusätzlich zeigt es an, welche Geschäfte aktuell stark besucht sind. |

| ID                                      | 002                                                                                                                                                        |
| --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Kundenaussage                           | Ich (Kunde) möchte so weit möglich wie bisher einkaufen. Ich suche mir die Zeit und Ort selbst aus. Leider muss ich oft in Schlangen vor den Läden warten. |
| Wer muss zur Lösung eingebunden werden? | Ich, das Geschäft, der Einlasser                                                                                                                           |
| Was ist das Problem?                    | Viele Kunden gehen zur gleichen Zeit einkaufen.                                                                                                            |
| Warum ist das Problem entstanden?       | Durch den geregelten Arbeitsalltag                                                                                                                         |
| Wann tritt das Problem auf?             | Wenn ich in der Schlange warte                                                                                                                             |
| Wo tritt das Problem auf?               | Vor dem Geschäft                                                                                                                                           |
| Wie erkennt man die Lösung?             | Es gibt vor dem Geschäft keine Schlangen mehr.                                                                                                             |
| Anforderung                             | Das System plant Kapazitäten für Laufkunden bzw. technische nicht versierte Benutzer ein.                                                                  |

| ID                                      | 003                                                                                                              |
| --------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Kundenaussage                           | Ich (Kunde) bin Arzt und möchte meinen Einkauf möglichst schnell erledigen, damit ich den Patienten helfen kann. |
| Wer muss zur Lösung eingebunden werden? | Ich, andere Kunde, der Einlasser, das Geschäft                                                                   |
| Was ist das Problem?                    | bestimmte Berufsgruppen werden derzeit besonders stark benötigt / müssen viel arbeiten.                          |
| Warum ist das Problem entstanden?       | Durch die hohe Anzahl an gefährdeten Patienten                                                                   |
| Wann tritt das Problem auf?             | Vor/Im Geschäft                                                                                                  |
| Wo tritt das Problem auf?               | Vor dem Einkauf                                                                                                  |
| Wie erkennt man die Lösung?             | bestimmte Berufsgruppen können zu der für sie optimalen Zeit einkaufen                                           |
| Anforderung                             | Das System berücksichtigt die knappe Zeit bestimmter Gruppen und ermöglicht diesen optimale Termine.             |

| ID                                      | 004                                                                                                                                            |
| --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Kundenaussage                           | Ich (Kunde) bin schon sehr alt und kann ohne Hilfe digital keinen Termin buchen. Zusätzlich bin ich besonders durch das Coronavirus gefährdet. |
| Wer muss zur Lösung eingebunden werden? | Ich, meine Freunde/Verwandte                                                                                                                   |
| Was ist das Problem?                    | Manche Personen sind hilflos/isoliert, da sie ungeübt im Umgang mit Smartphones/Computern sind                                                 |
| Warum ist das Problem entstanden?       | Durch das Kontaktverbot ergeben sich schwere Einschränkungen im Alltag                                                                         |
| Wann tritt das Problem auf?             | Wenn ich Einkaufen möchte                                                                                                                      |
| Wo tritt das Problem auf?               | Zu Hause                                                                                                                                       |
| Wie erkennt man die Lösung?             | Ich auch ohne technisches Wissen sicher Einkaufen gehen                                                                                        |
| Anforderung                             | Das System ermöglicht es für Freunde und Verwandte Termine zu buchen. Außerdem kann per Telefon ein Termin vereinbart werden                   |

| ID                                      | 005                                                                                                        |
| --------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Kundenaussage                           | Ich (Kunde) bin ziemlich unstrukturiert. Daher gehe oft Einkaufen, wenn auch alle anderen einkaufen gehen. |
| Wer muss zur Lösung eingebunden werden? | Ich                                                                                                        |
| Was ist das Problem?                    | Ich stehe in der Schlange.                                                                                 |
| Warum ist das Problem entstanden?       | Ich hätte zu einer anderen Zeit einkaufen gehen können, habe es aber vergessen.                            |
| Wann tritt das Problem auf?             | Vor dem Einkauf                                                                                            |
| Wo tritt das Problem auf?               | In der Schlange                                                                                            |
| Wie erkennt man die Lösung?             | Ich werde an gute Zeitpunkte zum Einkaufen erinnert.                                                       |
| Anforderung                             | Das System erinnert einen Kunden an seinen Termin.                                                         |

| ID                                      | 006                                                                                                                                                                  |
| --------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Kundenaussage                           | Ich (Inhaber) muss die gesetzlichen Anforderungen zur maximalen Personenzahl einhalten. Dadurch bilden sich lange Schlangen.                                         |
| Wer muss zur Lösung eingebunden werden? | die Kunden, der Einlasser                                                                                                                                            |
| Was ist das Problem?                    | Viele Kunden wollen zur gleichen Zeit einkaufen.                                                                                                                     |
| Warum ist das Problem entstanden?       | Durch die Einführung der Vorschrift                                                                                                                                  |
| Wann tritt das Problem auf?             | Bei Auslastungsspitzen                                                                                                                                               |
| Wo tritt das Problem auf?               | Im/Vor dem Geschäft                                                                                                                                                  |
| Wie erkennt man die Lösung?             | Es bilden sich keine Schlangen mehr vor den Geschäften, Kundenstrom verteilt                                                                                         |
| Anforderung                             | Das System bietet die Funktion, die Markt Eigenschaften (Kapazität/Termindauer..) zu konfigurieren / anpassen und nie zu viele Kunden in das Geschäft zu lassen. |

| ID                                      | 007                                                                                                                                        |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Kundenaussage                           | Ich (Inhaber) habe viele Kunden, die Klopapier horten, aber keines kaufen können, weil sie zu spät sind. Außerdem gibt es lange Schlangen. |
| Wer muss zur Lösung eingebunden werden? | Ich, die Kunden, die Mitarbeiter                                                                                                           |
| Was ist das Problem?                    | Die Nachfrage für bestimmte Artikelgruppen ist drastisch gestiegen.                                                                        |
| Warum ist das Problem entstanden?       | Panik, wegen des Coronavirus                                                                                                               |
| Wann tritt das Problem auf?             | Mittags bis Ladenschluss                                                                                                                   |
| Wo tritt das Problem auf?               | Im Geschäft                                                                                                                                |
| Wie erkennt man die Lösung?             | Wenn kritische Artikelgruppen ausverkauft sind, steht kein Kunde mehr wegen diesen in der Schlange                                         |
| Anforderung                             | Das System bietet die Möglichkeit, Endkunden einen frei wählbaren Status zu präsentieren.                                                  |

| ID                                      | 012                                                                                                        |
| --------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Kundenaussage                           | Ich (Kunde) bin ziemlich unstrukturiert. Daher gehe oft Einkaufen, wenn auch alle anderen einkaufen gehen. |
| Wer muss zur Lösung eingebunden werden? | Ich                                                                                                        |
| Was ist das Problem?                    | Ich stehe in der Schlange.                                                                                 |
| Warum ist das Problem entstanden?       | Ich hätte zu einer anderen Zeit einkaufen gehen können, habe es aber vergessen.                            |
| Wann tritt das Problem auf?             | Vor dem Einkauf                                                                                            |
| Wo tritt das Problem auf?               | In der Schlange                                                                                            |
| Wie erkennt man die Lösung?             | Ich werde an gute Zeitpunkte zum Einkaufen erinnert.                                                       |
| Anforderung                             | Das System bietet bei freien Kapazitäten Kunden aktiv Termine an. 

| ID                                      | 014                                                                                                              |
| --------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Aussage                                 | Die Authentizität der Geschäfte muss überprüft werden                                                            |
| Wer muss zur Lösung eingebunden werden? | Die Inhaber, externe Datenquellen                                                                                |
| Was ist das Problem?                    | Endkunde bucht Termin in Geschäft, welches nicht existiert                                                       |
| Warum ist das Problem entstanden?       | Ohne Überprüfung kann jeder (auch nicht existente) Geschäfte einstellen                                          |
| Wann tritt das Problem auf?             | Bei der Buchung bzw. beim Einkauf                                                                                |
| Wo tritt das Problem auf?               | Zu Hause bzw. vor dem nicht existenten Laden                                                                     |
| Wie erkennt man die Lösung?             | Es gibt keine nicht existenten Läden im System                                                                   |
| Anforderung                             | Das System kann die Authentizität von Geschäften durch manuellen Abgleich und/oder mit externen Daten bestimmen. |

| ID                                      | 009                                                                                              |
| --------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Aussage                                 | Der Nutzer der Mitarbeiter App der den Laden verwalten möchte, muss als Inhaber bestätigt werden |
| Wer muss zur Lösung eingebunden werden? | Authentifikation des Inhabers                                                                    |
| Was ist das Problem?                    | Sonst kann jeder einfach Läden anlegen / verwalten etc, der sich Inhaber registriert             |
| Warum ist das Problem entstanden?       | Ohne Überprüfung kann jeder (auch nicht existente) Geschäfte einstellen                          |
| Wann tritt das Problem auf?             | Beim Verwalten der Läden                                                                         |
| Wo tritt das Problem auf?               | Zu Hause bzw. vor dem nicht existenten Laden                                                     |
| Wie erkennt man die Lösung?             | Nur Läden von autorisierten Inhabern vorhanden                                                   |
| Anforderung                             | Es können nur Läden angelegt/ verwaltet werden, wenn der Nutzer als Ladeninhaber bestätigt wurde |

| ID                                      | 013                                                                                                      |
| --------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Aussage                                 | Die Auslastung eines Geschäfts muss bekannt und einstellbar sein.                                        |
| Wer muss zur Lösung eingebunden werden? | Die Mitarbeiter                                                                                          |
| Was ist das Problem?                    | Falsche Auslastungsdaten schränken die Kernfunktionalität des Systems ein                                |
| Warum ist das Problem entstanden?       | Andere Anforderung erfordern dies                                                                        |
| Wann tritt das Problem auf?             | Jedes mal, wenn jemand Informationen über die Auslastung brauch                                          |
| Wo tritt das Problem auf?               | Prinzipiell überall                                                                                      |
| Wie erkennt man die Lösung?             | Auslastungsinformationen für teilnehmende Geschäfte sind verfügbar.                                      |
| Anforderung                             | Das System bietet die Möglichkeit eine prozentuale Einschätzung (“Ampel”) über die Auslastung abzugeben. |

| ID                                      | 015                                                                                 |
| --------------------------------------- | ----------------------------------------------------------------------------------- |
| Aussage                                 | Der Nutzer muss über teilnehmenden Geschäfte informiert werden via App/Webapp       |
| Wer muss zur Lösung eingebunden werden? | Die Inhaber, die Entwickler                                                         |
| Was ist das Problem?                    | Das Gesamtkonzept kann nur in teilnehmenden Geschäften erfolgreich umgesetzt werden |
| Warum ist das Problem entstanden?       | Im Gesamtkonzept begründet                                                          |
| Wann tritt das Problem auf?             | Jedes mal, wenn jemand einen Termin buchen will.                                    |
| Wo tritt das Problem auf?               | Prinzipiell überall                                                                 |
| Wie erkennt man die Lösung?             | Der Endkunde kann nachschauen, welche Geschäfte teilnehmen                          |
| Anforderung                             | Das System zeigt in der App/Website teilnehmende Geschäfte an.                      |

| ID                                      | 016                                                                                 |
| --------------------------------------- | ----------------------------------------------------------------------------------- |
| Aussage                                 | Der Nutzer muss über teilnehmenden Geschäfte informiert werden via Telefon          |
| Wer muss zur Lösung eingebunden werden? | Die Inhaber, die Entwickler                                                         |
| Was ist das Problem?                    | Das Gesamtkonzept kann nur in teilnehmenden Geschäften erfolgreich umgesetzt werden |
| Warum ist das Problem entstanden?       | Im Gesamtkonzept begründet                                                          |
| Wann tritt das Problem auf?             | Jedes mal, wenn jemand einen Termin buchen will.                                    |
| Wo tritt das Problem auf?               | Prinzipiell überall                                                                 |
| Wie erkennt man die Lösung?             | Der Endkunde kann nachschauen, welche Geschäfte teilnehmen                          |
| Anforderung                             | Das System informiert per Telefon über teilnehmende Geschäfte.                      |

| ID                                      | 017                                                                           |
| --------------------------------------- | ----------------------------------------------------------------------------- |
| Aussage                                 | Die Mitarbeiter müssen prüfen können, dass der Endkunde einen Termin besitzt. |
| Wer muss zur Lösung eingebunden werden? | Die Mitarbeiter, der Endkunde                                                 |
| Was ist das Problem?                    | Nur der Besitzer eines Termins darf seinen reservierten termin nutzen.        |
| Warum ist das Problem entstanden?       | Im Gesamtkonzept begründet                                                    |
| Wann tritt das Problem auf?             | Jedes mal, wenn Kunde mit Termin ein geschäft betreten will.                  |
| Wo tritt das Problem auf?               | Prinzipiell in jedem Geschäft                                                 |
| Wie erkennt man die Lösung?             | Termine können geprüft werden                                                 |
| Anforderung                             | Das System bietet die Möglichkeit Termine zu verifizieren.                    |

| ID                                      | 018                                                                                                |
| --------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Aussage                                 | Der Endkunde muss die Funktionsweise des Systems erklärt bekommen                                  |
| Wer muss zur Lösung eingebunden werden? | Der Endkunde, die Entwickler                                                                       |
| Was ist das Problem?                    | Ahnungslose Kunden bedienen das System falsch.                                                     |
| Warum ist das Problem entstanden?       | Wissensmangel                                                                                      |
| Wann tritt das Problem auf?             | Jedes mal, wenn ein neuer Endkunde das System nutzt                                                |
| Wo tritt das Problem auf?               | Prinzipiell überall                                                                                |
| Wie erkennt man die Lösung?             | Es gibt ein Tutorial und Verhaltenskodex                                                           |
| Anforderung                             | Das System führt den Nutzer durch ein Tutorial und informiert über den Verhaltenskodex und Ablauf. |

| ID                                      | 019                                                                                                    |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Aussage                                 | Ich Inhaber möchte wissen, ob meinen Aufteilung auf geplante Termine und zufällige Kunden optimal ist. |
| Wer muss zur Lösung eingebunden werden? | Der Inhaber, die Entwickler                                                                            |
| Was ist das Problem?                    | Eine falsche Gewichtung wird zum Kundenverlust                                                         |
| Warum ist das Problem entstanden?       | Der Inhaber muss eine Gewichtung festlegen.                                                            |
| Wann tritt das Problem auf?             | Während der Einführung des Systems                                                                     |
| Wo tritt das Problem auf?               | Im Büro                                                                                                |
| Wie erkennt man die Lösung?             | Es gibt eine Aufbereitung vergangener Daten                                                            |
| Anforderung                             | Das System präsentiert dem Inhaber eine Übersicht vergangener Daten.                                   |

| ID                                      | 020                                                                             |
| --------------------------------------- | ------------------------------------------------------------------------------- |
| Aussage                                 | Ich Inhaber muss Mitarbeiter zum System einladen können                         |
| Wer muss zur Lösung eingebunden werden? | Der Inhaber, die Mitarbeiter                                                    |
| Was ist das Problem?                    | Es wird eine direkte Zuordnung benötigt                                         |
| Warum ist das Problem entstanden?       | Mitarbeiter können mit dem Gesamtsystem interagieren                            |
| Wann tritt das Problem auf?             | Während der Einführung des Systems                                              |
| Wo tritt das Problem auf?               | Im Geschäft                                                                     |
| Wie erkennt man die Lösung?             | Mitarbeiter sind einem Geschäft zugeordnet und haben Zugriff auf dessen Termine |
| Anforderung                             | Das System ermöglicht es einem Geschäft seine Mitarbeiter zu konfigurieren.     |

## Nicht-funktional:

| ID                                      | 500                                                                                         |
| --------------------------------------- | ------------------------------------------------------------------------------------------- |
| Aussage                                 | Einkaufen darf nicht komplizierter werden.                                                  |
| Wer muss zur Lösung eingebunden werden? | Die Geschäfte, der Einlasser, die Entwickler                                                |
| Was ist das Problem?                    | Einkaufen darf nicht nennenswert mehr Zeit als vorher beanspruchen                          |
| Warum ist das Problem entstanden?       | Durch die Einführung der Beschränkungen                                                     |
| Wann tritt das Problem auf?             | Vor/während des Einkaufs                                                                    |
| Wo tritt das Problem auf?               | Vor/Im Laden                                                                                |
| Wie erkennt man die Lösung?             | Kunden mit unterschiedlich ausgeprägten Technik-Know-How können eigenständig Termine buchen |
| Anforderung                             | Die Benutzeroberfläche ist intuitiv / leicht verstehen.                                     |

| ID                                      | 501                                                                                                 |
| --------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Aussage                                 | Das System muss ständig verfügbar sein, da sonst mein (Inhaber) Umsatz gefährdet ist                |
| Wer muss zur Lösung eingebunden werden? | Der Entwickler                                                                                      |
| Was ist das Problem?                    | Durch Softwarefehler kann das System in einen Fehlerzustand geraten.                                |
| Warum ist das Problem entstanden?       | Bei der Entwicklung ist ein Fehler unterlaufen                                                      |
| Wann tritt das Problem auf?             | willkürlich                                                                                         |
| Wo tritt das Problem auf?               | ortsunabhängig                                                                                      |
| Wie erkennt man die Lösung?             | Die Software wird entsprechenden Qualitätstests unterzogen und Architektur-Komponenten abgesichert. |
| Anforderung                             | Das System ist nahezu immer verfügbar.                                                              |

| ID                                      | 502                                                                                                                                         |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| Aussage                                 | Wir (die Bundesregierung + Inhaber) möchten möglichst viele Menschen mit der Lösung erreichen.                                              |
| Wer muss zur Lösung eingebunden werden? | Die Entwickler                                                                                                                              |
| Was ist das Problem?                    | Die Software besitzt eine begrenzte Performance.                                                                                            |
| Warum ist das Problem entstanden?       | Durch die hohen Nutzerzahlen                                                                                                                |
| Wann tritt das Problem auf?             | Wenn viele Menschen das System gleichzeitig nutzen                                                                                          |
| Wo tritt das Problem auf?               | ortsunabhängig                                                                                                                              |
| Wie erkennt man die Lösung?             | Die Performance des Systems wird durch ausreichende Tests und eine geeignete Architektur sichergestellt.                                    |
| Anforderung                             | Das Backend reagiert schnell, unabhängig von der Nutzeranzahl *(Internes erstes Ziel: kann Bedarf bis zu eine Million Nutzer unterstützen)* |

| ID                                      | 503                                                                                                    |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Aussage                                 | Wir (die Bundesregierung + Inhaber) möchten möglichst viele Menschen mit der Lösung erreichen.         |
| Wer muss zur Lösung eingebunden werden? | Die Entwickler                                                                                         |
| Was ist das Problem?                    | Die Nutzer verwenden unterschiedliche Endgeräte                                                        |
| Warum ist das Problem entstanden?       | Die Nutzer haben verschiedenes technisches Verständnis.                                                |
| Wann tritt das Problem auf?             | Immer bei Benutzung                                                                                    |
| Wo tritt das Problem auf?               | ortsunabhängig                                                                                         |
| Wie erkennt man die Lösung?             | Die Lösung funktioniert bei den meisten Nutzern                                                        |
| Anforderung                             | Das System unterstützt alle gängigen Betriebssysteme und Browser (Windows, MacOS, Linux, Android, iOS) |

| ID                                      | 504                                                                                       |
| --------------------------------------- | ----------------------------------------------------------------------------------------- |
| Aussage                                 | Meine Daten dürfen nicht in falsche Hände gelangen.                                       |
| Wer muss zur Lösung eingebunden werden? | Die Entwickler                                                                            |
| Was ist das Problem?                    | Daten dürfen nur für angegebene Zwecke verarbeitet werden                                 |
| Warum ist das Problem entstanden?       | Das System muss personenbezogene Daten verarbeiten                                        |
| Wann tritt das Problem auf?             | Während der Benutzung                                                                     |
| Wo tritt das Problem auf?               | ortsunabhängig                                                                            |
| Wie erkennt man die Lösung?             | Es werden sichere Technologien eingesetzt.                                                |
| Anforderung                             | Das System erfüllt die datenschutzrechtlichen Bestimmungen und ist so sicher wie möglich. |

| ID                                      | 505                                                                                                          |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Aussage                                 | Die Lösung muss erweiterbar und verständlich sein.                                                           |
| Wer muss zur Lösung eingebunden werden? | Die Entwickler                                                                                               |
| Was ist das Problem?                    | Das System wird iterativ entwickelt                                                                          |
| Warum ist das Problem entstanden?       | Neue Funktionen müssen integriert werden                                                                     |
| Wann tritt das Problem auf?             | Während der Entwicklung                                                                                      |
| Wo tritt das Problem auf?               | ortsunabhängig                                                                                               |
| Wie erkennt man die Lösung?             | Der Quellcode ist dokumentiert und flexibel.                                                                 |
| Anforderung                             | Die Funktionalität des Systems und der Quellcode sind dokumentiert. Einzelne Subsysteme sind lose gekoppelt. |

| ID                                      | 506                                                                                                                                                          |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Aussage                                 | Leichtes hinzufügen oder deaktivieren von (externen) Funktionen                                                                                              |
| Wer muss zur Lösung eingebunden werden? | Die Entwickler, Architekt, Operation                                                                                                                         |
| Was ist das Problem?                    | Die Anforderungen und Features werden sich mit der Zeit ändern. Zusätzlich werden verschiedene Menschen mit unterschiedlichen Skills an der Lösung arbeiten. |
| Warum ist das Problem entstanden?       | Anforderungen ändern sich mit der Zeit                                                                                                                       |
| Wann tritt das Problem auf?             | Während der Entwicklung / Betrieb                                                                                                                            |
| Wo tritt das Problem auf?               | ortsunabhängig                                                                                                                                               |
| Wie erkennt man die Lösung?             | Das System ist offen und erweiterbar.                                                                                                                        |
| Anforderung                             | Das System muss sich leicht um Services ergänzen/ entfernen lassen, die Unabhängig von der Haupt Funktionalität lauffähig sind.                              |

| ID                                      | 507                                                                                                               |
| --------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Aussage                                 | Sicher stellen, dass trotz wegfall von Teammitgliedern weiter an der bestehen Entwicklung gearbeitet werden kann. |
| Wer muss zur Lösung eingebunden werden? | Die Entwickler, Architekt, Operation                                                                              |
| Was ist das Problem?                    | Wegfall von Teammitgliedern muss vom Skill kompensiert werden                                                     |
| Warum ist das Problem entstanden?       | Beispiel vue.js ;)                                                                                                |
| Wann tritt das Problem auf?             | Wenn Leading Developer das Team verlassen                                                                         |
| Wo tritt das Problem auf?               | ortsunabhängig                                                                                                    |
| Wie erkennt man die Lösung?             | Top 10 most popular Programmiersprachen...                                                                        |
| Anforderung                             | Keine Insellösungen verwenden sondern auf stark verbreiten Sprachen / Frameworks aufbauen.                        |

| ID                                      | 508                                                                                                               |
| --------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Aussage                                 | Ich als Betreiber, möchte möglichst geringe Laufzeitkosten haben.|
| Wer muss zur Lösung eingebunden werden? | Die Entwickler, Architekt, Operation                                                                              |
| Was ist das Problem?                    | Vor Wochenenden / Feiertagen oder zu Stoßzeiten ist die Auslastung höher, nur dann soll entsprechend Kapazität vorhanden sein.|
| Warum ist das Problem entstanden?       | Einkaufszeiten unterschiedlich zur Tages/ Wochenzeit                                                                                                |
| Wann tritt das Problem auf?             | Vor langen Wochenenden, Stoßzeiten                                                                         |
| Wo tritt das Problem auf?               | ortsunabhängig                                                                                                    |
| Wie erkennt man die Lösung?             | Das System skaliert nach Auslastung.                                                                       |
| Anforderung                             | Das System skaliert automatisiert, je nach benötigter Kapazität und abhängig für die entsprechend benötigten Funktionen.|
