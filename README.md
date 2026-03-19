# Ace Data Cloud MCP Servers

[![VS Code Marketplace](https://img.shields.io/visual-studio-marketplace/v/acedatacloud.acedatacloud-mcp)](https://marketplace.visualstudio.com/items?itemName=acedatacloud.acedatacloud-mcp)
[![Installs](https://img.shields.io/visual-studio-marketplace/i/acedatacloud.acedatacloud-mcp)](https://marketplace.visualstudio.com/items?itemName=acedatacloud.acedatacloud-mcp)

Bring **11 AI-powered MCP servers** into VS Code Copilot Chat — generate music, images, videos, search the web, and more, all directly from your editor.

## Included MCP Servers

| Server | Package | Hosted Endpoint | Description |
|--------|---------|-----------------|-------------|
| **Suno** | `mcp-suno` | `https://suno.mcp.acedata.cloud/mcp` | AI music generation, extend, cover, remix |
| **Midjourney** | `mcp-midjourney` | `https://midjourney.mcp.acedata.cloud/mcp` | AI image generation with Midjourney |
| **Flux** | `mcp-flux-pro` | `https://flux.mcp.acedata.cloud/mcp` | Image generation with Flux models |
| **Seedream** | `mcp-seedream-pro` | `https://seedream.mcp.acedata.cloud/mcp` | Image generation with ByteDance Seedream |
| **NanoBanana** | `mcp-nanobanana-pro` | `https://nanobanana.mcp.acedata.cloud/mcp` | Image generation with Gemini NanoBanana |
| **Luma** | `mcp-luma` | `https://luma.mcp.acedata.cloud/mcp` | Video generation with Luma Dream Machine |
| **Sora** | `mcp-sora` | `https://sora.mcp.acedata.cloud/mcp` | Video generation with OpenAI Sora |
| **Veo** | `mcp-veo` | `https://veo.mcp.acedata.cloud/mcp` | Video generation with Google Veo |
| **Seedance** | `mcp-seedance` | `https://seedance.mcp.acedata.cloud/mcp` | Video generation with ByteDance Seedance |
| **SERP** | `mcp-serp` | `https://serp.mcp.acedata.cloud/mcp` | Google search (web, images, news, videos) |
| **ShortURL** | `mcp-shorturl` | `https://shorturl.mcp.acedata.cloud/mcp` | URL shortening and management |

## Get Your API Token

1. Sign up at [AceDataCloud Platform](https://platform.acedata.cloud)
2. Go to any [API documentation page](https://platform.acedata.cloud/documents) and click **"Acquire"**
3. Copy the token for use below

## Option A: Use Hosted MCP Servers (Recommended)

AceDataCloud provides **cloud-hosted MCP servers** — no local installation, no Python, no dependencies. Just add the endpoint URL and your API token.

Add to your VS Code MCP config (`.vscode/mcp.json`):

```json
{
  "servers": {
    "suno": {
      "type": "streamable-http",
      "url": "https://suno.mcp.acedata.cloud/mcp",
      "headers": { "Authorization": "Bearer YOUR_API_TOKEN" }
    },
    "midjourney": {
      "type": "streamable-http",
      "url": "https://midjourney.mcp.acedata.cloud/mcp",
      "headers": { "Authorization": "Bearer YOUR_API_TOKEN" }
    },
    "flux": {
      "type": "streamable-http",
      "url": "https://flux.mcp.acedata.cloud/mcp",
      "headers": { "Authorization": "Bearer YOUR_API_TOKEN" }
    },
    "luma": {
      "type": "streamable-http",
      "url": "https://luma.mcp.acedata.cloud/mcp",
      "headers": { "Authorization": "Bearer YOUR_API_TOKEN" }
    },
    "sora": {
      "type": "streamable-http",
      "url": "https://sora.mcp.acedata.cloud/mcp",
      "headers": { "Authorization": "Bearer YOUR_API_TOKEN" }
    },
    "veo": {
      "type": "streamable-http",
      "url": "https://veo.mcp.acedata.cloud/mcp",
      "headers": { "Authorization": "Bearer YOUR_API_TOKEN" }
    },
    "seedream": {
      "type": "streamable-http",
      "url": "https://seedream.mcp.acedata.cloud/mcp",
      "headers": { "Authorization": "Bearer YOUR_API_TOKEN" }
    },
    "seedance": {
      "type": "streamable-http",
      "url": "https://seedance.mcp.acedata.cloud/mcp",
      "headers": { "Authorization": "Bearer YOUR_API_TOKEN" }
    },
    "nanobanana": {
      "type": "streamable-http",
      "url": "https://nanobanana.mcp.acedata.cloud/mcp",
      "headers": { "Authorization": "Bearer YOUR_API_TOKEN" }
    },
    "serp": {
      "type": "streamable-http",
      "url": "https://serp.mcp.acedata.cloud/mcp",
      "headers": { "Authorization": "Bearer YOUR_API_TOKEN" }
    },
    "shorturl": {
      "type": "streamable-http",
      "url": "https://shorturl.mcp.acedata.cloud/mcp",
      "headers": { "Authorization": "Bearer YOUR_API_TOKEN" }
    }
  }
}
```

Pick only the servers you need, or add all 11.

## Option B: Use This Extension (Local)

This extension runs MCP servers locally via `uv` + Python. Useful if you prefer local execution.

### Requirements

- **VS Code 1.99+** (MCP server support)
- **Python 3.10+** with [`uv`](https://docs.astral.sh/uv/getting-started/installation/) installed
- **Ace Data Cloud API Token** — get one free at [platform.acedata.cloud](https://platform.acedata.cloud)

### Setup

1. Install this extension
2. Open VS Code Settings (`Cmd+,` or `Ctrl+,`)
3. Search for `acedatacloud.apiToken`
4. Paste your API token from [Ace Data Cloud Platform](https://platform.acedata.cloud)
5. Start using MCP tools in **Copilot Chat** — e.g., "Generate a jazz song about coding"

## Available Tools

<details>
<summary><strong>Suno (21 tools)</strong> — AI Music Generation</summary>

- `suno_generate_music` — Generate music from a text description
- `suno_generate_custom_music` — Generate with custom lyrics and style
- `suno_extend_music` — Extend an existing song
- `suno_cover_music` — Create a cover version
- `suno_concat_music` — Concatenate music clips
- `suno_generate_with_persona` — Generate with a specific voice/persona
- `suno_remaster_music` — Remaster audio quality
- `suno_stems_music` — Separate stems (vocals, instruments)
- `suno_replace_section` — Replace a section of a song
- `suno_upload_extend` — Upload audio and extend
- `suno_upload_cover` — Upload audio and create cover
- `suno_get_mp4` — Get MP4 video of the song
- `suno_get_timing` — Get timing/lyric sync data
- `suno_extract_vocals` — Extract vocals from a song
- `suno_get_wav` — Get WAV format
- `suno_get_midi` — Get MIDI file
- `suno_optimize_style` — Optimize style prompt
- `suno_mashup_lyrics` — Mashup lyrics from multiple songs
- `suno_upload_audio` — Upload custom audio
- `suno_generate_lyrics` — Generate lyrics
- `suno_create_persona` — Create a voice persona

</details>

<details>
<summary><strong>Midjourney (15 tools)</strong> — AI Image Generation</summary>

- `midjourney_imagine` — Generate images from text prompt
- `midjourney_transform` — Transform/upscale/vary images
- `midjourney_blend` — Blend multiple images
- `midjourney_with_reference` — Generate with reference image
- `midjourney_edit` — Edit regions of an image
- `midjourney_describe` — Describe an image
- `midjourney_translate` — Translate prompt to English
- `midjourney_get_seed` — Get the seed of a generation
- `midjourney_generate_video` — Generate video from image
- `midjourney_extend_video` — Extend video duration
- `midjourney_get_task` — Get task status
- `midjourney_get_tasks_batch` — Get multiple task statuses
- `midjourney_list_actions` — List available actions
- `midjourney_get_prompt_guide` — Get prompt writing guide
- `midjourney_list_transform_actions` — List transform actions

</details>

<details>
<summary><strong>Flux (6 tools)</strong> — AI Image Generation</summary>

- `flux_generate_image` — Generate images with Flux models
- `flux_edit_image` — Edit images
- `flux_get_task` — Get task status
- `flux_get_tasks_batch` — Get batch task statuses
- `flux_list_models` — List available models
- `flux_list_actions` — List available actions

</details>

<details>
<summary><strong>Seedream (6 tools)</strong> — ByteDance Image Generation</summary>

- `seedream_generate_image` — Generate images
- `seedream_edit_image` — Edit images
- `seedream_get_task` — Get task status
- `seedream_get_tasks_batch` — Get batch task statuses
- `seedream_list_models` — List models
- `seedream_list_sizes` — List supported sizes

</details>

<details>
<summary><strong>NanoBanana (4 tools)</strong> — Gemini Image Generation</summary>

- `nanobanana_generate_image` — Generate images
- `nanobanana_edit_image` — Edit images
- `nanobanana_get_task` — Get task status
- `nanobanana_get_tasks_batch` — Get batch task statuses

</details>

<details>
<summary><strong>Luma (8 tools)</strong> — AI Video Generation</summary>

- `luma_generate_video` — Generate video from text
- `luma_generate_video_from_image` — Generate video from image
- `luma_extend_video` — Extend existing video
- `luma_extend_video_from_url` — Extend video from URL
- `luma_get_task` — Get task status
- `luma_get_tasks_batch` — Get batch task statuses
- `luma_list_aspect_ratios` — List aspect ratios
- `luma_list_actions` — List available actions

</details>

<details>
<summary><strong>Sora (10 tools)</strong> — OpenAI Video Generation</summary>

- `sora_generate_video` — Generate video from text
- `sora_generate_video_from_image` — Generate from image
- `sora_generate_video_with_character` — Generate with character reference
- `sora_generate_video_async` — Async generation
- `sora_generate_video_v2` — V2 generation
- `sora_generate_video_v2_async` — V2 async generation
- `sora_get_task` — Get task status
- `sora_get_tasks_batch` — Get batch task statuses
- `sora_list_models` — List models
- `sora_list_actions` — List actions

</details>

<details>
<summary><strong>Veo (8 tools)</strong> — Google Video Generation</summary>

- `veo_text_to_video` — Generate video from text
- `veo_image_to_video` — Generate video from image
- `veo_get_1080p` — Get 1080p version
- `veo_get_task` — Get task status
- `veo_get_tasks_batch` — Get batch task statuses
- `veo_list_models` — List models
- `veo_list_actions` — List actions
- `veo_get_prompt_guide` — Get prompt guide

</details>

<details>
<summary><strong>Seedance (7 tools)</strong> — ByteDance Video Generation</summary>

- `seedance_generate_video` — Generate video from text
- `seedance_generate_video_from_image` — Generate from image
- `seedance_get_task` — Get task status
- `seedance_get_tasks_batch` — Get batch task statuses
- `seedance_list_models` — List models
- `seedance_list_resolutions` — List supported resolutions
- `seedance_list_actions` — List actions

</details>

<details>
<summary><strong>SERP (11 tools)</strong> — Google Search</summary>

- `serp_google_search` — Web search
- `serp_google_images` — Image search
- `serp_google_news` — News search
- `serp_google_videos` — Video search
- `serp_google_places` — Places search
- `serp_google_maps` — Maps search
- `serp_list_search_types` — List search types
- `serp_list_countries` — List supported countries
- `serp_list_languages` — List languages
- `serp_list_time_ranges` — List time ranges
- `serp_get_usage_guide` — Usage guide

</details>

<details>
<summary><strong>ShortURL (4 tools)</strong> — URL Shortening</summary>

- `shorturl_create` — Create a short URL
- `shorturl_batch_create` — Batch create short URLs
- `shorturl_get_usage_guide` — Usage guide
- `shorturl_get_api_info` — API info

</details>

## Example Usage in Copilot Chat

```
@workspace Generate a rock song about open source software

@workspace Create a Midjourney image of a futuristic city at sunset

@workspace Generate a 5-second video of ocean waves with Luma

@workspace Search Google for "latest VS Code release notes"

@workspace Shorten this URL: https://platform.acedata.cloud/services
```

## Links

- [Ace Data Cloud Platform](https://platform.acedata.cloud) — Get your API token
- [API Documentation](https://docs.acedata.cloud) — Full API reference
- [GitHub](https://github.com/AceDataCloud/VSCodeMCP) — Source code & issues

## License

MIT
