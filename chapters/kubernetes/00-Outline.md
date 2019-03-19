# Kubernetes

> [Kubernetes (k8s)](https://kubernetes.io/) is an open-source system for automating deployment, scaling, and management of containerized applications.

## Chapters

* [01 Installation](Installation.md)
* [02 Backup and Restore](Backup-and-Restore.md)
* [03 Worker Nodes](Worker-Nodes.md)
* [04 Service Mesh](Service-Mesh.md)
* [05 Security](Security.md)
* [06 Scaling](Scaling.md)
* [07 Helm](Helm.md)
* [08 Helmfile](Helmfile.md)
* [09 Chaos Engineering](Chaos-Engineering.md)
* [10 Operators](Operators.md)
* [11 Monitoring]()

## Open Topics

* What is actually happening when I delete a node?

## More Reading

* [Amazon EKS Workshop](https://eksworkshop.com)
* [Awsome Kubernetes - Testing](https://github.com/ramitsurana/awesome-kubernetes#testing)
* [Kubernetes: The Complete Guide](https://www.aquasec.com/wiki/display/containers/Kubernetes+Guide)
  * [Kubernetes Operations](https://www.aquasec.com/wiki/display/containers/Kubernetes+Operations)
    * [Kubernetes in Production](https://www.aquasec.com/wiki/display/containers/Kubernetes+in+Production)
      * Distribution of pods across AZs
      * Creating and maintaining TLS certificates
      * set `--kube-reserved` and `--system-reserved` in kublet
      * enforce resource limits
      * set default limits
      * add a small [systemd unit to run kubectl drain on shutdown](https://github.com/zalando-incubator/kubernetes-on-aws/blob/449f8f3bf5c60e0d319be538460ff91266337abc/cluster/userdata-worker.yaml#L92)

## Videos

* [June 2018 Online Meetup: Kubernetes Networking Master Class](https://www.youtube.com/watch?v=GXq3FS8M_kw)
* [Kubernetes Master Class: Building an Enterprise Kubernetes Strategy](https://www.youtube.com/watch?v=djTFhT33cz0)
* [Zalando - Kubernetes Deployments: A “Hands-Off” Approach](https://www.youtube.com/watch?v=e0DruWvY-ME)