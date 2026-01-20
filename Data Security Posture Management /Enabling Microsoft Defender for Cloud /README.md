This lab has two main exercises: (1) Provisioning resources via a custom ARM template, and (2) Enabling Microsoft Defender for Cloud in the Azure Portal. it aims to deploy a set of resources with an ARM template and then activate Microsoft Defender for Cloud to secure the subscription.

Objectives:

Learn how to deploy Azure resources using an ARM template (Infrastructure as Code).

Understand how to enable Microsoft Defender for Cloud on an Azure subscription.

Capture and document your steps with screenshots.

Verify that resources are deployed and Defender for Cloud is active.

#Exercise: Provisioning Resources

Purpose of the ARM Template. An ARM (Azure Resource Manager) template is a JSON file that defines your cloud infrastructure in a declarative manner. [What are ARM templates?](https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/overview#:~:text=To%20implement%20infrastructure%20as%20code,group%20those%20resources%20are%20deployed) Using an ARM template lets you automatically provision multiple Azure resources in one step, ensuring a repeatable and consistent environment. This lab’s template deploys a variety of resources (e.g. Windows and Linux VMs, an availability set, an AKS cluster, an App Service Plan with Web App, a SQL server and database, a Key Vault, a Function App, a Log Analytics workspace, Network Security Group, Azure Container Registry, Storage account, etc.). All these resources are defined in the JSON template so they are created together.

For the lab i used a special Azure deployment link that opens the Azure Portal and starts the process of deploying a resource using a predefined ARM (Azure Resource Manager) template hosted on GitHub. It’s commonly used in labs, tutorials, or automation scenarios to quickly set up cloud infrastructure.

To deploy, sign in to the Azure Portal and use the search bar to type Deploy a custom template. Select the Deploy a custom template option (as shown above). This opens the Custom deployment page. Here, you provide deployment details:
<img width="819" height="453" alt="image" src="https://github.com/user-attachments/assets/088badf8-0c4d-459e-bb56-2da30a4ba181" />

[Retrieve a custom template](https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/quickstart-create-templates-use-the-portal#retrieve-a-custom-template)

- Item 1 Subscription: Choose your Azure subscription.
- Item 2 Resource group: Create a new resource group (e.g. asclab-rg) or use an existing one.
Sub item 3 Region: Select a region (e.g. “West Europe”). All resources will be deployed in this region.
Sub item 4 Administrator password: Enter a strong admin password (minimum 12 characters with mixed-case, numbers, and symbols) for the VMs/SQL in the template.
Sub item 5 After entering these values, click Review + create, and then Create to start the deployment. Azure validates the template and then provisions the resources. The deployment can take several minutes (typically ~10 minutes).

Once the deployment is initiated, you can monitor its progress. Go to Resource groups in the portal, open the new resource group you created, and select Deployments. You should see the deployment in progress. When it finishes, each resource will show Provisioning state: Succeeded

