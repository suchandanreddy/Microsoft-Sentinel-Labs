# Sentinel Data Lake Onboarding Steps

## Overview
This lab guides you through onboarding your tenant to the Microsoft Sentinel data lake from the Microsoft Defender portal. The onboarding process creates a new Microsoft Sentinel data lake for your tenant in the subscription specified during the onboarding process. Graph enablement is automatically included as part of onboarding.

## Prerequisites

### Required Permissions
- User need to be either a Global Administrator or Security Administrator in Microsoft Entra ID **AND** Subscription Owner or User Access Administrator (Azure IAM role) **AND** Microsoft Sentinel Contributor role.

### Required Access
- Access to Microsoft Defender portal at https://security.microsoft.com/

## Step-by-Step Onboarding Instructions 

### Step 1: Sign In to Defender Portal
1. Open your web browser and navigate to **https://security.microsoft.com/**
2. Sign in with your credentials that have the required permissions

### Step 2: Initiate Data Lake Onboarding
1. Look for a banner at the top of the Defender portal home page indicating you can onboard to the Microsoft Sentinel data lake
2. Click the **"Get started"** button on the banner
   - *Alternative method:* If the banner is accidentally closed, navigate to **System > Settings > Microsoft Sentinel > Data lake**
   
![Microsoft Sentinel DataLake Settings](Images/Data%20Lake%20Onboarding-1.png)
   
### Step 3: Connect SIEM Workspace
1. If you don't have the correct roles specified in **Required Permissions**, Sentinel workspace doesn't show up here and filter might not show Subscriptions.


2. Select Workspace, then **Connect workspace** and set it as Primary. 

![Microsoft SIEM Workspace](Images/Data%20Lake%20Onboarding-2.png)

### Step 4: Select Subscription and Resource Group
1. Click on **Start setup** under **Data lake**, If you don't have the correct roles specified in **Required Permissions**, side panel will appear indicating missing permissions
![Microsoft Data lake setup](Images/Data%20Lake%20Onboarding-3.png)

2.   In the setup side panel, select your target **Subscription** from the dropdown

3. Select the target **Resource group** to enable billing for the Microsoft Sentinel data lake

4. Click the **Set up data lake** button
![Microsoft Data lake setup](Images/Data%20Lake%20Onboarding-4.png)

### Step 5: Monitor Onboarding Progress
1. The setup process begins and displays a progress panel
2. The onboarding process can take **up to 60 minutes** to complete
3. You can safely close the setup panel while the process runs in the background
4. A banner will be displayed on the Defender portal home page showing "Setup in progress"

### Step 6: Complete Onboarding
1. Once the onboarding process is complete, a new banner appears with information cards on how to use your new data lake. Verify **Data lake exploration** under **Microsoft Sentinel**

![Microsoft Sentinel Data lake exploration](Images/Data%20Lake%20Onboarding-5.png)

**Reference:** [Microsoft Docs - Onboard to Microsoft Sentinel data lake from the Defender portal](https://learn.microsoft.com/en-us/azure/sentinel/datalake/sentinel-lake-onboard-defender)
