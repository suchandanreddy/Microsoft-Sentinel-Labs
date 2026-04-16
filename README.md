# Microsoft Sentinel Labs

Welcome to the Microsoft Sentinel Labs! This directory contains comprehensive guides for setting up Microsoft Sentinel data lake, Sentinel MCP Server and building Security Copilot agent.

## 🎓 Lab Scenario: IdentityDrift Investigation

**Fictional ISV Scenario:** IdentityDrift - Identity-aware access intelligence

The labs culminate in a realistic security investigation scenario using **IdentityDrift**  telemetry ingested into the Sentinel data lake. You’ll build a Security Copilot agent that correlates IdentityDrift signals with Entra ID and Microsoft Defender data to drive end‑to‑end investigation workflows.

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

## 📋 Prerequisites

Before starting these labs, ensure you have:

- **Azure Account**
  - **Active Azure subscription** is required to complete all labs
  - If you don't have an Azure account:
    - **Sign up for a free Azure account** at https://azure.microsoft.com/pricing/purchase-options/azure-account/
    - New Azure accounts receive **$200 in free credits** for the first 30 days
  - Appropriate administrative roles mentioned in prerequisites section of each lab

- **Access & Permissions**
  - Access to Microsoft Defender portal (https://security.microsoft.com/)
  - Access to Azure portal (https://portal.azure.com/)
  - Access to Azure AI Foundry (https://ai.azure.com/) for Lab 4
   - Access to Security Copilot (https://securitycopilot.microsoft.com/) for Lab 5

- **Software & Tools**
  - Visual Studio Code installed (for Lab 3)

## 🎯 Recommended Learning Path

1. **Start with Lab 1:** [Sentinel Data Lake Onboarding](./01-Sentinel-DataLake-Onboarding.md)
   - Establish the foundation by setting up your data lake
   - Allow 60-120 minutes for the onboarding process
                     
2. **Lab 2:** [Creating KQL Jobs](./02-Create-KQL-Jobs.md)
   - Learn to create KQL jobs to ingest sample IdentityDrift telemetry and other test data

3. **Lab 3:** [Sentinel MCP Server Setup](./03-Sentinel-MCP-VSCode-Setup.md)
   - Use Sentinel MCP server in VS code

4. **Lab 4:** [Building an Agent in Azure AI Foundry](./04-Building-an-Agent-in-Azure-AI-Foundry.md)
   - Create an agent in AI Foundry
   - Correlate signals across identity, access, and endpoint data

5. **Lab 5:** [Building an Agent in Security Copilot](./05-Building-an-Agent-in-Security-Copilot.md)
   - Create an agent in Security Copilot
   - Test running the agent to correlate signals across identity, access, and endpoint data

6. **Lab 6:** [Publishing Agent to Security Store](./06-Publishing-Agent-to-Security-Store.md)
   - Package your agent
   - Create SaaS offer in Partner Center
   - Publish to Security Store 


![](Images/Learning%20Path.png)

## 📖 Additional Resources

Enhance your understanding of agent development with these complementary blogs:

- **[Accelerate Agent Development: Hacks for Building with Microsoft Sentinel Data Lake](https://aka.ms/AppAssure_AccelerateAgentDev)** — Outlines the complete **Composite Application Model** (data sources → ingestion → data lake → agent → end user) and walks through all five phases of agent development: data ingestion design, Sentinel data lake onboarding, building and testing in Foundry, migration to Security Copilot, and publishing. This blog provides the architectural framework and proven patterns.

- **[Agentic Use Cases for Developers on the Microsoft Sentinel Platform](https://aka.ms/AppAssure_AgenticUseCases)** — Discover how ISV developers can build Security Copilot agents aligned with their product expertise: Identity Intelligence, Cyber Resilience, Networking, Endpoint Detection & Response, Asset exploitability, and Threat Intelligence. Each use case shows how to correlate your product's signals with other data in Sentinel data lake to deliver fast, repeatable SOC investigation workflows that solve security problems at scale.


