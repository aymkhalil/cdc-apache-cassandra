# Cassandra CDC Replication using Apache Pulsar.

-The Cassandra replication requires:
* A message producer deployed as a JVM agent on each Cassandra data node.
* A Cassandra Source Sonnector deployed in the streaming platform.

| Streaming platform | Cassandra v3.x producer | Cassandra v4.x producer  | Source connector |
| ---                | ---                     | ---                      | ---              |
| Apache Pulsar      | [producer-v3-pulsar](producer-v3-pulsar) | [producer-v4-pulsar](producer-v4-pulsar) | [source-pulsar](source-pulsar) |

![Cassandra-source-connector](docs/modules/ROOT/assets/images/cassandra-source-connector.png)

## Limitations

* Does not replay batch updates
* Does not manage table truncates
* Does not sync data available before starting the CDC producer.
* Does not manage TTL
* Does not support range deletes

## Build from the sources

    ./gradlew assemble
