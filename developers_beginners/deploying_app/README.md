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

```
1) argocd login dashboard.internal.aurora.equinor.com --sso
2) Push your changes to the remote repository (create a new branch)
3) If this is  new repository or project, get in touch with the Aurora team and they will add them to argocd
3) Add the application to argocd: `argocd app create -f application-dev.yaml`
4) View the application at: https://dashboard.dev.aurora.equinor.com/applications/example
5) Sync the app
```

## Verifying Kutomize 
This command allows you to check the final yaml resulting from your environment patches.

```
kustomize build k8s_kustomize/overlays/development > k8s_kustomize/kustomization/manifests.yaml
```

