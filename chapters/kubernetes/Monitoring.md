# Monitoring

Metrics that should be scraped by Prometheus:

* number of running Docker containers
  * keep in mind that there are containers running Kubernetes services
* free disk space
* CPU load
* network traffic

## Prometheus

**Prometheus**
* https://prometheus.io/
* https://github.com/prometheus/prometheus

> Prometheus is a systems and service monitoring system. It collects metrics from configured targets at given intervals, evaluates rule expressions, displays the results, and can trigger alerts if some condition is observed to be true.

**Thanos**
* https://github.com/improbable-eng/thanos
* https://improbable.io/games/blog/thanos-prometheus-at-scale

> Thanos is a set of components that can be composed into a highly available metric system with unlimited storage capacity. It can be added seamlessly on top of existing Prometheus deployments and leverages the Prometheus 2.0 storage format to cost-efficiently store historical metric data in any object storage while retaining fast query latencies. Additionally, it provides a global query view across all Prometheus installations and can merge data from Prometheus HA pairs on the fly.