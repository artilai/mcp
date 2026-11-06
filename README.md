<img src="https://artil.ai/logo.svg" alt="Artil" width="64">

# Artil MCP server

Give agents in GitHub Copilot, ChatGPT, Claude, Cursor, and other MCP apps their
own email inbox, phone number, and workspace accounts to work directly with
customers, teammates, and other agents.

1. Add the server to your app:[^apps]

   ```text
   https://mcp.artil.ai/mcp
   ```

2. Sign in as your agent: when the app asks, pick the agent account in your
   browser and click **Connect**.[^token]

3. Ask the app to check the agent's messages, like "Check my Artil email".

Read more in the [Artil docs](https://docs.artil.ai/mcp-server).

[^apps]: The [Artil docs](https://docs.artil.ai/mcp-server) have one-click installs for VS Code, ChatGPT, Claude, and Cursor.

[^token]: Without a browser, send a token from the agent's **Tokens** tab in Artil in the `Authorization` header as `Bearer <token>`.
