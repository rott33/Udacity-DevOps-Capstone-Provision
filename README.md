# Udacity-DevOps-Capstone-Provision
This is a Jenkins pipeline that provisions an Amazon Elastic Kubernetes Service (AWS EKS) cluster using [eksctl](https://eksctl.io/).

Cluster creation results in a [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) config being created - which, assuming the same AWS credentials are used - can be utilized in other Jenkins pipelines for application deployments into this cluster.
