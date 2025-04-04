# Kafka
Video Link: [Apache Kafka Crash Course | What is Kafka?](https://youtu.be/ZJJHm_bd9Zo)
## Prerequisite
- Knowledge
  - Node.JS Intermediate level
  - Experience with designing distributed systems
- Tools
  - Node.js: [Download Node.JS](https://nodejs.org/en)
  - Docker: [Download Docker](https://www.docker.com)
  - VsCode: [Download VSCode](https://code.visualstudio.com)

## Commands
- Start Zookeper Container and expose PORT `2181`.
```bash
docker run -p 2181:2181 zookeeper
```
- Start Kafka Container, expose PORT `9092` and setup ENV variables.
```bash
docker run -p 9092:9092 \
-e KAFKA_ZOOKEEPER_CONNECT=<PRIVATE_IP>:2181 \
-e KAFKA_ADVERTISED_LISTENERS=PLAINTEXT://<PRIVATE_IP>:9092 \
-e KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR=1 \
confluentinc/cp-kafka
```

## Running Locally
To start this project, follow these steps:

1. **Start Zookeeper and Kafka using Docker Compose**:
   Run the following command in the terminal to start the Zookeeper and Kafka containers:
   ```bash
   docker-compose up
   ```

2. **Create the Kafka topic**:
   Run the following command to create the Kafka topic using the `admin.js` script:
   ```bash
   node admin.js
   ```

3. **Run Multiple Consumers**:
   ```bash
   node consumer.js <GROUP_NAME>
   ```

4. **Create Producer**:
   ```bash
   node producer.js
   ```

Example commands to produce messages:
```bash
> tony south
> tony north
```
