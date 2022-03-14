
# Example app

This is Flask App which outputs Hello World

It is used to show the most basic helm deployment and how argocd works.  
To build the container we run:  
```
az acr login --name auroradevacr
docker build  --label com.equinor.aurora.project="workshop" \
              --tag auroradevacr.azurecr.io/workshop-dev/flask-app-your-name:your-tag-number . 
docker push auroradevacr.azurecr.io/your-project-name/your-image-name:your-tag-number 

```

## Deploy to Argocd
1) Add the application to argocd: `argocd app create -f application-dev.yaml`
2) View the application at: https://dashboard.dev.aurora.equinor.com/applications/example
3) Sync the app