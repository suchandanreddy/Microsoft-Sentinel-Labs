# Setting Up Sentinel MCP Server in VS Code

## Prerequisites

You must first complete the previous labs:
- [Lab 1: Sentinel Data Lake Onboarding](./01-Sentinel-DataLake-Onboarding.md)
- [Lab 2: Creating KQL Jobs](./02-Create-KQL-Jobs.md)

## System Requirements
- Visual Studio Code installed

## Required Permissions
- Account with at least **Security Reader** role
- Access to Microsoft Sentinel workspace

## Step-by-Step Setup Instructions

### Step 1: Add MCP Server

#### Open MCP Server Configuration
1. Press **Ctrl + Shift + P** (Windows/Linux) or **Cmd + Shift + P** (macOS) to open the Command Palette
2. Type or select **`MCP: Add Server`**

#### Select Server Type
1. A menu will appear asking for the server type
2. Choose **"HTTP (HTTP or Server-Sent Events)"**

#### Enter MCP Server URL
1. Enter the URL **https://sentinel.microsoft.com/mcp/data-exploration** of the Sentinel MCP server
2. Press **Enter** to proceed

#### Assign Server ID
1. Assign a friendly **Server ID** for easy identification
   - **Recommended:** `Microsoft Sentinel MCP server` or similar descriptive name
   - This ID helps you identify which server is which if you add multiple MCP servers
2. Select MCP server to be available in all VS code workspaces or only in the current workspace

### Step 2: Allow Authentication

1. When prompted, VS Code will display an authentication dialog
2. Select **"Allow"** to authenticate using an account with at least a **Security Reader** role
3. You may need to:
   - Log in with your organizational credentials
   - Approve permissions when prompted
   - Wait for the authentication to complete

**Authentication Status:**
- Once authenticated, the MCP server connection is established

### Step 3: Open VS Code Chat

1. Select **View > Chat** from the menu bar
   - **OR** Select the Toggle Chat icon beside the search bar

2. The Chat panel opens at the right side of your editor

### Step 4: Verify Connection and Configure Tools

#### Set Chat to Agent Mode
1. In the VS Code Chat panel, Set the chat mode to **"Agent"** mode
   - This enables the use of external tools and MCP servers

#### Confirm MCP Server Connection
1. Look for the **"Configure Tools"** icon within the MCP server section
2. Select the Configure Tools icon next to the MCP server you added
3. You should see the server name you assigned (e.g., "Microsoft Sentinel MCP server")
4. A list of available tools from the MCP server should appear

## Using Sentinel MCP Tools in Chat

Once your MCP server is configured, you can:

1. **Ask the AI agent questions** that require Sentinel tool usage
2. **Request security investigations** that leverage pre-built tools
3. **Query Sentinel data lake** using integrated KQL capabilities

### Example Interactions
- "Analyze recent sign-in activity and surface anomalies"
- "Query the data lake for suspicious activity on endpoints"

## 🔄 Next Steps

Now that you’re familiar with the Sentinel MCP Server tool collections and their capabilities, the next step is to use these MCP tools and build an agent.

**Next:** Proceed to [Lab 4: Building an Agent in Azure AI Foundry](./04-Building-an-Agent-in-Azure-AI-Foundry.md) to build, test, and refine your agent using Azure AI Foundry.

## References
For more detailed information, see:
- [Get started with Microsoft Sentinel MCP server](https://learn.microsoft.com/en-us/azure/sentinel/datalake/sentinel-mcp-get-started)
- [Explore Microsoft Sentinel data lake with data exploration collection](https://learn.microsoft.com/en-us/azure/sentinel/datalake/sentinel-mcp-data-exploration-tool)
- [Create and use custom Microsoft Sentinel MCP tools](https://learn.microsoft.com/en-us/azure/sentinel/datalake/sentinel-mcp-create-custom-tool)