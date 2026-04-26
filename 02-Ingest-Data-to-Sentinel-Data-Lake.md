# Ingest Data to Sentinel Data Lake

This lab walks you through ingesting sample IdentityDrift telemetry (and supporting tables) into your Sentinel data lake so subsequent labs have data to query.

## Overview

### Typical Production Approach for ISVs

**ISVs** usually follow below approach to ingest data into Sentinel:

1. **Develop a Data Connector** 
    -  Create a Sentinel data connector using the [Sentinel Connector Builder Agent](https://learn.microsoft.com/en-us/azure/sentinel/create-custom-connector-builder-agent) in VS Code with GitHub Copilot. This AI-assisted approach reduces development time from weeks to hours and use natural language prompts to build polling configurations, data collection rules, connector definitions, and schemas. 
    - For pull-based data sources, use [Codeless Connector Framework (CCF)](https://learn.microsoft.com/en-us/azure/sentinel/create-codeless-connector) 
    - For push-based data sources, use [CCF Push](https://learn.microsoft.com/en-us/azure/sentinel/create-push-codeless-connector).
2. **Ingest Data to Data Lake** — Stream telemetry through the connector into Sentinel's data lake
3. **Leverage Sentinel Platform** — Use [Sentinel platform capabilities](https://www.microsoft.com/en-us/security/business/siem-and-xdr/microsoft-sentinel#Capabilities) for Data exploration, Graph, MCP server and build Security Copilot Agents.

**Alternative:** If a connector already exists for your data source, refer to the [Sentinel Data Connectors Reference](https://learn.microsoft.com/en-us/azure/sentinel/data-connectors-reference) to enable it and start ingesting the data.

### Lab Approach: Ingest Sample Data via KQL Jobs

For **this lab**, we take a pragmatic shortcut using **KQL Jobs** to populate data lake with sample records. This approach:

- ✅ **Mirrors the actual data schema** — Sample data adheres to the same schema as connector‑ingested data, letting you populate the data lake and test agent logic immediately
- ✅ **Represents realistic attack scenarios** — Mock data reproduces the attack patterns and correlations you'd investigate in production

## Prerequisites

### Onboarding
You must first onboard to the data lake. See the [Sentinel Data Lake Onboarding guide](./01-Sentinel-DataLake-Onboarding.md) for instructions.

### Required Permissions
- User need to be **Security Administrator** or **Security Operator**

## Step-by-Step: Ingest Sample Data Using a KQL Job

### Step 1: Data Lake Exploration - Jobs

1. Click on **Jobs** and **Create a new KQL job**
2. **Job name** - Enter a unique job name, Example: CommonSecurity_ID_logs
2. **Job Description** - Provide context and purpose of the job, Example: Generate logs for IdentityDrift vendor to ingest to CommonSecurity_ID_logs
3. **Select workspace** - Choose the destination workspace.
4. **Select destination table:**
   - **Option A:** Select **"Create a new table"** and enter a table name. Example: CommonSecurity_ID
     - Tables created by KQL jobs automatically have the suffix `_KQL_CL` appended
   
### Step 2: Review and Prepare Query

1. Copy KQL Query from KQL-Jobs folder. Example: Copy the query in [CommonSecurity_ID_Logs](KQL-Jobs/CommonSecurity_ID_Logs)

### Step 3: Schedule the Job
1. Select **Next**
2. On the **Schedule the query job** page, select your execution option:
   - **Scheduled job** - Job runs on a schedule you specify and ingest sample data periodically.

   Schedule Job option to have recurring records added to the table. 

**For Scheduled Jobs:**
1. Select **Schedule** option
2. Enter the following details:
   - **Repeat frequency** - Select: By minute, Hourly, Daily, Weekly, or Monthly
   - **Repeat every** - How often the job runs based on selected frequency
   - **From date** - Select date and enter time for when job should start
     - **Requirement:** Start time must be at least 30 minutes after job creation
   - **To date** - Select when the schedule finishes
     - **Option:** Select "Set job to run indefinitely" to continue without end date

### Step 4: Review and Submit
1. Select **Next** to review job details
2. Review all settings
3. Select **Submit** to create the job

### Repeat the above steps to ingest data into the SigninLogs, AADRiskyUsers, DeviceProcessEvents and SecurityAlerts tables by executing the KQL jobs provided in the [KQL-Jobs](./KQL-Jobs/)

| KQL Job | Table Name |
|---------|-----------|
| SigninLogs | SigninLogs |
| AADRiskyUsers | AADRiskyUsers |
| DeviceProcessEvent | DeviceProcessEvents | 
| SecurityAlerts | SecurityAlerts |

## 🔄 Next Steps

Great! Your data lake is now populated with sample telemetry from IdentityDrift, Microsoft Entra ID and Microsoft Defender.

**Next:** Proceed to [Lab 3: Setting Up Sentinel MCP Server in VS Code](./03-Sentinel-MCP-VSCode-Setup.md) to explore Sentinel MCP Server tools and query the data using prompts.