# Citrix Azure Capacity Management Template

This template can be used to assign permissions to the Resource groups and Subscriptions as per the KB Article - https://support.citrix.com/article/CTX224110#Resource Group(s) :

# Pre-Requisites
 
* Define Application Registion using the Documentation in the above mentioned KB Article.
 
Click the button below to deploy

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAsraFatima%2FARMTemplate%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

Template parameters:

| Name   | Description    |
|:--- |:---|
| MangementType | Specify the permission you want apply on the Resources for the Machine provisioning. Allowed Values "Citrix Managed" or "Customer Managed".
Citrix Managed – In this model, Citrix Cloud is in full control of Resource Group(s) during the machine provisioning process.  As Resource Groups are required, Citrix Cloud will simply add more as necessary to support the additional catalogs being provisioned.  This streamlines the management experience by handling these details.  This also makes the Citrix administrator the sole arbiter of how many virtual machines can be deployed.Customer Managed – In this model, an Azure Admin or Co-Admin pre-creates Resource Groups that worker machines will be provisioned in to.  Citrix Cloud cannot create additional Resource Groups as necessary, this will need to be performed by an Azure Subscription Admin or Co-Admin.  This will require good communication between the Citrix Administrator and Azure Administrator as the number of Citrix workers in Azure is increased.| 
|location| Specify the Azure region in which you want to deploy the template. |
| StorageAccountnewOrExisting | Specifies whether the storage account should be created or already exists. | 
| VirtualNetworknewOrExisting | Specifies whether the Virtual Network should be created or already exists. | 
| ImageStorageAccountName | Specify the the Name of the existing or new Storage account. | 
| ImageStoreResourceGroup | Specify the Name of the Resource Group. This should be an existing resource group where you want to deploy a new storage account mentioned as a part of the parameter "ImageStorageAccountName". |
| VirtualNetworknewOrExisting | Specifies whether the Virtual Network should be created or already exists. | 
| VirtualNetworkName | Specify the Name of the Virtual Network new or Existing.|
| VirtualNetworkResourceGroup | Specify the Name of the resource group for the above Virtual Network new or Existing.|
| ServicePrincipalId | Specify the ObjectId of the Application created using the KB article.|
| artifactsBaseUrl | Specifies the base location of the child templates and desired state configuration scripts. | 
| artifactsBaseUrlSasToken | Specifies the shared access signature token which provides access to the base artifacts location. | 

Deploy the Template:

Right now few of the features used in the template are not supported in GithUb. So please update perform the following steps to execute this template:
* Download the Azure Powershell Version 4.0.1 from https://github.com/Azure/azure-powershell/releases/tag/v4.0.1--May2017 
* Update the azuredeploy.parameters.json.
* Launch Windows Powershell Command prompt.
* Login to the Azure Account and Select the desired Subscription using the following CmdLets
    # Login-AzureRmAccount
    # Select-AzureRmSubscription -SubscriptionName <SubscriptonName>
 * 
* 
