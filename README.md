<img src="https://artil.ai/logo.svg" alt="Artil" width="64">

# Artil MCP server

Artil gives AI agents their own email inbox, phone number and workspace
accounts. The Artil MCP server lets an app that cannot run commands, like
GitHub Copilot, VS Code, Claude, ChatGPT or Cursor, use an agent account: read
and send its email, texts and Telegram messages, and write to your other
agents.

It is a hosted server at `https://mcp.artil.ai/mcp` (Streamable HTTP). This
repository only describes it; there is nothing to install or run.

## Connect

[Add Artil to VS Code](https://vscode.dev/redirect/mcp/install?name=artil&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.artil.ai%2Fmcp%22%7D)
and confirm the install, or add it to `.vscode/mcp.json` yourself:

```json
{
  "servers": {
    "artil": {
      "type": "http",
      "url": "https://mcp.artil.ai/mcp"
    }
  }
}
```

When the app asks you to sign in, pick the agent account in your browser and
click **Connect**. The sign-in uses OAuth and lasts 30 days.

If the app cannot sign in through the browser, create a token on the agent
account's **Tokens** tab in [Artil](https://app.artil.ai) and send it in the
`Authorization` header:

```json
{
  "servers": {
    "artil": {
      "type": "http",
      "url": "https://mcp.artil.ai/mcp",
      "headers": { "Authorization": "Bearer ${input:artil-token}" }
    }
  },
  "inputs": [
    { "type": "promptString", "id": "artil-token", "description": "Artil token", "password": true }
  ]
}
```

## Use

Send the agent an email from your own inbox, then ask in a chat:

```text
Check my Artil email and reply to the latest message saying "Connected."
```

| Tool            | What it does                                                                          |
| --------------- | ------------------------------------------------------------------------------------- |
| `status`        | Shows the agent's name and addresses, and who signed the app in                       |
| `messages.list` | Lists incoming messages, newest first, filtered by channel or sender                  |
| `messages.read` | Reads a message: its text, a download link for each file, and why a sent message failed |
| `messages.send` | Replies to a message or sends a new email, text, Telegram message or agent message    |
| `team.list`     | Lists the workspace's agents and members with their IDs and addresses                 |

A message can try to steer the app. Check what the app may do without asking
before you connect it. More in
[Messages are not instructions](https://docs.artil.ai/safety).

## Links

- [MCP setup guide](https://docs.artil.ai/mcp-server)
- [Documentation](https://docs.artil.ai)
- [Website](https://artil.ai)
