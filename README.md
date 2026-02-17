# 🔄 Realtime Data Streaming | End-to-End Data Engineering Project

An end-to-end data engineering pipeline that orchestrates data ingestion, processing, and storage using a powerful, modern tech stack. This project demonstrates a complete real-time data workflow, from generating source data to storing processed results, with all components containerized using Docker for easy deployment and scalability.

---

## 🏗️ System Architecture

The project is designed with the following components, creating a robust and scalable data pipeline:

1.  **Data Source**: We use the `randomuser.me` API to generate random user data, simulating a live data stream for our pipeline.
2.  **Apache Airflow**: Responsible for orchestrating the entire pipeline. It fetches data from the API and stores it in a PostgreSQL database.
3.  **Apache Kafka & Zookeeper**: Used for real-time streaming. Zookeeper manages the Kafka cluster, while Kafka streams the data from PostgreSQL to the processing engine.
4.  **Control Center & Schema Registry**: These tools help in monitoring the Kafka streams and managing the data schemas.
5.  **Apache Spark**: The processing engine. It consumes data from Kafka, processes it (master node directing worker nodes), and prepares it for storage.
6.  **Cassandra**: The final destination for the processed data, providing a scalable and highly available storage solution.

---

## ✨ What You'll Learn

- 🔧 **Pipeline Orchestration**: Setting up and managing a data pipeline with **Apache Airflow**.
- 📡 **Real-time Streaming**: Implementing real-time data streams with **Apache Kafka**.
- 🤝 **Distributed Coordination**: Managing distributed systems with **Apache Zookeeper**.
- ⚙️ **Data Processing**: Performing data processing and transformations using **Apache Spark**.
- 💾 **Data Storage**: Implementing storage solutions with **Cassandra** and **PostgreSQL**.
- 🐳 **Containerization**: Using **Docker** to containerize your entire data engineering setup for easy deployment and scalability.

---

## 🧰 Technology Stack

| Category                   | Technologies                                                                |
| -------------------------- | --------------------------------------------------------------------------- |
| **Workflow Orchestration** | Apache Airflow                                                              |
| **Programming Language**   | Python                                                                      |
| **Streaming & Messaging**  | Apache Kafka, Apache Zookeeper, Kafka Schema Registry, Kafka Control Center |
| **Data Processing**        | Apache Spark (Master & Worker)                                              |
| **Databases**              | Cassandra, PostgreSQL                                                       |
| **Containerization**       | Docker, Docker Compose                                                      |
| **Data Source**            | `randomuser.me` API                                                         |

---

## 🛠️ Getting Started

Follow these steps to get the pipeline running on your local machine.

### 📋 Prerequisites

- [Docker](https://www.docker.com/products/docker-desktop/) and [Docker Compose](https://docs.docker.com/compose/install/) installed on your system.
- `git` command-line tool.

### 🔧 Installation & Setup

1.  **Clone the repository**

    ```bash
    git clone https://github.com/airscholar/data-engineering.git
    ```

2.  **Navigate to the project directory**

    ```bash
    cd data-engineering
    ```

3.  **Start all services with Docker Compose**
    This command will build and start all the containers defined in the `docker-compose.yml` file (Airflow, Kafka, Spark, Cassandra, etc.).
    ```bash
    docker-compose up
    ```
    _(You can add the `-d` flag to run in detached mode)_.

### ▶️ Running the Pipeline

Once all services are up and running, the pipeline should automatically start as defined by the Airflow DAGs. You can monitor the workflow and check logs through the respective web UIs of the services (e.g., Airflow webserver, Kafka Control Center).
