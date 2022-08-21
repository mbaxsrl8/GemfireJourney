# GemfireJourney
Distributed cache cluster running on k8s.
## References
1. https://network.pivotal.io/products/tanzu-gemfire-for-kubernetes/
2. https://docs.vmware.com/en/VMware-Tanzu-GemFire-for-Kubernetes/index.html

## Installation Guide
### Prerequisites
- kubernetes environment
- helm v3
### Monitoring Tool
Install [kube-prometheus-stack](https://artifacthub.io/packages/helm/prometheus-community/kube-prometheus-stack)  
[Configuration docs](https://github.com/prometheus-operator/kube-prometheus)  
Replace `k8s.gcr.io` image if not access