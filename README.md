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
az aks get-credentials --overwrite-existing --resource-group workshop13 --name workshop13 --subscription S913-Aurora-Non-production
```
Set your context
```
kubectl config set-context --current --namespace=workshop
```
Apply a resource yaml
```
kubectl apply -f <file>.yaml
```