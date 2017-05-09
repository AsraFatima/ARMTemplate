# Citrix Azure Capacity Management Template

This template demonstrates the creation of a self-contained XenApp environment in Azure, creating the following resources:

* Resource Groups
  * CitrixInfrstructureRG
  * CitrixCustomImageRG
  * Inaddition to above two resource groups, Worker resource groups
* Storage Account for storing the CustomImages
* Citrix NetScaler
* Citrix Virtual Desktop Agents (1 RDSH & 1 Server VDI)
* RDP JumpBox

After deployment, the components are fully configured and a simple XenApp site is created in a number of steps:

1. A new user-specified Active Directory domain is created and the machines are automatically joined to it.
2. A SQL server database is configured and a site is created on the XenApp Delivery Controller.
3. VDAs are provisioned and joined to the new site.
4. A StoreFront site is created, providing access to published Apps & Desktops.
5. A certificate is obtained for the deployment from the letsencrypt certificate authority.
6. NetScaler is configured as a gateway to the deployment.

# Pre-Requisites
 
These templates make use of hidden Virtual Machine images which have the above XenApp components fully installed. 

Need to understand this so i can document it better.
 
Click the button below to deploy

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAsraFatima%2FARMTemplate%2Fmaster%2FmainTemplate.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

Template parameters:

| Name   | Description    |
|:--- |:---|
| vhdStorageAccount | Specifies the name of the storage account used for virtual machine disks. This has to be a unique name, up to 24 chars, all lowercase. | 
| vhdStorageType | Specifies the type of storage account, if being created. | 
| vhdStorageGroup | Specifies the resource group which should contain the storage account. | 
| vhdStorageNewOrExisting | Specifies whether the storage account should be created or already exists. | 
| artifactsBaseUrl | Specifies the base location of the child templates and desired state configuration scripts. | 
| artifactsBaseUrlSasToken | Specifies the shared access signature token which provides access to the base artifacts location. | 
