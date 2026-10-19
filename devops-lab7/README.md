# Real-Time Delivery Monitoring and Alerting

## Objective
Set up a real-time delivery monitoring system using Python, Prometheus, Grafana, Docker, and Jenkins to monitor delivery metrics and configure alerts.

## Prerequisites
- Windows 11
- Docker Desktop
- Python 3.10 or higher
- Prometheus
- Grafana
- Jenkins

## Setup and Execution Steps

### 1. Start Docker Services
Ensure Docker Desktop is running. Start the Prometheus, Grafana, and Jenkins containers if they are not already running.

```bash
docker ps
```

### 2. Run the Python Metrics Application

Navigate to the project directory:

```cmd
cd C:\Users\harsh\delivery_monitoring
```

Install the required library:

```cmd
python -m pip install prometheus-client
```

Start the application:

```cmd
python delivery_metrics.py
```

The application simulates delivery metrics and exposes them at:

http://localhost:8000/metrics

Keep the application running.

### 3. Verify Prometheus

Open:

http://localhost:9090

Navigate to **Status → Targets** and verify that the Prometheus and delivery service targets are UP.

### 4. Verify Alert Rules

Open the Prometheus Alerts page and check the configured rules:

- `HighPendingDeliveries`
- `HighAverageDeliveryTime`

The rules should be loaded. An alert fires only when its configured condition is satisfied.

### 5. Open Grafana

Open:

http://localhost:3000

Navigate to the **ZAPPTTO Delivery Monitoring** dashboard.

Verify the following panels:

1. Total Deliveries
2. Pending Deliveries
3. On-the-Way Deliveries
4. Average Delivery Time

Ensure Prometheus is configured as the Grafana data source.

### 6. Verify Jenkins Pipeline

Open:

http://localhost:8080

Select the `Delivery-Monitoring-Pipeline` job and click **Build Now**.

Check the Console Output for:

```text
Finished: SUCCESS
```

The current pipeline demonstrates successful execution of its configured stages.

## Expected Results

- Delivery metrics are exposed by the Python application.
- Prometheus collects the configured metrics.
- Alert rules are loaded in Prometheus.
- Grafana displays delivery monitoring metrics.
- Jenkins executes the pipeline successfully.

## Technologies Used

Python · Prometheus · Grafana · Docker · Jenkins
