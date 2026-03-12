# Microsoft Sentinel Labs

Welcome to the Microsoft Sentinel Labs! This directory contains comprehensive guides for setting up Microsoft Sentinel's data lake capabilities and creating Security Copilot agent.

## 🎓 Lab Scenario: IdentityDrift Investigation

The labs culminate in a realistic security investigation scenario:

### The Scenario
A user (`u1291@contoso.onmicrosoft.com`) experiences unusual authentication patterns:
- Sign-in from new geographic location
- Multi-factor authentication triggered
- Privileged access to production Kubernetes cluster (prod-aks-eastus)
- Privilege escalation detected via RoleBinding creation
- Suspicious endpoint process execution (kubectl commands)

### Your Agent Will:
1. Query identity access data from IdentityDrift
2. Correlate with Entra ID sign-in logs
3. Assess risk level from AAD Risk Detection
4. Analyze endpoint and cloud workload alerts
5. Surface actionable insights for security response

### Outcome
Determine whether the sign-in is a legitimate identity activity or an initial access event requiring immediate containment.

## 📚 Lab Contents

### 1. [Sentinel Data Lake Onboarding](./01-Sentinel-DataLake-Onboarding.md)

This lab guides you through the initial setup of your Microsoft Sentinel data lake:
- Sign in to Defender portal
- Complete onboarding process
- Verify permissions and prerequisites
- Monitor onboarding progress

### 2. [Creating KQL Jobs in Sentinel Data Lake Exploration](./02-Create-KQL-Jobs.md)

This lab covers creating and scheduling KQL jobs to ingest and analyze data:
- Creating KQL jobs with sample data
- Scheduling recurring jobs
- Ingesting fictional ISV telemetry (IdentityDrift)
- Creating tables: CommonSecurity_ID_KQL_CL, SigninLogs_KQL_CL, AADRiskyUsers_KQL_CL, DeviceProcessEvents_KQL_CL and SecurityAlerts_KQL_CL

### 3. [Setting Up Sentinel MCP Server in VS Code](./03-Sentinel-MCP-VSCode-Setup.md)

This lab explains how to integrate Sentinel tools with VS Code's AI agents:
- Adding MCP servers in VS Code
- Authentication setup
- Using Sentinel MCP server in VS code

### 4. [Building an Agent in Azure AI Foundry](./04-Building-an-Agent-in-Azure-AI-Foundry.md)

This lab guides you through building an intelligent agent that correlates security signals:
- Creating an agent in Azure AI Foundry
- Configuring agent instructions for security investigations
- Integrating Sentinel Data Exploration MCP Server
- Querying multiple data sources: CommonSecurity_ID_KQL_CL, SigninLogs_KQL_CL, AADRiskyUsers_KQL_CL, DeviceProcessEvents_KQL_CL and SecurityAlerts_KQL_CL
- Correlating identity risk, authentication signals, access telemetry, and endpoint activity
- Testing the agent scenarios

### 5. [Building an Agent in Security Copilot](./05-Building-an-Agent-in-Security-Copilot.md)

This lab guides you through building a Security Copilot agent that correlates identity risk across multiple security signals:
- Creating and managing Security Copilot workspaces
- Provisioning Security Compute Units (SCUs) for agent execution
- Configuring agent instructions for identity risk investigation
- Integrating Sentinel MCP tools into agent
- Running and testing agent scenarios.

**Fictional ISV Scenario:** IdentityDrift - Identity-aware access intelligence

## 📋 Prerequisites Checklist

Before starting these labs, ensure you have:

- [ ] **Azure Account**
  - Active Azure subscription
  - Appropriate administrative roles mentioned in prerequisites section of each lab.

- [ ] **Access & Permissions**
  - Access to Microsoft Defender portal (https://security.microsoft.com/)
  - Access to Azure portal
  - Access to Microsoft Sentinel workspace
  - Access to Azure AI Foundry (https://ai.azure.com/) for Lab 4
   - Access to Security Copilot (https://securitycopilot.microsoft.com/) for Lab 5

- [ ] **Software & Tools**
  - Visual Studio Code installed (for Lab 3)
  - Modern web browser for Defender, Azure, and AI Foundry portals

## 🎯 Recommended Learning Path

### For Complete Beginners:
1. **Start with Lab 1:** [Sentinel Data Lake Onboarding](./01-Sentinel-DataLake-Onboarding.md)
   - Establish the foundation by setting up your data lake
   - Allow 60-120 minutes for the onboarding process

2. **Then Lab 2:** [Creating KQL Jobs](./02-Create-KQL-Jobs.md)
   - Learn to create sample data jobs
   - Ingest IdentityDrift telemetry and other test data

3. **Then Lab 3:** [MCP Server Setup](./03-Sentinel-MCP-VSCode-Setup.md)
   - Configure VS Code to use Sentinel MCP Server

4. **Then Lab 4:** [Building an Agent in Azure AI Foundry](./04-Building-an-Agent-in-Azure-AI-Foundry.md)
   - Create an agent
   - Correlate signals across identity, access, and endpoint data

5. **Finally Lab 5:** [Building an Agent in Security Copilot](./05-Building-an-Agent-in-Security-Copilot.md)
   - Create an agent in Security Copilot
   - Test running the agent to correlate signals across identity, access, and endpoint data

## 📁 Lab Structure

```
Labs/
├── 01-Sentinel-DataLake-Onboarding.md
├── 02-Create-KQL-Jobs.md
├── 03-Sentinel-MCP-VSCode-Setup.md
├── 04-Building an Agent in Azure AI Foundry.md
├── 05-Building-an-Agent-in-Security-Copilot.md
├── KQL-Jobs/
│   ├── CommonSecurity_ID_Logs          (IdentityDrift access telemetry)
│   ├── SigninLogs                       (Azure AD sign-in events)
│   ├── AADRiskyUsers                    (Azure AD risk detection)
│   ├── DeviceProcessEvents              (Endpoint process execution)
│   └── SecurityAlerts                   (Defender for Cloud Alerts)
├── DataLake-Onboarding/
├── Images/                              (Screenshots and diagrams)
└── README.md
```


