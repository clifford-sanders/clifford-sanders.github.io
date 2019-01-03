# Worker Nodes

Links:
* https://docs.aws.amazon.com/eks/latest/userguide/worker.html

> By default, Amazon EKS provides AWS CloudFormation templates to spin up worker nodes in your Amazon EKS cluster. This AMI is built on top of Amazon Linux 2, and is configured to serve as the base image for Amazon EKS worker nodes. The AMI is configured to work with Amazon EKS out of the box, and it includes Docker, kubelet, and the AWS IAM Authenticator. The AMI also contains a specialized bootstrap script that allows it to discover and connect to your cluster's control plane automatically.
> The AWS CloudFormation worker node template launches your worker nodes with specialized Amazon EC2 user data that triggers a specialized bootstrap script<sup>[1](#bootstrap_script)</sup> that allows them to discover and connect to your cluster's control plane automatically. For more information, see _Launching Amazon EKS Worker Nodes_<sup>[2](#launch_worker_nodes)</sup>.

<sup><a name="bootstrap_script">1</a></sup> [bootstrap script](https://github.com/awslabs/amazon-eks-ami/blob/master/files/bootstrap.sh)

<sup><a name="launch_worker_nodes">2</a></sup> [Launching Amazon EKS Worker Nodes](https://docs.aws.amazon.com/eks/latest/userguide/launch-workers.html)