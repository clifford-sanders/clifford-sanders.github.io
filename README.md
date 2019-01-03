## Welcome

Since 2004 I've been working as Developer, Build and Release Engineer and IT Infrastructure Engineer and always wanted document everything that I learned while solving challenges.

## Topics

### Kubernetes

> [Kubernetes (k8s)](https://kubernetes.io/) is an open-source system for automating deployment, scaling, and management of containerized applications.

#### Installation

* Setting up control plane on [Amazon Elastic Container Service for Kubernetes (Amazon EKS)](https://aws.amazon.com/eks/)
* Setting up control plane on [Amazon Elastic Container Service (Amazon ECS)](https://aws.amazon.com/ecs/) using [kops](https://github.com/kubernetes/kops)
* Setting up worker nodes using [AWS CloudFormation](https://aws.amazon.com/cloudformation/)
* Setting up [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

#### Backup and Restore

> [Heptio Ark](https://github.com/heptio/ark) is a utility for managing disaster recovery, specifically for your Kubernetes cluster resources and persistent volumes. 

#### Disable swapping

We encountered problems when starting Jenkins. The worker node immediatly started to swap making it unusable.

After waiting for a long time we got a timeout and Kubernetes tried to start Jenkins on another worker node.

Setting the swappiness to 0 didn't help.

### Terraform
#### Installation

### Git
#### Installation

### Monitoring

* Prometheus
* Graylog
* Grafana
* Icinga
