# Production Ready Kubernetes Cluster

In order to run a Kubernetes cluster reliably in production it has to be
resilient against:

* misbehaving Applications
* intentionally or unintentionally shutting down of
  * pods
  * worker nodes (distribute across AZs)
  * the cluster
* expected/planned or unexpected/unplanned increase of workloads (scaling, resource constraints and quotas)
* attacks from outside
  * pod to pod SSL (service mesh)
  * encrypt secrets
* unwanted interservice communication (service mesh)

The current status of the Kubernetes cluster has to be monitored permanently and extensively.

In case of the Kubernetes cluster not being able to fix issues by itself someone has to be alerted.

The production readiness can be validated through execution of tests.

There will be no outage when updating

* applications
* worker nodes
* Kubernetes masters
* Kubernetes version

Applications and worker nodes are updated using a deployment tool (GitOps).
This make changes auditable.

1. Everything that can be described must be stored in git
2. Kubectl should not be used directly
3. Use a Kubernetes controller that follows an operator pattern

Observability


https://eng.lyft.com/awesome-tech-specs-86eea8e45bb9