# StyTrix MCP Server

Connect AI agents to **[StyTrix](https://www.stytrix.com)** — an AI fashion design platform — via the Model Context Protocol (MCP). Ask your assistant to generate fashion concepts, models, fabrics, and full mix-and-match looks, and the results appear **live on your StyTrix canvas**.

- **Endpoint:** `https://www.stytrix.com/api/mcp`
- **Transport:** Streamable HTTP
- **Auth:** OAuth 2.1 (sign in with your StyTrix account — no API key)
- **Docs:** https://www.stytrix.com/mcp

This is a **hosted remote MCP server** — there's nothing to install or run locally. Add the URL to any MCP-capable client and sign in.

## Add to your client

### Claude.ai
Settings → Connectors → **Add custom connector** → paste `https://www.stytrix.com/api/mcp` → Connect and sign in.

### Claude Code
```bash
claude mcp add --transport http stytrix https://www.stytrix.com/api/mcp
```

### Cursor
Add to `.cursor/mcp.json`:
```json
{
  "mcpServers": {
    "stytrix": { "url": "https://www.stytrix.com/api/mcp" }
  }
}
```

### OpenAI Codex
Add to your Codex MCP config:
```toml
[mcp_servers.stytrix]
url = "https://www.stytrix.com/api/mcp"
```

### Gemini CLI
Add to `settings.json` under `mcpServers`:
```json
{
  "mcpServers": {
    "stytrix": { "httpUrl": "https://www.stytrix.com/api/mcp" }
  }
}
```

## Tools

**Read-only (free):** `whoami`, `list_projects`, `get_credits`, `check_video`, `check_style_training`

**Write (deduct credits):** `create_project`, `add_image_to_canvas`, `generate_concept`, `mix_match`, `generate_style`, `generate_model`, `generate_fabric`, `upscale_image`, `remove_background`, `image_to_sketch`, `multi_angle`, `split_layer`, `start_video`, `start_style_training`

Generation tools deduct StyTrix credits only after a successful result. You keep full ownership of everything you create.

## Example prompts

- "List my StyTrix projects and tell me my credit balance."
- "Create a project, then generate a photorealistic concept of an oversized beige wool coat and place it on the canvas."
- "Generate a seamless herringbone wool fabric swatch and add it to my canvas."
- "Take this garment photo and create front, back, and side views."

## Links

- Website: https://www.stytrix.com
- MCP docs: https://www.stytrix.com/mcp
- Privacy: https://www.stytrix.com/privacy
- Support: hello@stytrix.com

## License

This project is licensed under the [MIT License](LICENSE).
