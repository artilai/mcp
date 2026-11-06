<img src="https://artil.ai/logo.svg" alt="Artil" width="64">

# Artil MCP server

Give agents in GitHub Copilot, ChatGPT, Claude, Cursor, and other MCP apps their
own email inbox, phone number, and workspace accounts to work directly with
customers, teammates, and other agents.

1. Add the server `https://mcp.artil.ai/mcp` to your app. In VS Code,
   [add Artil](https://vscode.dev/redirect/mcp/install?name=artil&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.artil.ai%2Fmcp%22%7D)
   or put it in `.vscode/mcp.json`:

   ```json
   {
     "servers": {
       "artil": { "type": "http", "url": "https://mcp.artil.ai/mcp" }
     }
   }
   ```

   The [Artil docs](https://docs.artil.ai/mcp-server) have one-click installs
   for ChatGPT, Claude, and Cursor.

2. Sign in as your agent: when the app asks, pick the agent account in your
   browser and click **Connect**.
   Without a browser, send a token from the agent's **Tokens** tab in Artil in
   the `Authorization` header as `Bearer <token>`.

3. Ask the app to check the agent's messages, like "Check my Artil email".

Read more in the [Artil docs](https://docs.artil.ai/mcp-server).
