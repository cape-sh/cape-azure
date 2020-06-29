# cape_on_azure_centos7

[![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2Fcape-sh%2Fcape-azure%2Fmaster%2Fazuredeploy.json)


# Welcome to CAPE
<p align="center" style="background-color:#23327c">
  <img src="https://raw.githubusercontent.com/cape-sh/cape/master/assets/logo.png" height="125px" width="200px"/>
</p>

**About**

Organizations struggle to manage their Kubernetes clusters at a level expected by various stakeholders; they are debilitated by a lack of resources, expertise and tools. Organizations need to overcome these obstacles and become Kubernetes-ready. CAPE will provide organizations with the tooling and ability to perform:

- Disaster Recovery
  - Utilize Velero, an open source Kubernetes tool for backup & restore
  - Perform single scheduled backup & restore
  - Perform multi-cluster & multi-cloud backup & restore
- Multi-cluster application deployment
- Multi-cluster DNS and ingress

CAPE enables you to manage Kubernetes clusters on day one without specialized knowledge or proprietary API/CLI experience.

---

**Find out more about CAPE:**

[![](http://img.youtube.com/vi/4KJt8NXTO8E/0.jpg)](http://www.youtube.com/watch?v=4KJt8NXTO8E "Biqmind Cape")


---

## Try CAPE SAAS for FREE on Azure cloud

### Install CAPE on Azure

> There are 2 options for accessing CAPE. Follow one of the options below as "root" user on the machine that you want to deploy to.

Option 1: 

Azure CLI method: 
[!Install Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)
Clone this repo and go to directory 

```bash
git clone https://github.com/cape-sh/cape-azure.git
cd cape-azure
```

Run the deployment as below:
* Recommended to create a new Resource group and pass it in below cmd*
```
templateFile=azuredeploy.json
ParameterFile=azuredeploy.parameters.json
az deployment group create   --name capedeployment   --resource-group <your-new-resource group>   --template-file $templateFile --parameters $ParameterFile
```

Option 2:
*Non CLI option*
Click  Deploy button :

[![Deploy To Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fcape-sh%2Fcape-azure%2Fmaster%2Fazuredeploy.json)

> Downlaod **azuredeploy.parameters.json** and manually in Edit template section if you want to edit parameters. 

You can modify the parameters fields as per your requirement
azuredeploy.parameters.json download URL: https://github.com/cape-sh/cape-azure/blob/master/azuredeploy.parameters.json

---

### Access CAPE UI 

The service may take 1-5 mins to come up based on the server config and the internet bandwidth.

> URL

```
http://<Your_server_ip>.nip.io/
```
** All CAPE documentation is available [here](https://docs.cape.sh/docs/) **

---


### Troubleshooting 

As "root" user run below command to check the pods status.

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

## Get Started with CAPE

Use this [tutorial](https://docs.cape.sh/docs/simple-install) to get started quickly.


## Get Involved

We appreciate your feedback and active participation.

If you want to get in touch with us to discuss improvements and new
features, please [create a new issue on GitHub](https://github.com/cape-sh/cape/issues/new) or connect with us over on Slack:

* [`#general` Slack channel](https://capesh.slack.com)



