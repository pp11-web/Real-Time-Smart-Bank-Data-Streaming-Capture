
# Real-Time Smart Bank Data Streaming Capture

## Overview

The **Real-Time Smart Bank Data Streaming Capture** project is a comprehensive data analytics pipeline designed to handle real-time streaming of bank data for fraud detection and customer experience enhancement. This project utilizes cutting-edge technologies like **Docker**, **Kafka**, **Apache Spark**, and **Flask**, along with IoT integration for capturing and processing data from diverse sources such as sensors, transaction data, and application data.

## Key Features

- **Real-Time Data Processing**: Data is ingested, processed, and analyzed in real-time using **Kafka** and **Apache Spark**.
- **Fraud Detection**: Incorporates logic to detect fraudulent patterns using techniques like tokenization, K-anonymity, and Locality-Sensitive Hashing (LSH).
- **IoT Sensor Integration**: Processes sensor data using **AWS IoT Core** and **AWS Timestream** for visualization in **Grafana**.
- **Multi-Source Data Streaming**: Streams data from multiple sources—transactions, applications, and sensors—for robust analytics.
- **Data Anonymization**: Ensures privacy compliance by anonymizing sensitive financial data.
- **Visualization**: Provides detailed dashboards for data analysis using **Grafana**, **Kibana**, and **Flask**.

## Architecture Diagram

![Architecture Diagram](./Images/Architecture%20Diagram.jpg)

The architecture includes multiple components:
- **IoT Sensor Data**: Captured via AWS IoT Core and processed through AWS Lambda and Timestream for fraud detection and visualization.
- **Transaction and Application Data**: Ingested through Kafka and processed using **Apache Spark**, **MongoDB**, and **Elasticsearch** for visualization in Kibana and Flask.

## Workflows

### Workflow 1 (Sensor Data)

![Workflow 1 (Sensor)](./Images/Workflow-1%20(Sensor).jpg)

1. **Data Generation**: Sensor data is generated, with noise added and data encrypted.
2. **IoT Processing**: Data is processed through AWS IoT Core, creating rules and schema, and is stored in Timestream.
3. **Visualization**: Data is visualized using Grafana and ElasticSearch after being processed via Python.

### Workflow 2 (Transaction & Application Data)

![Workflow 2 (Transaction & App)](./Images/Workflow%20-2%20(Transaction%20&%20App).jpg)

1. **Data Generation**: Both transaction and application data are generated, with noise added.
2. **Data Processing**: The data is processed through Kafka, Spark sessions are used for tokenization, and anonymization is ensured through K-anonymity.
3. **Visualization**: Data is presented in Flask and visualized in Kibana.

## Technology Stack

- **Docker**: Containerization and environment setup.
- **Kafka**: Streaming platform for real-time data ingestion.
- **Apache Spark**: Real-time data processing engine.
- **AWS IoT Core**: Captures sensor data and forwards it for further processing.
- **AWS Timestream**: Time-series data management for IoT data.
- **Flask**: Web application framework for building dashboards.
- **Elasticsearch**: Used for search and analytics across the data pipeline.
- **Grafana & Kibana**: For data visualization and analytics dashboards.

## Installation

1. **Clone the repository**:

    ```bash
    git clone https://github.com/pp11-web/Real-Time-Smart-Bank-Data-Streaming-Capture.git
    ```

2. **Set up Docker containers**:
    - Ensure Docker is installed on your system.
    - Build and run the Docker containers for Kafka, Spark, Flask, etc.

    ```bash
    docker-compose up --build
    ```

3. **Configure AWS IoT Core**:
    - Set up the IoT rules and connections to capture sensor data.
    - Configure AWS Lambda and Timestream for real-time processing.

4. **Run Flask**:

    ```bash
    python app.py
    ```

5. **Access the dashboards**:
    - **Grafana**: For IoT sensor data visualization.
    - **Kibana**: For transaction and application data analytics.
    - **Flask**: For additional data visualization and fraud detection results.

## Results

- **Sensor Data Visualization**: Grafana dashboards displaying real-time IoT sensor data.
- **Transaction and Application Data Visualization**: Kibana dashboards for fraud detection and detailed analysis.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

Special thanks to the team for their hard work and dedication in developing this comprehensive real-time data analytics platform.

