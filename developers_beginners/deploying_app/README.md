# Kustomize Structure
```
~/deploying_app
├──src
│  ├── your_app_files
│  └── Dockerfile
└──k8s
    ├── base
    │   ├── deployment.yaml
    │   └── kustomization.yaml
    └── overlays
        ├── development
        │   ├── kustomization.yaml
        │   ├── resource_patch_dev_1.yaml
        │   └── resource_patch_dev_2.yaml
        └── production
            ├── kustomization.yaml
            ├── resource_patch_prod_1.yaml
            └── resource_patch_prod_2.yaml
```


# Helm Structure
```
~/deploying_app
├──src
│  ├── your_app_files
│  └── Dockerfile
└──k8s
   ├── templates
   │   ├── deployment.yaml
   │   └── _helpers.tpl
   ├── Chart.yaml
   ├── values.yaml
   └── values-dev.yaml

```


## Deploy to Argocd
1) Add the application to argocd: `argocd app create -f application-dev.yaml`
2) View the application at: https://dashboard.dev.aurora.equinor.com/applications/example
3) Sync the app