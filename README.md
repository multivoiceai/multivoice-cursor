# Video Dubbing, Subtitles, Transcription & Audiobooks

Dub and translate videos, create SRT/VTT subtitles, transcribe audio and video, and turn manuscripts into multi-voice audiobooks directly from AI agents. Paid jobs always show the exact price before execution.

Cursor Marketplace plugin for the MultiVoice remote MCP at `https://db.multivoice.ai/mcp`.

<a href="https://smithery.ai/servers/info-k2tg/video-dubbing-subtitles-transcription"><img src="https://smithery.ai/badge/info-k2tg/video-dubbing-subtitles-transcription" alt="Smithery" /></a>

## Available MCP Tools

This server provides 20 tools. Dubbing, subtitles, transcription, and audiobooks are paid orders. The agent does not call `dub_video`, `generate_subtitles`, `transcribe_audio`, or `create_audiobook`. Those names are not on the server.

* **Video dubbing** — from any language into German, English, French, Latvian, or Russian. Fully automatic: €0.40 per minute. Native-speaker QA: €5.00 per minute, and then accuracy is 100%.
* **Subtitles** — SRT and VTT captions, €0.015 per minute.
* **Transcription** — speech to text for meetings, lectures, and calls, 120+ languages, €0.015 per minute.
* **Audiobooks** — multi-voice narration of a manuscript in Russian, German, English, French, or Latvian, €100 per book.

Flow: `multivoice.orders.get_create_options`, then `multivoice.orders.prepare_create` (exact price, no charge), then `multivoice.orders.execute_create` only after the human confirms that price.

### Tool names

* `multivoice.orders.get_create_options` — order types and language ids.
* `multivoice.orders.prepare_create` — exact price. Does not start the job and does not charge.
* `multivoice.orders.execute_create` — start the job after the human confirmed the price.
* `multivoice.sources.inspect` — check an allowlisted HTTPS media URL.
* `multivoice.sources.prepare_upload` — register a local file by name, size, and duration. No file path.
* `multivoice.uploads.init` — start a chunked upload after execute.
* `multivoice.uploads.chunk` — one chunk, at most 10 MiB, with its MD5.
* `multivoice.uploads.complete` — finish the upload with the full-file MD5.
* `multivoice.uploads.get_status` — upload status.
* `multivoice.orders.get_status` — status of one owned order.
* `multivoice.orders.get` — one owned order.
* `multivoice.orders.list` — orders for the signed-in account.
* `multivoice.orders.get_actions` — allowed actions for one order.
* `multivoice.orders.get_operation` — state of one order action.
* `multivoice.orders.get_artifacts` — results for one order. The file body is not included.
* `multivoice.orders.prepare_download` — short-lived HTTPS download link. Does not charge.
* `multivoice.services.list` — service catalog.
* `multivoice.account.get` — signed-in account summary.
* `multivoice.billing.get_wallet` — wallet summary.
* `multivoice.billing.prepare_topup` — Stripe Checkout URL. The human pays in the browser.

### Human-in-the-loop and budget security

OAuth 2.1 + PKCE. No static API keys are stored in Cursor or Claude Desktop config. Browser OAuth is the one-time sign-in. Every paid job returns the exact price from `prepare_create` in the MCP client. Funds are debited only after the human confirms that amount and the agent calls `execute_create`. Repeating the same `operation_id` does not charge twice.

## What Cursor can do

- Dub and translate videos
- Create SRT/VTT subtitles and captions
- Transcribe audio and video (speech to text)
- Detect speakers
- Produce multi-voice audiobooks / voice over
- Check job status and retrieve finished artifacts

## Authentication

MultiVoice uses browser-based OAuth 2.1 + PKCE.

No API keys or access tokens should be stored in Cursor configuration.

## One-click install (no GitHub)

[Add MultiVoice to Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=multivoice&config=eyJ1cmwiOiJodHRwczovL2RiLm11bHRpdm9pY2UuYWkvbWNwIn0=)

Or open [multivoice.ai/for-agents](https://multivoice.ai/for-agents) and click **Add MultiVoice to Cursor**.

## Manual MCP config

```json
{
  "mcpServers": {
    "multivoice": {
      "url": "https://db.multivoice.ai/mcp"
    }
  }
}
```

Put this in Cursor `~/.cursor/mcp.json` or project `.cursor/mcp.json`, and in Claude Desktop `claude_desktop_config.json`. The first call opens OAuth in the browser. Do not add an API key or an `npx` command.

## MCP endpoint

https://db.multivoice.ai/mcp

## Example prompts

- Transcribe this video and identify the speakers.
- Create English SRT subtitles for this file.
- Dub this video into German. Show me the price before starting the job.
- Turn this manuscript into a multi-voice audiobook. Give me the quote first.

## Paid operations

MultiVoice shows the price before a paid job is executed.
The user must approve the quoted amount before production starts.

## Documentation

https://multivoice.ai/for-agents

Canonical marketplace copy: [LISTING.md](./LISTING.md)

## Cursor Directory / Marketplace

This repository is a thin connector plugin for [cursor.directory](https://cursor.directory/plugins/new) and directories that require a public repository URL (for example mcp.so).

- Root **`.mcp.json`** — remote MCP URL for cursor.directory Auto detect (no secrets).
- Root **`mcp.json`** — same config, referenced by `.cursor-plugin/plugin.json`.

Submit: https://cursor.directory/plugins/new → paste `https://github.com/multivoiceai/multivoice-cursor` → Scan → Publish.

The MultiVoice backend, OAuth, and billing stay on `db.multivoice.ai` and are not open-sourced here.
