|Name|Data model|Pro|Kontra|Skalierbarkeit
|:-|:-|:-|:-|:-|
|Mysql|Structured|-Kennt jeder kann jeder mit umgehen|||
|Postgresql|Structured|-Kennt jeder kann jeder mit umgehen,performanter als mysql|||
|Mongodb|Document||||
|Cassandra|Document||||
|Arangodb|Key/Value+Document+Graph|-IntegrierteAPI/microservices,Sehr gute Fulltext Search/search engine,-[performant](https://www.arangodb.com/2018/02/nosql-performance-benchmark-2018-mongodb-postgresql-orientdb-neo4j-arangodb/)|-Query language mit der wenige im team gearbeitet haben, aber sehr ähnlich zus sql: [AQL](https://www.arangodb.com/why-arangodb/sql-aql-comparison/)|[Master/Master](https://www.arangodb.com/why-arangodb/cluster/)|
