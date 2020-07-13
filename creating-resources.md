There are different ways to create resources in Azure.

1. Azure Portal
2. Azure CLI (Cloud Shell or installing CLI librabry on local CLI tool)
3. PowerShell

When we create any resource in azure, azure provide option to export resource infrastructure and configuration in file so that we can create and deploy same resource within different region, 
subscription or resource group just with little tweeks. This configuration file is knows as Azure Resource Manager template (ARM) file.

The ARM template is a JavaScript Object Notation (JSON) file that defines the infrastructure and configuration for your project. 
The template uses declarative syntax, which lets you state what you intend to deploy without having to write the sequence of programming commands to create it. 
In the template, you specify the resources to deploy and the properties for those resources.
