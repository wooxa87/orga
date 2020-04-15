https://en.wikipedia.org/wiki/Workflow_management_system


Im endeffekt ein System welches periodische Abläufe automatisiert.

#### Solche Abläufe könnten sein:

- Marktdaten von OSM ziehen aufbereiten und in die Datenbank inserten

- Vorhersagen anhand statistischer modelle Für die Auslastung eines Marktes berechnen

- Machine Learning zeugs was auf mehrere Worker Nodes verteilt wird



## Prefect:
https://www.prefect.io/core/

- Gut für Tasks die sich gut clustern Lassen(Große Tasks, z.b. Machine Learning, statistik)
- Gut für Datenpiplines via DAGs

#### Skalierbarkeit Prefect:

- bis Zu 1000 Nodes(so ca 4000-5000 Cores)

- so ca max 1000 Workflows sie sekunde danach macht der scheduler glaub ich dicht weil der nicht verteilt arbeitet


#### Abläufe die ungeeignet sind:
Sachen die hochfrequent sind also Flows die öfter als 500-1000 mal die sekunde so Ablaufen

#### Vorbereitete Tasks Prefect:
- Airtable write row
- AWS(lamdba, S3)
- Azure (Blobstorage,Cosmosdb)
- Azure ML
- etc:https://docs.prefect.io/core/task_library/


## Celery
http://www.celeryproject.org/

- Gut für eine riesige Masse an Tasks(so ca 10k-100k/s möglich wzb.  verschicken von notifications an telegram,whatsapp,email
- unterstützt async via gevent (d.h eine queue mit async workern kann pro worker mehrere hundert tasks gleichzeitig abarbeiten, gut für pure i/o sachen)
-mehere queues mit unterschieldlichen worker pools möglich


#### Skalierbarkeit

- Nutzt redis oder Rabbitmq als messagebroker und hängt davon ab
- Wird bei instagram und Mozilla mit nen paar mio Tasks pro tag genutzt

## Bastians Vorschlag:
- eher celery nutzen und alles was wir dort nicht erreichen(Verarbeitung von Daten die größer als der Arbeitsspeicher sind und wir nicht als stream verarbeiten können, große wiederkehrende Jobs) können in dask/prefect(prefect baut auf dask auf) machen, was das execution backend ist ist im Endeffekt relativ egal, da das im Endeffekt nur die Änderung eines decorators erfordert pro Funktion um sie auf ein anderes backend zu porten
### Nutzen für cpu/io heavy Aufgaben die die api nicht handeln kann/sollte(alles Vorschläge):
#### i/o-queue:
- Notifications jeglicher Art(Email/WhatsApp, telegram, etc was evt noch kommt)
- Api Anfragen des backends die nicht direkt ans Frontend gekoppelt sind und nicht allzu Zeit kritisch sind (und/oder wir ne maximale Anzahl an anfragen haben bzw diese limiten wollen) (evt osm, maps api, telefonsystem, was weiß ich was noch kommt)
- generelle api für SMTP/Emailserver, Z. B. Newsletter oder überprüfen ob eine Emailadresse existiert(ist relativ aufwendig, da via regex, dns, und SMTP Anfrage, kann bis zu 2-3sek dauern wenn die latzenz des empfangenen emailserver schlecht ist, normalerweise aber eher so 100ms, muss man limiten, sonst mögen andere emailserver irgendwann uns  net mehr, sollte aber wenn möglich in der api selber passieren weil sonst evt ne extra Latenz drin ist)


#### CPU-queue:
- Statistiken für den Markt/Region/Deutschland berechnen
- evt große Daten ingests für die Märkte
