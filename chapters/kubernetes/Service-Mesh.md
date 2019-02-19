# Service Mesh

[Service mesh data plane vs. control plane][1]
[Microservices Patterns With Envoy Sidecar Proxy: The series][2]

## Envoy

[Envoy][3] Proxy is a small, lightweight, native/C++ application that enables the following features (and more!):

* Service discovery
* Adaptive routing / client side load balancing
* Automatic retries
* Circuit breakers
* Timeout controls
* Back pressure
* Rate limiting
* Metrics/stats collection
* Tracing
* Request shadowing
* Service refactoring / request shadowing
* TLS between services
* Forced service isolation / outlier detection

## Istio

[1]:https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc
[2]:https://blog.christianposta.com/microservices/00-microservices-patterns-with-envoy-proxy-series/
[3]:https://www.envoyproxy.io