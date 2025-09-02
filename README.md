# 📊 Thanos Monitoring

This repository documents the design and implementation of a monitoring system using [**Thanos**](https://github.com/thanos-io/thanos), an open-source project built to provide highly available Prometheus monitoring at scale.

Thanos extends Prometheus with long-term storage, global querying, high availability, and cost-efficient historical data access — all through a modular and flexible architecture.

---

## 🔗 Reference Repository

We’ve built our monitoring system based on [**thanos-io/thanos**](https://github.com/thanos-io/thanos?tab=readme-ov-file), leveraging its powerful ecosystem of components to suit our metrics monitoring needs.

---

## 🧩 Components Used

Our monitoring setup includes the following **core Thanos components**:

- **Receiver**  
  Collects data from Prometheus using remote write and optionally uploads it to cloud storage.

- **Store Gateway**  
  Reads metrics from cloud storage and exposes them for querying.

- **Querier (Query)**  
  Aggregates and exposes metrics from multiple data sources via the Prometheus API.

- **Compactor**  
  Performs compaction, downsampling, and retention on historical data stored in object storage.

- **Ruler (Rule)**  
  Evaluates Prometheus-style recording and alerting rules based on long-term storage data.

These components were selected to meet the primary goal of **reliable metrics collection, querying, and historical analysis**.

---

## 🚫 Components Not Used

The following Thanos components were **not included** in our implementation, as they were not essential to our current monitoring objectives:

- **Sidecar**  
  Typically used to connect directly to a Prometheus instance for short-term data querying and uploading to storage. In our case, `Receiver` covered the required functionality.

- **Query Frontend**  
  Provides caching and query sharding capabilities, which were not required for our scale or performance needs at this time.

---

## 🚀 Getting Started

```bash
# Start Thanos monitoring setup 
sudo docker-compose up -d
