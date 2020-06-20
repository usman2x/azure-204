Azure CLI commands to create, manage, deploy Azure container instance (ACI). 

### List all subscriptions
> `az account list`

### List all resource groups
> `az group list `

### Create resource group
> `caz group create --name aci_session --location eastus `

### Create container instance with public ACR image and expose 80 port as public
> ` az container create --resource-group aci_session --name helloworld --image mcr.microsoft.com/azuredocs/aci-helloworld --dns-name-label aci-demo --ports 80 `

> `az container create --resource-group aci_session --name aciwebcontainer --image microsoft/aci-helloworld --ports 80 --dns-name-label aci-web-demo  --location eastus`

### Create container with restart policy, Restart policies describes How often container instance will run

> `az container create --resource-group aci_practice --name mycontainer-restart-demo --image microsoft/aci-wordcount:latest --restart-policy OnFailure --location eastus`

### Create container with environment variables
> ` az container create --resource-group aci_practice --name mycontainer-restart-demo --image microsoft/aci-wordcount:latest --restart-policy OnFailure --location eastus --environment-variables 'NumWords'='5' 'MinLength'='8' `

### Create container with yaml file, YAML file allows to create container instance fastly with same configuration.
> ` az container create --resource-group aci_practice --file secret.yaml`

### Create container using ACR, ACI is configurable all kinds of docker registeris, ACR is azure managed resource, access can be made through headless or direct. 

There are different ways to give access to Azure ACR, 1) Enable ACR admin rule, get credentials and provide full admin access. 2) Create service principal with role based access.

> ` az container create --name aci-acr-hello-world --resource-group acr_session  --image acracisession.azurecr.io/hello-world:v1 --registry-login-server acracisession.azurecr.io --registry-username acracisession --registry-password Qjxnk/aUTnSiFoMmDrNzqvqD7u4A62AT --dns-name-label aci-acr-hello-world --query ipAddress.fqdn `

### Deploy container and mount volume
Docker container is stateless, we can integrate data volume to make docker instance statefull. Azure file share is azure managed service that could be used as docker volume
> ` az container create --resource-group aci_practice --name acrhellofiles --image mcr.microsoft.com/azuredocs/aci-hellofiles --dns-name-label aci-storage-hello-files --ports 80 --azure-file-volume-account-name acistoragefileshare --azure-file-volume-account-key hUP2B7NpyXnUs7zZYu8qJ6OiqKMo2/9XybGlwJZRLw/t8JpkoO6QT9TU+V+y2cNtzveifhpjbVrDio/NCqGetg== --azure-file-volume-share-name acistoragefileshare --azure-file-volume-mount-path /aci/logs/ `

> ` az container show --resource-group aci_practice --name acrhellofiles --query ipAddress.fqdn --output tsv  `

### Deploy container group using yaml, Container group allows to deploy similar container instances as a group
> `az container create --resource-group aci_practice --file aci-group.yaml`

### View Container group deployment state & Logs
> `az container show --resource-group aci_practice --name acicontainergroup --output table`

> `az container logs --resource-group aci_practice --name myContainerGroup --container-name aci-tutorial-app`

### Show container status
> `az container show --resource-group aci_practice --name aciwebcontainer --query "{FQDN:ipAddress.fqdn,ProvisioningState:provisioningState}" --out table`

> `az container show --resource-group aci_practice --name aciwebcontainer --query containers[0].instanceView.currentState.state`

> `az container show --resource-group aci_practice --name securetest --query 'containers[].environmentVariables'`

### Container logs
> `az container logs --resource-group aci_practice --name mycontainer-restart-demo`

### Open shell in running container
> `az container exec --resource-group aci_practice --name secret-volume-demo --exec-command "/bin/sh"`


### Create ACR
> `az acr create --resource-group aci_session --name acracisession --sku Basic`

### Push image to Azure ACR registry
> `docker pull dockersamples/static-site`

> `docker pull yeasy/simple-web:latest`

> `docker tag dockersamples/static-site acracisession.azurecr.io/static-site:latest`

> `docker push acracisession.azurecr.io/static-site:latest`

> `docker rmi acracisession.azurecr.io/simple-web:latest`

### List container images
> `az acr repository list --name acracisession --output table`

> `az acr repository show-tags --name acracisession --repository hello-world --output table`

Login to ACR
> `az acr login --name acracisession`

> `docker login acracisession.azurecr.io --username cccb2059-961d-44f7-9be5-1f48e9a78e24 --password e1aaa573-c61a-44c1-b7fb-e065d9b408ba`

### Enable acr registry admin
> `az acr update -n acracisession --admin-enabled true`
> `az acr credential show --name acracisession`

### Create Service principal
> `ACRREGISTRYID = $(az acr show --name acracisession --query id --output tsv)`

> `az ad sp create-for-rbac --name http://acracipracticesp --scopes $ACRREGISTRYID --role acrpush --query password --output tsv`

> `az ad sp show --id http://acracipracticesp --query appId --output tsv`

> `az ad sp show --id http://acracipracticesp`


### Create Storage Account and file share
> `az storage account create --resource-group aci_session --name acisessionstorageaccount  --location eastus --sku Standard_LRS`

> `az storage share create --name acisessionstoragefileshare --account-name acisessionstorageaccount`

> `az storage account keys list --resource-group aci_session --account-name  acisessionstorageaccount --query "[0].value" --output tsv`
