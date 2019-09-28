# Udacity-DevOps-Capstone-Provision
This is a Jenkins pipeline that provisions an Amazon Elastic Kubernetes Service (AWS EKS) cluster using [eksctl](https://eksctl.io/).

Cluster creation results in a [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) config being created - which, assuming the same AWS credentials are used - can be utilized in other Jenkins pipelines for application deployments into this cluster.

Note that the use of optional eksctl parameter ```--node-private-networking``` forces the cluster node VMs to be created in private subnets of the newly created dedicated VPC, as opposed to the default behavior of creating them in public subnets. Deployed applications can then be exposed on publicly accessible ports through the use of Kubernetes [services](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) declaring ```type: LoadBalancer```.
