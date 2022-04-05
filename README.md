# aurora-technical-training
This repository holds the material for the technical training workshop hosted by the Aurora team

## Gaining access

Log into Azure
```
az login
```
Set the subscription to the Aurora non-prod subscription
```
az account set --subscription S913-Aurora-Non-production
```
Authenticate into the workshop13 cluster
```
aurora_subscription="S913-Aurora-Non-production"; cluster_name="workshop13"; az aks get-credentials --overwrite-existing --resource-group ${cluster_name} --name ${cluster_name} --subscription ${aurora_subscription}
```
Set your context
```
kubectl config set-context --current --namespace=workshop
```
Apply a resource yaml
```
kubectl apply -f <file>.yaml
```