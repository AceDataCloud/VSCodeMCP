# Ace Data Cloud MCP Toolbox

One VS Code extension for AI chat, images, video, music, search, web extraction,
and account management. Choose from **26 hosted MCP services** and use them in
Copilot Chat without installing Python or running local servers.

## Get started

1. Install **AceDataCloud MCP** from the [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=acedatacloud.acedatacloud-mcp).
2. Open the Command Palette and run **Ace Data Cloud: Choose MCP Services**.
3. Run **Ace Data Cloud: Set Shared API Key**, using an API key with access to your selected services from the
   [Ace Data Cloud console](https://platform.acedata.cloud/console/credentials).
4. Open Copilot Chat in Agent mode, enable the tools you need, and ask a question.

VS Code **1.101 or newer** and a chat client with MCP tool support are required.
VS Code asks you to trust an MCP server before starting it. API requests use your
Ace Data Cloud account and are billed according to the selected service.

The default selection includes Suno, Midjourney, Flux, Seedream, NanoBanana,
Luma, Veo, Seedance, Google Search, and Short URL. Add or remove services at any
time with the picker. The extension exposes server definitions; VS Code controls
when each selected server starts.

## Services

| Use | Services |
| --- | --- |
| Chat and AI APIs | OpenAI, AI Chat, GLM |
| Images and faces | Midjourney, Flux, Seedream, NanoBanana, Qwen Image, Face Transform |
| Video | Kling, Veo, Luma, Seedance, Wan, Hailuo, MiniMax, Grok Imagine, HappyHorse |
| Music and audio | Suno, Producer, Fish Audio |
| Production | Maestro |
| Search and utilities | Google Search, Web Extractor, Short URL |
| Account | Ace Data Cloud Account |

Account management is optional and requires its own platform token from
[Platform tokens](https://platform.acedata.cloud/console/platform-tokens).
Run **Ace Data Cloud: Set Account Platform Token** to save it. API keys are never
sent to the account-management server, and platform tokens are never sent to
API-service servers.

## Credentials and configuration

Credentials are stored in VS Code **SecretStorage**, not in `settings.json`.
Use **Set Service API Key** when one service needs a different key. Saved service
keys take precedence over the shared key. Environment variables
`ACEDATACLOUD_API_TOKEN` and `ACEDATACLOUD_PLATFORM_TOKEN` are used only when the
corresponding saved credential is absent.

**Clear Saved Credentials** removes keys saved by this extension. It does not
change environment variables. To stop exposing a service, deselect it with
**Choose MCP Services**. To stop all services, select none.

You can also set `acedatacloud.bundle.services` in VS Code settings:

```json
{
  "acedatacloud.bundle.services": ["suno", "kling", "qwen-image", "serp"]
}
```

If upgrading from the March 2026 bundle, save your key using the command above
and remove the old `acedatacloud.apiToken` plaintext setting. It is no longer read.
The retired Sora service is no longer included. Individual Ace Data Cloud service
extensions remain available; disable duplicate entries if you also use this bundle.

## Examples

- “Use Suno to create a short instrumental track for a product demo.”
- “Use Qwen Image to make a watercolor illustration of a mountain village.”
- “Use Google Search to find the latest developments in battery recycling.”

For generation tasks, continue tracking the task until it completes before
using the output.

## Development

```bash
npm ci
npm test
npm run check
npm run package
```

`servers.json` is the bundle's curated list of hosted services. Add a service only
after checking its public health endpoint and MCP authentication response. Update
its setting enum and this README together. The publishing workflow runs tests,
packages a VSIX, publishes it, and reads back the public Marketplace version.

[API documentation](https://docs.acedata.cloud) ·
[MCP server source](https://github.com/AceDataCloud/MCPs) ·
[Issues](https://github.com/AceDataCloud/VSCodeMCP/issues)

MIT licensed.
