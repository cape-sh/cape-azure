# Deploy CAPE on Azure cloud 


[![Deploy To Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fcape-sh%2Fcape-azure%2Fmaster%2Fazuredeploy.json)

[![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2Fcape-sh%2Fcape-azure%2Fmaster%2Fazuredeploy.json)


## Try CAPE for FREE on Azure cloud

### Install CAPE on Azure

> There are 2 options for accessing CAPE. Follow one of the options below as "root" user on the machine that you want to deploy to.

**Option 1 (Recommended)**: 


Go to azure cloud shell: [Azure Shell](https://shell.azure.com/) and type commands below.


Run the deployment by copy pasting the given commands:


```bash
az group create --name caperesgrp2020 --location eastus
curl https://raw.githubusercontent.com/cape-sh/cape-azure/master/azuredeploy.json > azuredeploy.json
curl https://raw.githubusercontent.com/cape-sh/cape-azure/master/azuredeploy.parameters.json > azuredeploy.parameters.json
templateFile=azuredeploy.json
parameterFile=azuredeploy.parameters.json
az deployment group create   --name capesaasdeployment   --resource-group caperesgrp2020   --template-file $templateFile --parameters $parameterFile 
 
 
```
Here we will create a new resource group to keep cape resources in separate zone and deploy cape saas end to end.
Yes your deployment is complete!!

You can login to your cape cloud machine :
> username :  cape
> Password: Biqmind@1234!

**Option 2:**

*Non CLI option*

Click  Deploy button :

[![Deploy To Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fcape-sh%2Fcape-azure%2Fmaster%2Fazuredeploy.json)

> Downlaod **azuredeploy.parameters.json** and upload manually in "Edit paramaters" or copy the contents

You can modify the parameters fields as per your requirement 

---

### Access CAPE UI 

The service may take 1-5 mins to come up based on the server config and the internet bandwidth.

> URL

```
http://<Your_server_ip>.nip.io/
```
---


### Troubleshooting 

As "root" user run below command to check the pods status. 
Login as cape and switch user as root "sudo su - root"

```bash
kubectl get pods -A
```
Make sure all pods are in a healthy state else kill any unhealthy pods and they will restart within a few seconds

---

### RESET everything using playbook

Login as root to your machine

> Run this playbook to uninstall Kubernetes and crictl

```bash
cd cape-azure
ansible-playbook reset.yml
```
> "cape-ansible" directory is located where the capesaasPubIP.sh or capesaasPvtIP.sh script was downloaded earlier.

---

### Recommended System requirements

```
OS: Centos 7.3/7.4/7.5  
CPU: 2 core
RAM: 4GB RAM
Disk Space: 10 GB free 
Server Internet access: Yes
```

---

## Support
For more information on CAPE, return to the main [Repo](https://github.com/cape-sh/cape)



