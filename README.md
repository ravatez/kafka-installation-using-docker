![Logo](https://miro.medium.com/v2/resize:fit:500/1*rnircEdbpU9_-pTMXlyqLg.png)

# Installation Of Apache Kafka Using Docker

Apache Kafka is an open-source platform designed for stream processing, emphasizing a robust publish-subscribe messaging system tailored for real-time data pipelines and streaming applications.

Key components of Kafka include:

- Producer: Responsible for sending data to Kafka topics, which can be various applications or systems generating valuable data.
- Consumer: Receives data from Kafka topics for processing; consumers can be applications or services acting on the data.
- Broker: Manages storage, distribution, and retrieval of data, serving as an intermediary between producers and consumers.
- ZooKeeper: Manages and coordinates Kafka brokers, aiding in configuration maintenance, leader election, and broker failure detection.

Kafka's data organization:
- Topic: Represents a named stream of data within Kafka, categorizing data and serving as channels for publishing and subscribing.
- Partitions: Divides topics for parallelism and increased throughput, with each partition being ordered and immutable.
- Offset: A unique identifier for each message within a partition, aiding consumers in tracking consumed messages.

Additional features include:
- Consumer Groups: Organizes consumers into groups for independent data processing, facilitating load balancing and fault tolerance.
- Cluster: Comprises a group of computers or servers, each running Kafka brokers, offering fault tolerance and scalability.
## Installation

#### Using Docker for Kafka Setup
- You can also download and install the Docker Desktop application to run Docker in the background.
- Here’s a sample **[docker-compose.yml](https://github.com/ravatez/kafka-installation/blob/main/docker-compose.yml)** file for setting up Kafka and ZooKeeper containers:

#### To set up Kafka using Docker : 
1. Go inside the Kafka installation folder

```bash 
cd /opt/kafka_<version>/bin
```
2. Run this command to launch Kafka and ZooKeeper services.

```bash 
docker exec -it <kafka_conatiner_id> /bin/sh
``` 

3. Create Kafka topic
```bash 
kafka-topics.sh --create --topic mytopic --bootstrap-server localhost:9092 --partitions 1 --replication-factor 1
```
4. Start Producer app (CLI)
```bash 
kafka-console-producer.sh --topic work --bootstrap-server localhost:9092
```
5. Start consumer app (CLI)
```bash 
kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic mytopic --from-beginning
```
6. Stop services: 
```bash
docker-compose down
```

Thus, the connection is established between the Producer & Consumer, you can test it and send messages within the terminals through docker kafka.
## Running Kafka-Enabled Applications Using Docker

Running Kafka-enabled applications within Docker can also be streamlined:

1. Build a Docker container for your Kafka-enabled application.
2. Configure your application to utilize Kafka’s connection details and topic names.
3. Launch your Kafka-enabled application container using Docker.

## Support

For support, email ravatez@gmail.com

## 🔗 Links
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ravatez/)



# Thank You! 🧑🏼‍💻
