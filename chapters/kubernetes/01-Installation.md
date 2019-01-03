# Installation

* Setting up control plane on [Amazon Elastic Container Service for Kubernetes (Amazon EKS)](https://aws.amazon.com/eks/)
  * [Getting Started with Amazon EKS](https://docs.aws.amazon.com/eks/latest/userguide/getting-started.html)
  * [Manage Amazon EKS with Terraform](https://learn.hashicorp.com/terraform/aws/eks-intro)
* Setting up control plane on [Amazon Elastic Container Service (Amazon ECS)](https://aws.amazon.com/ecs/) using [kops](https://github.com/kubernetes/kops)
* Setting up worker nodes using [AWS CloudFormation](https://aws.amazon.com/cloudformation/)

## kubectl

Links:
* [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
* [Configure kubectl for Amazon EKS](https://docs.aws.amazon.com/eks/latest/userguide/configure-kubectl.html)
* [Install kubectl binary using curl](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-binary-using-curl)


1. Download the latest release.
  ```
  curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
  ```
  To download a specific version, replace the `$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)` portion of the command with the specific version.
  For example, to download version v1.11.5 on macOS, type:
  ```
  curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.11.5/bin/darwin/amd64/kubectl
  ```
1. Make the kubectl binary executable.
  ```
  chmod +x ./kubectl
  ```
1. Move the binary in to your PATH.
  ```
  sudo mv ./kubectl /usr/local/bin/kubectl
  ```