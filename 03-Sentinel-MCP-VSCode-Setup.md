# Setting Up Sentinel MCP Server in VS Code

## Prerequisites

### Onboarding
You must first onboard to the data lake. See the [Sentinel Data Lake Onboarding guide](./01-Sentinel-DataLake-Onboarding.md) for instructions.

### System Requirements
- Visual Studio Code installed
- AI Toolkit or similar MCP-enabled extension

### Required Permissions
- Account with at least **Security Reader** role
- Access to Microsoft Sentinel workspace
- Azure account with appropriate permissions

### References
For more detailed information, see:
- [Get started with Microsoft Sentinel MCP server](https://learn.microsoft.com/en-us/azure/sentinel/datalake/sentinel-mcp-get-started)
- [Create and use custom Microsoft Sentinel MCP tools](https://learn.microsoft.com/en-us/azure/sentinel/datalake/sentinel-mcp-create-custom-tool)

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

### Step 2: Allow Authentication

1. When prompted, VS Code will display an authentication dialog
2. Select **"Allow"** to authenticate using an account with at least a **Security Reader** role
3. You may need to:
   - Log in with your organizational credentials
   - Approve permissions when prompted
   - Wait for the authentication to complete

**Authentication Status:**
- Once authenticated, the MCP server connection is established
- The server status should show as connected in the VS Code MCP interface

### Step 3: Open VS Code Chat

1. Select **View > Chat** from the menu bar
   - **OR** Select the Toggle Chat icon beside the search bar
   - **OR** Press **Ctrl + Alt + I** (Windows/Linux) or **Cmd + Alt + I** (macOS)

2. The Chat panel opens at the right side of your editor

### Step 4: Verify Connection and Configure Tools

#### Set Chat to Agent Mode
1. In the VS Code Chat panel, look for mode selection (typically at the top)
2. Set the chat mode to **"Agent"** mode
   - This enables the use of external tools and MCP servers

#### Confirm MCP Server Connection
1. Look for the **"Configure Tools"** icon within the MCP server section
2. Select the Configure Tools icon next to the MCP server you added
3. You should see the server name you assigned (e.g., "Microsoft Sentinel MCP server")
4. A list of available tools from the MCP server should appear

#### Verify Available Tools
- The Chat interface should display available tools from your connected MCP server
- You can now use these tools in your AI agent queries

## Using Sentinel MCP Tools in Chat

Once your MCP server is configured, you can:

1. **Ask the AI agent questions** that require Sentinel tool usage
2. **Reference Sentinel data** directly in your queries
3. **Request security investigations** that leverage pre-built tools
4. **Query data lake** using integrated KQL capabilities

### Example Interactions
- "Analyze recent sign-in activity and surface anomalies"
- "Query the data lake for suspicious activity on endpoints"

