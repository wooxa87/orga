# Gesamtarchitektur mit Functions-as-a-Service


## Functions-as-a-service wird ersetzt durch eine Eigene api + https://github.com/SafeMarket-WirVsVirus/orga/blob/master/architekturvorschlaege/workflowmanagement.md


## Aufbau:
Siehe faas Aufbau von https://github.com/SafeMarket-WirVsVirus/orga/blob/master/architekturvorschlaege/faas-architecture.md, dort anstatt des faas, ähnliche Funktion bloß  mit eigener API gebaut (api endpoint pro Funktion->in ne redis/rabittmq queue-> worker arbeiten diese ab) 
-Via kubernetes ein automatisches skalieren von workern und redis/rabbitmq, sollte daher egal auf welchem hoster laufen solange ein kubernetes System existiert
https://github.com/SafeMarket-WirVsVirus/orga/blob/master/architekturvorschlaege/faas-architecture.md

Vorteile:
- Da Python ne relativ schnelles prototyping besonders im Bereich von Datenverarbeitung (asnychrones i/o so ca 500-1000 io anfragen gleichzeitig pro core, sehr viele robuste libarys zur Datenverarbeitung(pandas, numpy, tensorflow, scikit-learn) 
- Gut skalierbar(Mozilla ist bei nen paar Millionen CPU Jobs pro Tag) 
- Plattform und Architektur unabhängig (wird auf nem Laptop ohne docker genauso wie in kubernetes in der cloud laufen) 

Nachteile:
- Mehr Aufwand 
- Bindung als python als Programmiersprache
- Ineffizienz in cpu bound Sachen die nicht über spezielle  libarys (die die die c-api nutzen z. B. Numpy tensorflow etc) gehandelt werden aufgrund von Python als Programmiersprache.

Könnte man auch wie Caas aufziehen und dort einzelne Funktionsgruppen in einzelne container zieht mit eigener queue zieht.
Vorteile:
  - Bessers Monitoring der einzelnen Queues
  - Andere Programmiersprachen möglich
  
Nachteile:
  - Komplexer in der Architektur
  - Evt schlechter Wartbar wenn leute wegfallen die sachen in einer anderen Programmiersprache geschrieben hat die keiner aus dem Team kann


