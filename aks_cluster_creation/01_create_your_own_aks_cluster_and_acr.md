### Note: For this section, you have to know some k8s basics and also be somewhat familiar with Azure (beginner level would be fine)

## Exercise 1 - Create your AKS Cluster and connect to it

1. Log into your azure account and make sure to set your correct subscription (if not done already)

  ```bash
  az login
  az account list
  az account set --subscription 'my-subscription-name'
  ```

2. Create a resource group, replace "\<aks-resource-group>" with the name of the Resource Group you want to create:

  ```bash
  az group create --name=<aks-resource-group> --location=northeurope
  ```

3. Run the following command to deploy Kubernetes cluster with AKS. Replace "\<aks-resource-group>" and "\<aks-name>" with the name of the Resource Group you created and the AKS cluster name you want to create:

  ```bash
  az aks create --resource-group <aks-resource-group> --name <aks-name> --node-count 2 --node-vm-size "Standard_DS2_v2" --generate-ssh-keys
  ```
  
  > This may take a short while to complete.
 
4. Use the Azure CLI to get the credentials to connect kubectl to your AKS cluster:

  ```bash
  az aks get-credentials --resource-group <aks-resource-group> --name <aks-name>
  ```
    
# Setup Kubectl in Codespace environment

1. Install Kubectl in vs code environment (via its terminal)

    https://kubernetes.io/docs/tasks/tools/install-kubectl/

2. Run some basic commands to ensure you're able to connect to your cluster.

    ```
    kubectl cluster-info
    kubectl get all     
    
    ```

## Exercise 2 - Deploy ACR
In this exercise, you will create an Azure Container Registry instance using the Azure CLI and setup integration between ACR and AKS. 

### Steps

1. Create a resource group, replace "\<acr-resource-group>" with the name of the Resource Group you want to create:

    ```bash
    az group create --name=<acr-resource-group> --location=northeurope
    ```

2. Create an ACR instance using the ```az acr create``` command. Replace "\<acr-resource-group>" and "\<acr-name>" with the Resource Group name and the Azure Container Registry name you wish to create.

    ```bash
    az acr create --resource-group <acr-resource-group> --name <acr-name> --sku Basic
    ```

3. When you're using Azure Container Registry (ACR) with Azure Kubernetes Service (AKS), an authentication mechanism needs to be established. Use the ```az aks update``` command to integrate with your newly created Container Registry.

    ```bash
    az aks update -n <aks-name> -g <aks-resource-group> --attach-acr <acr-name>
    ``` 
