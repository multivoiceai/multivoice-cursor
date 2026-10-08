# Video Dubbing, Subtitles, Transcription & Audiobooks

Dub and translate videos, create SRT/VTT subtitles, transcribe audio and video, and turn manuscripts into multi-voice audiobooks directly from AI agents. Paid jobs always show the exact price before execution.

Cursor Marketplace plugin for the MultiVoice remote MCP at `https://db.multivoice.ai/mcp`.

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

Put this in `~/.cursor/mcp.json` or project `.cursor/mcp.json`.

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

## Marketplace

This repository is a thin connector plugin for the Cursor Marketplace and directories that require a public repository URL (for example mcp.so).
The MultiVoice backend, OAuth, and billing stay on `db.multivoice.ai` and are not open-sourced here.
