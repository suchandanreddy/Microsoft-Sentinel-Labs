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
- Create a Log Analytics workspace in Azure Portal
- Sign in to Defender portal
- Complete data lake onboarding process
- Connect SIEM workspace and select subscription/resource group
- Monitor onboarding progress

### 2. [Creating KQL Jobs in Sentinel Data Lake Exploration](./02-Create-KQL-Jobs.md)

This lab shows how to use KQL Jobs as a  shortcut to populate data lake with sample data:
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

This lab uses Azure AI Foundry as **developer playground** to build, test, and refine agent instructions before building Security Copilot Agent:
- Create an agent and configure instructions for security investigations
- Integrate Sentinel Data Exploration MCP Server to query data
- Querying multiple data sources: CommonSecurity_ID_KQL_CL, SigninLogs_KQL_CL, AADRiskyUsers_KQL_CL, DeviceProcessEvents_KQL_CL and SecurityAlerts_KQL_CL
- Correlate identity risk, authentication signals, access telemetry, and endpoint activity
- Test and iterate on agent behavior with realistic IdentityDrift scenarios


### 5. [Building an Agent in Security Copilot](./05-Building-an-Agent-in-Security-Copilot.md)

This lab guides you through building a Security Copilot agent that correlates identity risk across multiple security signals:
- Creating and managing Security Copilot workspaces
- Provisioning Security Compute Units (SCUs) for agent execution
- Configuring agent instructions for identity risk investigation
- Integrating Sentinel MCP tools into agent
- Running and testing agent scenarios.

**Fictional ISV Scenario:** IdentityDrift - Identity-aware access intelligence
### 6. [Publishing Agent to Security Store](./06-Publishing-Agent-to-Security-Store.md)

This lab guides you through publishing your Security Copilot agent to the Microsoft Security Store:
- Creating a deployment package (.zip) with agent manifest and dependencies
- Publishing your agent offer in Microsoft Partner Center

## 📋 Prerequisites Checklist

Before starting these labs, ensure you have:

- [ ] **Azure Account**
  - **Active Azure subscription** is required to complete all labs
  - If you don't have an Azure account:
    - **Sign up for a free Azure account** at https://azure.microsoft.com/pricing/purchase-options/azure-account/
    - New Azure accounts receive **$200 in free credits** for the first 30 days
  - Appropriate administrative roles mentioned in prerequisites section of each lab

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

1. **Start with Lab 1:** [Sentinel Data Lake Onboarding](./01-Sentinel-DataLake-Onboarding.md)
   - Establish the foundation by setting up your data lake
   - Allow 60-120 minutes for the onboarding process
                     
2. **Lab 2:** [Creating KQL Jobs](./02-Create-KQL-Jobs.md)
   - Learn to create sample data jobs
   - Ingest IdentityDrift telemetry and other test data

3. **Lab 3:** [MCP Server Setup](./03-Sentinel-MCP-VSCode-Setup.md)
   - Configure VS Code to use Sentinel MCP Server

4. **Lab 4:** [Building an Agent in Azure AI Foundry](./04-Building-an-Agent-in-Azure-AI-Foundry.md)
   - Create an agent
   - Correlate signals across identity, access, and endpoint data

5. **Lab 5:** [Building an Agent in Security Copilot](./05-Building-an-Agent-in-Security-Copilot.md)
   - Create an agent in Security Copilot
   - Test running the agent to correlate signals across identity, access, and endpoint data

6. **Lab 6:** [Publishing Agent to Security Store](./06-Publishing-Agent-to-Security-Store.md)
   - Package your agent
   - Create SaaS offer in Partner Center
   - Publish to Security Store for customer acquisition

## 📁 Lab Structure

```
Labs/
├── 01-Sentinel-DataLake-Onboarding.md
├── 02-Create-KQL-Jobs.md
├── 03-Sentinel-MCP-VSCode-Setup.md
├── 04-Building an Agent in Azure AI Foundry.md
├── 05-Building-an-Agent-in-Security-Copilot.md
├── 06-Publishing-Agent-to-Security-Store.md
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

## 📖 Additional Resources

Enhance your understanding of agent development with these complementary blogs:

- **[Accelerate Agent Development: Hacks for Building with Microsoft Sentinel Data Lake](https://aka.ms/AppAssure_AccelerateAgentDev)** — Outlines the complete **Composite Application Model** (data sources → ingestion → data lake → agent → end user) and walks through all five phases of agent development: data ingestion design, Sentinel data lake onboarding, building and testing in Foundry, migration to Security Copilot, and publishing. This blog provides the architectural framework and proven patterns.

- **[Agentic Use Cases for Developers on the Microsoft Sentinel Platform](https://aka.ms/AppAssure_AgenticUseCases)** — Discover how ISV developers can build Security Copilot agents aligned with their product expertise: Identity Intelligence, Cyber Resilience, Networking, Endpoint Detection & Response, Asset exploitability, and Threat Intelligence. Each use case shows how to correlate your product's signals with Sentinel data to deliver fast, repeatable SOC investigation workflows that solve security problems at scale.


