# Kustomize Structure
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



# Helm Structure
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

