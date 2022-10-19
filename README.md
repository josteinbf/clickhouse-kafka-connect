# ClickHouse Kafka Connect Sink

clickhouse-kafka-connect is the official Kafka Connect sink connector for [ClickHouse](https://clickhouse.com/).

## Main Features
- Shipped with out of the box exactly-once semantics. This is powered by a new ClickHouse core feature named KeeperMap (used a state store by the connector) and allows to keep the architecture minimalistic.
- Support for 3rd party statestores: Currently defaults to In-memory but can use KeeperMap (Redis to be added soon).
- Core integration: Built, maintained and supported by ClickHouse
- Tested continuously against ClickHouse Cloud
- Handling of Schema & Schemaless out of the box
- Support for most major datatypes of ClickHouse (more to be added soon)

## Setup
- Download the latest release or run ./gradlew createConfluentArchive to create your own archive
- Copy & Unzip the Archive Of ClickHouse Sink to Connect Plugin directory (Can be found at "/usr/share/java,/usr/share/confluent-hub-components") (clickhouse-kafka-connect-1.8.0-SNAPSHOT.zip)
- Restart connect worker to load ClickHouse Sink
- Open Control Center 
- Add ClickHouseSink & Configure 


## Current Limitations 
- Batch size is inherited from the Kafka Consumer properties   
- Destination table name needs to match the source topic name
- Destination ClickHouse table needs to be already created in ClickHouse