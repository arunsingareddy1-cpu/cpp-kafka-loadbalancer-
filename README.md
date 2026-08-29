
# C++ Kafka Load Balancer

A real-time distributed system project built using C++, Kafka, Docker, and CMake.

## Project Overview

This project demonstrates how to build a distributed backend system with multiple C++ servers, a load balancer, and Apache Kafka for asynchronous communication.

The load balancer distributes incoming client requests between multiple backend servers. Backend servers process requests and publish events to Kafka. Kafka consumers then process those events asynchronously.

## Architecture

```text
                         CLIENT
                            |
                            v
                   +----------------+
                   | LOAD BALANCER  |
                   |      C++       |
                   +-------+--------+
                           |
              +------------+------------+
              |                         |
              v                         v
       +-------------+           +-------------+
       | C++ Server1 |           | C++ Server2 |
       +------+------+           +------+------+
              |                         |
              +------------+------------+
                           |
                           v
                    +-------------+
                    |    KAFKA    |
                    +------+------+ 
                           |
              +------------+------------+
              |                         |
              v                         v
        +-----------+             +-----------+
        |Consumer 1 |             |Consumer 2 |
        +-----------+             +-----------+
```

## Features

* C++ backend servers
* Custom load balancer
* Round Robin algorithm
* Health checks
* Automatic failover
* Kafka producer
* Kafka consumer
* Kafka consumer groups
* Asynchronous event processing
* Docker containerization
* CMake build system
* Logging
* Multi-threading

## Technologies Used

| Technology     | Purpose                      |
| -------------- | ---------------------------- |
| C++17          | Core application development |
| Apache Kafka   | Event streaming              |
| librdkafka     | Kafka C++ client             |
| Docker         | Containerization             |
| Docker Compose | Multi-container management   |
| CMake          | Build system                 |
| Git            | Version control              |
| Linux          | Development environment      |

## Project Structure

```text
cpp-kafka-load-balancer/
│
├── README.md
├── .gitignore
├── docker-compose.yml
│
├── load-balancer/
│   ├── src/
│   │   ├── main.cpp
│   │   ├── LoadBalancer.cpp
│   │   └── HealthCheck.cpp
│   │
│   ├── include/
│   ├── CMakeLists.txt
│   └── Dockerfile
│
├── server1/
│   ├── src/
│   │   └── main.cpp
│   ├── CMakeLists.txt
│   └── Dockerfile
│
├── server2/
│   ├── src/
│   │   └── main.cpp
│   ├── CMakeLists.txt
│   └── Dockerfile
│
├── kafka-producer/
│   ├── producer.cpp
│   ├── CMakeLists.txt
│   └── Dockerfile
│
├── kafka-consumer/
│   ├── consumer.cpp
│   ├── CMakeLists.txt
│   └── Dockerfile
│
├── config/
│   └── config.yaml
│
└── tests/
    └── load_test.cpp
```

## Load Balancing Flow

```text
Request 1 → Server 1
Request 2 → Server 2
Request 3 → Server 1
Request 4 → Server 2
```

The initial load balancing algorithm used is Round Robin.

## Kafka Flow

```text
Client Request
      |
      v
Backend Server
      |
      v
Kafka Producer
      |
      v
Kafka Topic
      |
      v
Kafka Consumer
      |
      v
Process Event
```

## Learning Goals

This project helps understand:

* TCP/IP networking
* Socket programming
* HTTP communication
* Load balancing
* Distributed systems
* Multithreading
* Kafka architecture
* Producer and consumer concepts
* Docker
* CMake
* Git workflow

## Development Roadmap

### Phase 1: Project Setup

* [ ] Create Git repository
* [ ] Setup project structure
* [ ] Configure CMake

### Phase 2: Backend Servers

* [ ] Create C++ Server 1
* [ ] Create C++ Server 2
* [ ] Test HTTP communication

### Phase 3: Load Balancer

* [ ] Create C++ load balancer
* [ ] Implement Round Robin
* [ ] Implement weighted Round Robin
* [ ] Implement least connections

### Phase 4: Health Checks

* [ ] Server health monitoring
* [ ] Detect failed servers
* [ ] Automatic failover

### Phase 5: Kafka

* [ ] Setup Kafka
* [ ] Create Kafka topics
* [ ] Implement C++ producer
* [ ] Implement C++ consumer
* [ ] Configure consumer groups

### Phase 6: Docker

* [ ] Create Dockerfiles
* [ ] Create Docker Compose
* [ ] Run complete system

### Phase 7: Testing

* [ ] Load testing
* [ ] Failure testing
* [ ] Kafka message testing

## How to Run

Instructions will be added as the project is developed.

```bash
git clone <repository-url>
cd cpp-kafka-load-balancer
```

## Future Improvements

* Prometheus monitoring
* Grafana dashboards
* Kubernetes deployment
* Multiple Kafka brokers
* Service discovery
* Rate limiting
* Authentication
* HTTPS support

## Author

Arun Singareddy

## License

MIT License
