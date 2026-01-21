This lab has two main exercises: 
- (1) Provisioning resources via a custom ARM template, and
- (2) Enabling Microsoft Defender for Cloud in the Azure Portal.

it aims to deploy a set of resources with an ARM template and then activate Microsoft Defender for Cloud to secure the subscription.

Objectives:

- Learnt how to deploy Azure resources using an ARM template (Infrastructure as Code).

- Understand how to enable Microsoft Defender for Cloud on an Azure subscription.

- Capture and document the steps taken during the lab session.

- Verify that resources are deployed and Defender for Cloud is active.

# Exercise: Provisioning Resources

Purpose of the ARM Template. An ARM (Azure Resource Manager) template is a JSON file that defines your cloud infrastructure in a declarative manner. 
- [What are ARM templates?](https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/overview#:~:text=To%20implement%20infrastructure%20as%20code,group%20those%20resources%20are%20deployed)
Using an ARM template lets you automatically provision multiple Azure resources in one step, ensuring a repeatable and consistent environment. This lab’s template deploys a variety of resources (e.g. Windows and Linux VMs, an availability set, an AKS cluster, an App Service Plan with Web App, a SQL server and database, a Key Vault, a Function App, a Log Analytics workspace, Network Security Group, Azure Container Registry, Storage account, etc.). All these resources are defined in the JSON template so they are created together.

For the lab i used a special Azure deployment link that opens the Azure Portal and starts the process of deploying a resource using a predefined ARM (Azure Resource Manager) template hosted on GitHub. It’s commonly used in labs, tutorials, or automation scenarios to quickly set up cloud infrastructure.

To deploy, sign in to the Azure Portal and use the search bar to type Deploy a custom template. Select the Deploy a custom template option (as shown above). This opens the Custom deployment page. Here, you provide deployment details:

  <img width="400" height="220" alt="image" src="https://github.com/user-attachments/assets/088badf8-0c4d-459e-bb56-2da30a4ba181" />

[Retrieve a custom template](https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/quickstart-create-templates-use-the-portal#retrieve-a-custom-template)

- Subscription: Choose your Azure subscription.
- Resource group: Create a new resource group (e.g. asclab-rg) or use an existing one.
- Region: Select a region (e.g. “West Europe”). All resources will be deployed in this region.
- Administrator password: Enter a strong admin password (minimum 12 characters with mixed-case, numbers, and symbols) for the VMs/SQL in the template.
- After entering these values, click Review + create, and then Create to start the deployment. Azure validates the template and then provisions the resources. The deployment can take several minutes (typically ~10 minutes).

  <img width="450" height="230" alt="image" src="https://github.com/user-attachments/assets/d711a997-6198-4bde-b9fd-20d48c10e4a9" /> <img width="450" height="230" alt="image" src="https://github.com/user-attachments/assets/b93880eb-c52f-4b15-9dcc-36265046ca38" />
  <img width="450" height="230" alt="image" src="https://github.com/user-attachments/assets/44fbcfca-9322-4f8e-9a3c-2272735acbad" /> 

Once the deployment is initiated, you can monitor its progress. Go to Resource groups in the portal, open the new resource group you created, and select Deployments. You should see the deployment in progress. When it finishes, each resource will show Provisioning state: Succeeded

  <img width="450" height="230" alt="image" src="https://github.com/user-attachments/assets/e082c41c-ddf3-4760-a350-2f0048fc0e62" />

# Enable Microsoft Defender for Cloud

In this hands-on Azure lab, I successfully provisioned essential cloud resources using an Azure Resource Manager (ARM) template, which helped in understanding infrastructure-as-code (IaC) for automated deployment. Following resource setup, I enabled Microsoft Defender for Cloud at the subscription level, configuring advanced security features to enhance cloud workload protection and posture management.

Key configurations included:

- Enabling Cloud Security Posture Management (CSPM) plans, including the foundational (free) and Defender CSPM tiers, which provide agentless vulnerability scanning, data-aware security assessments, cloud security graphs, and threat hunting capabilities. All these comes with different pricing which can be reviewed depending on the resource (e.g., $5/resource/month for 5 resources).
- Activating Cloud Workload Protection (CWP) for comprehensive, cloud-native protections across development and runtime environments, supporting multi-cloud integrations (e.g., AWS, GCP).
- Assigning tenant-level permissions by granting the "Security Admin" role at the root management group, ensuring tenant-wide visibility and adherence to least-privilege principles.
- Setting up data collection in Log Analytics workspaces, selecting "All Events" for Windows security and AppLocker logs to enable detailed auditing, threat detection, and analysis.
- Configuring additional components such as agentless scanning for machines, sensitive data discovery integrated with Microsoft Purview, permissions management (CIEM) for overprovisioned identities, and API security posture management to mitigate risks like OWASP threats.

  The lab progressed through environment settings, verifying full Defender coverage (e.g., 12/12 plans), and utilizing the overview dashboard to monitor secure scores, recommendations, attack paths, and alerts. This exercise aided in improving skills in Azure Portal navigation, security policy enforcement, multi-cloud security, and troubleshooting limited visibility issues via role assignments and refreshes.
  
<img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/3c1f97ce-fd66-4988-9fc9-5e0a6e53370e" /> <img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/af6d2a02-130c-4e68-bfa3-85177fad66c2" />
<img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/93535088-950c-488f-be0f-47a0cb34a6e4" /> <img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/784acc86-fa45-4273-97ee-0c468c760989" />
<img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/22039719-3d53-4800-8dd2-9f0fbdc3973c" /> <img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/f563a559-6b87-43f9-a2c2-f3bf8155e378" />
<img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/cdf4932e-8613-4773-9ad6-e78a96dd5d70" /> <img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/98cd425a-57a8-481e-96bc-235a1554d057" />
<img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/8756e317-90a3-477d-93d8-222413be0001" /> <img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/3f0bf1e4-ccdb-42ed-81aa-8f680a5ca5ff" />
<img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/8e82cd3b-22c1-453a-bcaf-7e828be3647d" /> <img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/a1923e47-670f-4dc4-9528-a3518c86e6e4" />
<img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/c3521d78-4f57-4b2a-a7da-4a7a9d85080f" /> <img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/400e65b7-8338-48fb-be3f-b9b6938daede" />
<img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/515537e1-96f3-4fd0-b555-69c594cec5e9" /> <img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/9e80e448-2f88-4bea-bb2a-30c1679982b1" />
<img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/8efc0baa-7df0-4dc7-bd6d-789a28814e1a" /> <img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/48624e66-9173-46c2-989b-a378e9e94967" />
<img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/0a6c2063-0d2f-49e7-808c-c3873b92547d" /> <img width="360" height="140" alt="image" src="https://github.com/user-attachments/assets/b00c2118-a96f-4feb-9cba-2598bb2b3c9c" />










