# Jenkins on Kubernetes

Kubernetes manifests to deploy a Jenkins master on a Kubernetes cluster running
on Amazon Web Services. This assumes CoreOS [Tectonic][0], but should work on
any "standard" Kubernetes cluster that doesn't have a ton of open source
hackery/customization.

## Components

* `jenkins-ns.yaml` : creates a namespace for Jenkins
* `ebs-storageclass.yaml`: creates a StorageClass for Elastic Block Storage
* `jenkins-service-account.yaml`: creates a ServiceAccount that gives
permission to Jenkins to run pods as build slaves
* `jenkins-master.yaml`: creates a Jenkins master pod, PersistentVolumeClaim on
EBS, and a Service so Jenkins is accessible from outside the cluster.
* `example-Jenkinsfile`: An example Jenkinsfile for use in application
repositories.

[0]: https://coreos.com/tectonic