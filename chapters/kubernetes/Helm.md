# Helm

Taken from [Manage Helm repositories and deploy charts via REST][1]

Helm is the package manager for Kubernetes. It’s built on three key ingredients:

* _Charts_ - bundles of information that are necessary to create the instances of Kubernetes applications
* _Config_ - which contains configuration information that can be merged into a packaged chart to create a releasable object
* _Release_ - a running instance of a chart, combined with a specific config

Helm is also built on two major architectural components:

**The Helm Client**, a command line tool with the following responsibilities

* Interacts with the Tiller server
* Sends charts to be installed
* Upgrades or uninstalls existing releases
* Manages repositories

**The Tiller Server**, an in-cluster server with the following responsibilities:

* Interacts with the Helm client
* Interfaces the Kubernetes API server
* Combines a chart and configuration to build a release
* Installs charts and tracks their release
* Upgrades and uninstalls charts

Both the Helm client and Tiller are written in Go, and use gRPC to interact. Tiller (as the server component running inside Kubernetes) provides a gRPC server in order to connect with the client, and uses the k8s client library to communicate with Kubernetes. It does not require it’s own database, since the information is stored within Kubernetes as ConfigMaps.

## Plugins

```
# diff - Preview helm upgrade changes as a diff
helm plugin install https://github.com/databus23/helm-diff --version v2.11.0+3
```

## Chart Repositories

<dl>
<dt>[Kubernetes](https://github.com/helm/charts)</dt>
<dd>Official Charts for Helm</dd>

<dt>[Banzai](https://github.com/banzaicloud/banzai-charts)</dt>
<dd>Curated list of Banzai Cloud Helm charts used by the Pipeline Platform</dd>
</dl>

[1]:https://banzaicloud.com/blog/helm-rest-api/