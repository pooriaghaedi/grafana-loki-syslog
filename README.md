# Grafana Loki Syslog RFC3164 Integration

This repository contains a setup to collect, parse, and visualize syslog messages using **Grafana Loki** and **Syslog-ng** with **Promtail** as the log shipper. It helps centralize log management for devices emitting logs in RFC3164 format, providing efficient log aggregation and querying via Grafana.

## Stack Components

- **Syslog-ng**: 
- **Promtail**: 
- **Grafana Loki**:
- **Grafana**:

## Project Structure

- `loki/`: Contains configuration files for the Loki instance.
- `promtail/`: Configuration for Promtail to collect syslog logs.
- `syslog-ng/`: Syslog-ng setup to receive and forward logs.
- `docker-compose.yaml`: Docker setup for deploying the stack.

## Setup Instructions

1. Clone this repository:
   ```bash
   git clone https://github.com/pooriaghaedi/grafana-loki-syslog.git
   cd grafana-loki-syslog
   ```

2. Deploy the stack using Docker Compose:
   ```bash
   docker-compose up -d
   ```

3. Configure your devices to send syslog messages to the Syslog-ng instance.
   ```bash
   docker run -d --log-driver=syslog --log-opt syslog-address=tcp://127.0.0.1:601 nginx
   ```

4. Access Grafana at `http://localhost:3000`, and configure Loki as a data source.

## Syslog Format Handling

- **Syslog-ng** is used to handle syslog messages in the RFC3164 format.
- **Promtail** is configured to parse logs in the RFC5424 format.

## Contributions

Feel free to submit issues or contribute via pull requests to enhance the setup or add new features.

## License

This project is open-source under the MIT License.