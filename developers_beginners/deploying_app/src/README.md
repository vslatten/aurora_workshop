
# Example app

This is Flask App which outputs Hello World

It is used to show the most basic helm deployment and how argocd works.  
To build the container, cd into this folder and run:  
```
az acr login --name auroradevacr
docker build  --label com.equinor.aurora.project="workshop" \
              --tag auroradevacr.azurecr.io/workshop-dev/flask-app-your-name:your-tag-number .
docker push auroradevacr.azurecr.io/workshop-dev/your-image-name:your-tag-number 
```

To check the image is correctly stored:
```
az acr repository show -n auroradevacr.azurecr.io --repository your-project-name/your-image-name
```

Tips:
To check the app while developing:
```
python view.py
```
to Check docker image:
```
docker run -p 5000:5000 -d auroradevacr.azurecr.io/workshop-dev/flask-app-your-name:your-tag-number
```