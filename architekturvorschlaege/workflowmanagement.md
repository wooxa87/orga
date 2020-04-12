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
