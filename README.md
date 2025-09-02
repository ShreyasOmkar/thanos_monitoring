# Thanos_monitoring
Thanos provides a global query view, high availability, data backup with historical, cheap data access as its core features in a single binary.

Those features can be deployed independently of each other. This allows you to have a subset of Thanos features ready for immediate benefit or testing, while also making it flexible for gradual roll outs in more complex environments.

# Prometheus 
Thanos is based on Prometheus. With Thanos, Prometheus always remains as an integral foundation for collecting metrics and alerting using local data.

# Components 
Following these philosophies, Thanos is comprised of a set of components where each fulfills a specific role.

- Receiver: receives data from Prometheus’s remote write write-ahead log, exposes it, and/or uploads it to cloud storage.
- Store Gateway: serves metrics inside of a cloud storage bucket.
- Querier/Query: implements Prometheus’s v1 API to aggregate data from the underlying components.
- Compactor: compacts, downsamples and applies retention on the data stored in the cloud storage bucket.
- Ruler/Rule: evaluates recording and alerting rules against data in Thanos for exposition and/or upload.

There are other two components which we did not opt for in our application cause the metrics was our main goal to achieve so the left out components are:
- Sidecar: connects to Prometheus, reads its data for query and/or uploads it to cloud storage.
- Query Frontend: implements Prometheus’s v1 API to proxy it to Querier while caching the response and optionally splitting it by queries per day.

# Deploy
Deploy to your local to check with the deployment of the containers using below command in the src or where the compose file resides
- sudo docker-compose up -d 
