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

## Pushing to GitHub
To create a repository on GitHub and push your code there, follow these steps:

1. **Create a new repository on GitHub**:
   - Go to [GitHub](https://github.com) and log in.
   - Click on the `+` icon in the top right corner and select `New repository`.
   - Enter a repository name, description (optional), and choose visibility (public or private).
   - Click `Create repository`.

2. **Initialize Git in your project directory**:
   Run the following commands in the terminal:
   ```bash
   cd /home/user/Downloads/old projects/1study/kafka
   git init
   git add .
   git commit -m "Initial commit"
   ```

3. **Add the remote repository and push your code**:
   Replace `<USERNAME>` with your GitHub username and `<REPO_NAME>` with the name of your repository.
   ```bash
   git remote add origin https://github.com/<USERNAME>/<REPO_NAME>.git
   git branch -M main
   git push -u origin main
   ```

4. **Verify the push**:
   Go to your repository on GitHub and verify that your code has been pushed successfully.