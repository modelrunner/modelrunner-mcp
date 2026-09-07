# ModelRunner MCP Server

Official [Model Context Protocol](https://modelcontextprotocol.io) (MCP) server for [ModelRunner](https://modelrunner.ai) — run 100+ AI models across **image, video, audio, and 3D generation** from Claude, Cursor, and any MCP client.

- **Endpoint:** `https://mcp.modelrunner.run/mcp` (remote server, Streamable HTTP)
- **Auth:** OAuth 2.1 — your browser authorizes once; **no API key is pasted into config**
- **Registry name:** `ai.modelrunner/mcp`
- **Setup guide & full tool reference:** [modelrunner.ai/mcp](https://modelrunner.ai/mcp)

Unlike single-vendor MCP servers, one connection exposes the **entire ModelRunner catalog** — models from multiple AI providers behind one endpoint and one pay-per-use billing account. Your assistant can search the catalog, inspect a model's input schema, run inference, and get results back as hosted URLs directly in the conversation.

> **Maintaining an open-source project?** ModelRunner gives active open-source
> projects free monthly API credits — apply at
> [modelrunner.ai/oss-program](https://modelrunner.ai/oss-program).

## Quick start

### Claude Code

```bash
claude mcp add --transport http modelrunner https://mcp.modelrunner.run/mcp
```

### Cursor / VS Code (native remote URL)

```json
{
  "mcpServers": {
    "modelrunner": { "url": "https://mcp.modelrunner.run/mcp" }
  }
}
```

### Claude Desktop or any stdio-only client (via [mcp-remote](https://www.npmjs.com/package/mcp-remote))

```json
{
  "mcpServers": {
    "modelrunner": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://mcp.modelrunner.run/mcp"]
    }
  }
}
```

On first use your AI assistant opens a browser window to sign in to ModelRunner — that's the whole setup.

## Tools

| Group | Tools |
| ----- | ----- |
| Discover & inspect | `search`, `list_models`, `list_wrappers`, `recommended_models`, `recommended_wrappers`, `get_model`, `get_wrapper`, `get_model_raw_schema`, `get_wrapper_raw_schema`, `get_wrapper_prompt_template`, `get_wrapper_field_mappings` |
| Run & fetch | `run_model`, `wait_for_request`, `get_request`, `list_my_requests` |
| Upload files | `create_upload_url`, `upload_file` |
| Author wrappers | `wrapper_authoring_guide`, `create_wrapper`, `patch_wrapper`, `preview_wrapper`, `list_my_wrappers`, `delete_wrapper` |

"Wrappers" are reusable, simplified interfaces you can build over base models — a few friendly inputs, a prompt template, and baked-in settings — and they run through the same `run_model`-style tools.

## Models & capabilities

The catalog covers **text-to-image, image-to-image, text-to-video, image-to-video, video-to-video, music generation, speech-to-text, and image-to-3D**, including models like Kling, HiDream, Hunyuan Image, Stable Audio, and Rodin. Browse by capability:

- [Text-to-Image API](https://modelrunner.ai/text-to-image-api) · [Image-to-Image API](https://modelrunner.ai/image-to-image-api)
- [Text-to-Video API](https://modelrunner.ai/text-to-video-api) · [Image-to-Video API](https://modelrunner.ai/image-to-video-api) · [Video-to-Video API](https://modelrunner.ai/video-to-video-api)
- [Music Generation API](https://modelrunner.ai/music-generation-api) · [Speech-to-Text API](https://modelrunner.ai/speech-to-text-api)
- [Image-to-3D API](https://modelrunner.ai/image-to-3d-api)

Full catalog: [modelrunner.ai/models](https://modelrunner.ai/models)

## Pricing

Free to connect. Model runs are pay-per-use from prepaid credits — no subscription. Every model's exact price (per image, per second of video, per megapixel, …) is shown on its model page and on the [pricing page](https://modelrunner.ai/pricing).

## About this repository

This repository documents the hosted ModelRunner MCP server. The server itself is first-party, run by ModelRunner as a remote MCP endpoint — there is nothing to install or self-host; the configs above are the entire integration.

- Landing page: [modelrunner.ai/mcp](https://modelrunner.ai/mcp)
- Docs: [modelrunner.ai/docs](https://modelrunner.ai/docs)
- Model catalog: [modelrunner.ai/models](https://modelrunner.ai/models)

## License

[MIT](./LICENSE)
