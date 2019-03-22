# Scaling

Kubernetes supports three different kinds of autoscalers - cluster, horizontal and vertical.

* Autoscaling Kubernetes clusters
* Vertical pod autoscaler
* Horizontal pod autoscaler

## Cluster Autoscaler

Taken from [Autoscaling Kubernetes clusters][12].

The Cluster Autoscaler is a tool that automatically right sizes your Kubernetes cluster. It runs periodically and reacts to the following events:

* there are pods that failed to run in the cluster due to insufficient resources, usually these pods are in `Pending` state
* some nodes in the cluster are underutilized for a configurable extended period of time, so they can be deleted and their pods easily placed on other existing nodes.

--------------------
Scale Kubernetes workloads managed by Amazon EKS in response to custom metrics.

For many workloads, it’s crucial to be able to define application scaling based
on custom metrics like inbound connection requests or job queue length. 

The [Horizontal Pod Autoscaler][2] (HPA) is a Kubernetes component that automatically
scales your service based on CPU utilization or other metrics that you define
through the Kubernetes [Metrics Server][3].

## [Horizontal Pod Autoscaler Walkthrough][4]


### Install [Kubernetes Metrics Server][5]

use [Helm chart][6]

### Run & expose php-apache server

Start a deployment running the image and expose it as a service:
```
$ kubectl run php-apache \
--image=k8s.gcr.io/hpa-example \
--requests=cpu=200m \
--expose \
--port=80

service/php-apache created
deployment.apps/php-apache created
```

### Create Horizontal Pod Autoscaler

The following command will create a Horizontal Pod Autoscaler that maintains
between 1 and 5 replicas of the Pods. 

HPA will increase and decrease the number of replicas (via the deployment) to
maintain an average CPU utilization across all Pods of 50% 

```console
kubectl autoscale deployment php-apache \
--cpu-percent=50 \
--min=1 \
--max=5

horizontalpodautoscaler.autoscaling/php-apache autoscaled
```

```
$ kubectl get hpa
NAME         REFERENCE               TARGETS         MINPODS   MAXPODS   REPLICAS   AGE
php-apache   Deployment/php-apache   <unknown>/50%   1         5         0          24s
```


## Cluster Autoscaler on AWS

The [cluster autoscaler on AWS][7] scales worker nodes within any specified autoscaling group. It will run as a Deployment in your cluster. This README will go over some of the necessary steps required to get the cluster autoscaler up and running.

* [Cluster Autoscaler in Amazon EKS][8]
* [Helm - cluster-autoscaler][9]
* [Blog - Horizontally autoscale Kubernetes deployments on custom metrics][10]
* [Helm - Prometheus Adapter][11]
* [Why and how do we run Kubernetes on the Spot instances][13]

[1]:https://aws.amazon.com/blogs/opensource/horizontal-pod-autoscaling-eks/
[2]:https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/
[3]:https://kubernetes.io/docs/tasks/debug-application-cluster/core-metrics-pipeline/#metrics-server
[4]:https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale-walkthrough/
[5]:https://github.com/kubernetes-incubator/metrics-server/
[6]:https://github.com/helm/charts/tree/master/stable/metrics-server
[7]:https://github.com/kubernetes/autoscaler/blob/master/cluster-autoscaler/cloudprovider/aws/README.md#cluster-autoscaler-on-aws
[8]:https://medium.com/@alejandro.millan.frias/cluster-autoscaler-in-amazon-eks-d9f787176519
[9]:https://github.com/helm/charts/tree/master/stable/cluster-autoscaler
[10]:https://banzaicloud.com/blog/k8s-horizontal-pod-autoscaler/
[11]:https://github.com/helm/charts/tree/master/stable/prometheus-adapter
[12]:https://banzaicloud.com/blog/k8s-cluster-autoscaler/
[13]:https://medium.com/preply-engineering/why-and-how-do-we-run-kubernetes-on-the-spot-instances-c88d32fb9df3