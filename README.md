# Observability

## Prometheus

From metrics to insight: Power your metrics and alerting with the leading
open-source monitoring solution.

-  Dimensional data: Prometheus implements a highly dimensional data model. Time series are identified by a metric name and a set of key-value pairs.

-  Powerful queries: PromQL allows slicing and dicing of collected time series data in order to generate ad-hoc graphs, tables, and alerts.

-  Great visualization: Prometheus has multiple modes for visualizing data: a built-in expression browser, Grafana integration, and a console template language.

-  Efficient storage: Prometheus stores time series in memory and on local disk in an efficient custom format. Scaling is achieved by functional sharding and federation.

-  Simple operation: Each server is independent for reliability, relying only on local storage. Written in Go, all binaries are statically linked and easy to deploy.

-  Precise alerting: Alerts are defined based on Prometheus's flexible PromQL and maintain dimensional information. An alertmanager handles notifications and silencing.

-  Many client libraries: Client libraries allow easy instrumentation of services. Over ten languages are supported already and custom libraries are easy to implement.

-  Many integrations: Existing exporters allow bridging of third-party data into Prometheus. Examples: system statistics, as well as Docker, HAProxy, StatsD, and JMX metrics. 

### Architecture

![Architecture](https://github.com/JessiiPer/fullcycle-prometheus/blob/master/docs/prometheus-architecture.png)

## CADVISOR

cAdvisor (short for container Advisor) analyzes and exposes resource usage and performance data from running containers. cAdvisor exposes Prometheus metrics out of the box

- Added container cadvidor in docker-compoder and added a job in prometheus for cadvisor. In this way, it is possible export metrics of the containers (example: container cpu load average, container cpu usage, memory, etc)

![Prometheus](https://github.com/JessiiPer/fullcycle-prometheus/blob/master/docs/prometheus.png)

## Metrics

Metrics are quantifiable measures used to analyze the outcome of a specific process, action or strategy.

### Metrics Types

#### **Counter**

The COUNT metric submission type represents the total number of event occurrences in one time interval

- Examples:
    - Number of visits to a website
    - Quantity of sale
    - Amount of errors

#### **Gauge**

The GAUGE metric submission type represents a snapshot of events in one time interval. This representative snapshot value is the last value submitted to the Agent during a time interval. A GAUGE can be used to take a measure of something reporting continuously

- Examples:
    -  the available disk space or memory used
    - number of online users
    - number of active servers

#### **Histogram**

Histogram metrics are useful to represent a distribution of measurements. They are often used to measure request duration or response size. Histograms divide the entire range of measurements into a set of intervals

- Examples:
    - Website purchases by age range
    - Response time

Generated dashboard in grafana with these type metrics:

![grafana](https://github.com/JessiiPer/fullcycle-prometheus/blob/master/docs/grafana.png)

