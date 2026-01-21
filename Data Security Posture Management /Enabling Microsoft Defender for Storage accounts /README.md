# Microsoft Defender for Storage Lab Tutorial

This guide outlines a practical lab exercise on enabling and setting up Microsoft Defender for Storage in Azure. The main goal is to activate Microsoft Defender for Storage at the subscription level and adjust its settings to provide stronger protection. This helps safeguard Azure Blob Storage against risks like malware uploads and unauthorized access to sensitive information.
We use the Azure Portal to turn on the service, check costs and coverage, and customize options such as limits on malware scanning and detection of sensitive data. This setup works with Microsoft Purview for classifying data and offers real-time alerts for threats. It is useful for ensuring security and meeting compliance standards in cloud storage.
The lab has two key exercises:

- Exercise 1: Turn on Microsoft Defender for Storage via the Azure Portal.
- Exercise 2: Adjust the settings for Microsoft Defender for Storage, including changes to subscription-wide options.

This lab helped my understanding in configuring Azure security, managing policies, and protecting against threats. It is relevant for jobs in cloud security, DevSecOps, or Azure management.

# Step-by-Step Guide

Exercise: Turn On Microsoft Defender for Storage in the Azure Portal

Step 1: In the Environment settings page, clicking the "Contoso-Security-078" Azure subscription under the main tenant group. It lists 10 total resources and 12/12 coverage for Defender plans.
This check in the lab confirms that turning on and adjusting Defender for Storage has updated the full environment coverage. Reaching 12/12 plans means there are resourced linked and worked well. The exercise ensures that there are no missing parts, and it is ready for adding other resource to the cloud if wanted. This overall check connects back to the goal of protection across the subscription.

<img width="260" height="140" alt="image" src="https://github.com/user-attachments/assets/55d81f2a-9314-42df-a5ae-e23c2aed4b33" />

Step 2: Shows the Defender plans page, Pricing and Services, listing plans like Servers, App Service, Databases, Storage, Containers, Key Vault, Resource Manager.
- This checks the status of all Defender plans, with focus on turning on Storage. The lab shows how to review resource counts, costs, and coverage to ensure full protection across services. Activating Storage here changes the default subscription settings, adding checks for malware on uploads and threats to sensitive data.
  
<img width="260" height="140" alt="image" src="https://github.com/user-attachments/assets/60be5911-8d7e-4904-bac6-42347c50a881" />

Step 3: Focus on Details of the Storage Plan.
- The Storage plan lets you adjust specifics. It guides to see details like cost splits ($10 per account per month + $0.15 per GB for scans). This part of the Exercise helps understand cost matters and change settings, like scan limits. It is important for planning budgets and fitting protection to your needs, avoiding surprise costs while keeping security strong.
  
<img width="260" height="140" alt="image" src="https://github.com/user-attachments/assets/e7c095ff-4512-42ce-831b-185079ca2451" />

Step 4: Storage Plan Details pane for Defender for Storage. It lists benefits like detecting harmful access, filtering data outflows, and spotting threats to sensitive data. Advantages include easy setup, ongoing log checks, use of Microsoft Threat Intelligence, creating alerts for SIEM systems, finding exposure risks, and scanning for malware on uploads.
- Helps to know why Defender for Storage is valuable, including links to Azure Blobs, Data Lake Storage, and Files. The lab uses this for setting changes, like turning on logs or agents. It stresses active security, for example, spotting malware almost instantly and sorting sensitive data with Purview. This step gives background on why activating this plan matters for places with lots of stored data.
  
<img width="260" height="140" alt="image" src="https://github.com/user-attachments/assets/de0cb9c4-5647-49e9-bbd6-6fee684dc601" /> <img width="260" height="140" alt="image" src="https://github.com/user-attachments/assets/b8b5392e-f35b-4733-ae78-8bd6a775532d" />

Step 5: Go to Settings and Monitoring for Storage
- This displays the "Settings & monitoring" page in Microsoft Defender for Cloud > Environment settings > Defender plans. It highlights the "Storage" plan, with features like "Malware scanning" (turned on, with a 5000 GB scan limit, costing $0.15 per GB) and "Sensitive data discovery" (turned on, linked to Microsoft Purview).
- This step takes you to the area where you set up Defender for Storage. Turning on these features protects Azure Blob Storage by checking uploads for harmful software right away and finding sensitive data through smart checks and labels. The lab aims to confirm or activate these at the subscription level, allowing changes to standard settings. This improves overall security by giving quick scan results for automated actions and rules following. In real use, it stops data leaks and supports laws like GDPR.
  
<img width="260" height="140" alt="image" src="https://github.com/user-attachments/assets/d1fc6045-2d82-4b57-85af-b83620362316" /> <img width="260" height="140" alt="image" src="https://github.com/user-attachments/assets/8be6408a-ee3d-4e0d-946e-90ad5ec66b0a" />
<img width="260" height="140" alt="image" src="https://github.com/user-attachments/assets/99500580-843c-4d94-99c5-2c59ed3592d2" />


