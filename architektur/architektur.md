*Das muss noch ausführlicher werden.*

# Architektur

- Wir haben uns auf FaaS mit Rate-Limiting (OpenWhisk in der IBM Cloud) für die Backend-Logik geeignet (Vgl. [Faas Vorschlag](./architekturvorschlaege/faas-architecture.md)). Webseiten werden per Webhosting ausgeliefert. Bei Bedarf kann noch ein Kubernetes Cluster daneben gestellt werden.
    - [Ganz kleiner C# Functions Showcase](https://github.com/SafeMarket-WirVsVirus/functions-example/tree/master/csharp)
- Für die Authentifizierung wird vor das Backend ein Login Proxy geschaltet
- Datenbank: PostgreSQL
- Wenn Performance nicht passt, muss NoSQL evaluiert werden
