# Sentinel Data Lake Onboarding Steps

## Overview
This lab guides you through onboarding your tenant to the Microsoft Sentinel data lake from the Microsoft Defender portal.

## Prerequisites

### Required Permissions
- User need to be either a Global Administrator or Security Administrator in Microsoft Entra ID **AND** Subscription Owner or User Access Administrator (Azure IAM role) **AND** Microsoft Sentinel Contributor role.

### Required Access
- Access to Microsoft Defender portal at https://security.microsoft.com/

## Step-by-Step Onboarding Instructions 

### Step 1: Create Log Analytics Workspace in Azure Portal
Before onboarding to the data lake, you need to create or have access to a Log Analytics workspace.

1. Sign in to the **Azure portal** at https://portal.azure.com/
2. Use the search bar to search for **Microsoft Sentinel** and select it
3. Click **Create** button
4. Select **Create a new workspace**
5. Under **Subscription > Resource group**, select **Create new** to create a new resource group
   - Enter a name for your resource group (e.g., `sentinel-rg`) and click **OK**
6. Configure the workspace:
   - **Workspace name:** Enter a descriptive name (e.g., `sentinel-workspace`)
   - **Region:** Select an appropriate region (refer to [which regions are Data lake supported](https://learn.microsoft.com/en-us/azure/sentinel/geographical-availability-data-residency#supported-regions)) (e.g., Select `Central-US` or `South Central US`)
7. Click **Review + Create** to validate the configuration
8. Click **Create** and wait for the deployment to complete (this may take a few minutes)

**Reference:** [Create a Log Analytics workspace - Microsoft Docs](https://learn.microsoft.com/en-us/azure/sentinel/quickstart-onboard?tabs=defender-portal#create-a-log-analytics-workspace)

---

### Step 2: Sign In to Defender Portal
1. Open your web browser and navigate to **https://security.microsoft.com/**
2. Sign in with your credentials that have the required permissions

### Step 3: Initiate Data Lake Onboarding
1. Look for a banner at the top of the Defender portal home page indicating you can onboard to the Microsoft Sentinel data lake
2. Click the **"Get started"** button on the banner
   - *Alternative method:* If the banner is accidentally closed, navigate to **System > Settings > Microsoft Sentinel > Data lake**
   
![Microsoft Sentinel DataLake Settings](Images/Data%20Lake%20Onboarding-1.png)
   
### Step 4: Connect SIEM Workspace
1. If you don't have the correct roles specified in **Required Permissions**, Sentinel workspace doesn't show up here and filter might not show Subscriptions.


2. Select Workspace, then **Connect workspace** and set it as Primary. 

![Microsoft SIEM Workspace](Images/Data%20Lake%20Onboarding-2.png)

### Step 5: Select Subscription and Resource Group
1. Click on **Start setup** under **Data lake**, If you don't have the correct roles specified in **Required Permissions**, side panel will appear indicating missing permissions
![Microsoft Data lake setup](Images/Data%20Lake%20Onboarding-3.png)

2.   In the setup side panel, select your target **Subscription** from the dropdown

3. Select the target **Resource group** to enable billing for the Microsoft Sentinel data lake

4. Click the **Set up data lake** button
![Microsoft Data lake setup](Images/Data%20Lake%20Onboarding-4.png)

### Step 6: Monitor Onboarding Progress
1. The setup process begins and displays a progress panel
2. The onboarding process can take **up to 60 minutes** to complete
3. You can safely close the setup panel while the process runs in the background
4. A banner will be displayed on the Defender portal home page showing "Setup in progress"

### Step 7: Complete Onboarding
1. Once the onboarding process is complete, a new banner appears with information cards on how to use your new data lake. Verify **Data lake exploration** under **Microsoft Sentinel**

![Microsoft Sentinel Data lake exploration](Images/Data%20Lake%20Onboarding-5.png)

## 🔄 Next Steps

Congratulations! Your Sentinel data lake is now onboarded and ready for data ingestion.

**Next:** Proceed to [Lab 2: Ingest Data to Sentinel Data Lake](./02-Ingest-Data-to-Sentinel-Data-Lake.md) to ingest sample telemetry into data lake.

## References
For more detailed information, see:

- [Microsoft Docs - Onboard to Microsoft Sentinel data lake from the Defender portal](https://learn.microsoft.com/en-us/azure/sentinel/datalake/sentinel-lake-onboard-defender)