# Security

Links:

* https://github.com/aquasecurity/kube-bench
* https://www.cisecurity.org/benchmark/kubernetes/
* https://www.clearscale.com/blog/securing-aws-eks-with-calico-and-kube2iam/
  * [Calico](https://docs.projectcalico.org/v2.5/reference/public-cloud/aws)
  > Project Calico aims to provide robust security solutions for modern containerized implementations.  As such, ClearScale chose to leverage the Network Policy Engine feature because it allowed network isolation and segmentation inside of the Kubernetes clusters and similar to what AWS Security Groups accomplishes.
  * [Kube2IAM](https://github.com/jtblin/kube2iam)
  > Because of how AWS EKS manages the individual Kubernetes Pods, they initially all receive the same permission set assigned by the IAM role associated to the EC2 instance it runs on.  Since our client required a more granular permission set for each Kubernetes Pod, Kube2IAM was implemented to allow each Pod access through individually assigned IAM roles.
    * [Moving from Kube2Iam to Kiam](https://medium.com/building-ibotta/moving-from-kube2iam-to-kiam-a000639b839e)
    > After further investigation, the future of the project seems to be uncertain and there are other issues logged around race conditions, etc. After some research, [Kiam](https://github.com/uswitch/kiam) seems to be a valid alternative. The developers have written a post on their experience of Kube2iam and why they decided to write Kiam which goes into a lot of detail.
    * [Kiam: Iterating for Security and Reliability](https://medium.com/@pingles/kiam-iterating-for-security-and-reliability-5e793ab93ec3)
    > Kiam bridges Kubernetes’ Pods with Amazon’s Identity and Access Management (IAM). It makes it easy to assign short-lived AWS security credentials to your application.
  * [CNI Plugin](https://github.com/aws/amazon-vpc-cni-k8s)
  > The open-sourced project Amazon Virtual Private Cloud (VPC) Container Networking Interface (CNI) plugin for Kubernetes allowed ClearScale to assign the “real” IP Address to the Kubernetes Pods from the VPC network.