# GemfireJourney
Distributed cache cluster running on k8s.

## Installation Guide
### Prerequisites
- kubernetes environment
- cert-manager installed [link](https://cert-manager.io/docs/installation/)
- helm v3
- gfsh [Installing Pivotal Gemfire](https://gemfire.docs.pivotal.io/99/gemfire/getting_started/installation/install_intro.html)
### Monitoring Tool
Install [kube-prometheus-stack](https://artifacthub.io/packages/helm/prometheus-community/kube-prometheus-stack)  
[Configuration docs](https://github.com/prometheus-operator/kube-prometheus)  
Replace `k8s.gcr.io` image if no access
### Gemfire Operator
https://docs.vmware.com/en/VMware-Tanzu-GemFire-for-Kubernetes/2.0/tgf-k8s/GUID-install.html
### Gemfire Cluster
https://docs.vmware.com/en/VMware-Tanzu-GemFire-for-Kubernetes/2.0/tgf-k8s/GUID-create-and-delete.html
``` shell
kubectl -n NAMESPACE apply -f  gemfire-cluster.yaml
kubectl -n NAMESPACE apply -f  loadbalancer.yaml
```
### Pulse
Start `gfsh` command
#### Connect to k8s Gemfire cluster
``` shell
gfsh>connect --locator --use-http=true --url=https://EXTERNAL-IP:7070/gemfire/v1 --skip-ssl-validation
```
``` shell
gfsh> start pulse
```
Open https://EXTERNAL-IP:7070/pulse  
Sign in with default *admin:admin*