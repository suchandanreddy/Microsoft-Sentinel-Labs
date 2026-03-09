# Creating KQL Jobs in Sentinel Data Lake Exploration

## Prerequisites

### Onboarding
You must first onboard to the data lake. See the [Sentinel Data Lake Onboarding guide](./01-Sentinel-DataLake-Onboarding.md) for instructions.

### Required Permissions
- User need to be **Security Administrator** or **Security Operator**

## Step-by-Step: Creating a KQL Job to Ingest Sample Data

### Step 1: Data Lake Exploration - Jobs

1. Click on **Jobs** and **Create a new KQL job**
2. **Job name** - Enter a unique job name, Example: CommonSecurity_ID_logs
2. **Job Description** - Provide context and purpose of the job, Example: Generate logs for IdentityDrift vendor to ingest to CommonSecurity_ID_logs
3. **Select workspace** - Choose the destination workspace.
4. **Select destination table:**
   - **Option A:** Select **"Create a new table"** and enter a table name. Example: CommonSecurity_ID
     - Tables created by KQL jobs automatically have the suffix `_KQL_CL` appended
   
### Step 2: Review and Prepare Query

1. Copy KQL Query from KQL-Jobs folder. Example: Copy the query in[CommonSecurity_ID_Logs](KQL-Jobs/CommonSecurity_ID_Logs)

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