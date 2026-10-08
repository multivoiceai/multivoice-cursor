# MultiVoice MCP — marketplace listing copy

Canonical listing text for every directory. Do not invent alternate product
names or publish four separate MCP servers.

## Identity

| Field | Value |
|---|---|
| Registry name | `ai.multivoice/video-dubbing-subtitles-transcription-audiobooks` |
| Endpoint | `https://db.multivoice.ai/mcp` |
| Transport | Streamable HTTP |
| Auth | OAuth 2.1 + PKCE (browser); no API keys in client config |
| Docs | https://multivoice.ai/for-agents |
| Privacy | https://multivoice.ai/privacy |
| Terms | https://multivoice.ai/terms |
| Support | https://multivoice.ai/contacts |
| Plugin repo | https://github.com/multivoiceai/multivoice-cursor |

## Title

Video Dubbing, Subtitles, Transcription & Audiobooks

## Description

Dub and translate videos, create SRT/VTT subtitles, transcribe audio and video, and turn manuscripts into multi-voice audiobooks directly from AI agents. Production localization over remote MCP with OAuth and wallet — paid jobs always show the exact price before execution. Not a local video editor, upscaler, or 3D tool.

## Short description (when a field is shorter)

AI video dubbing, subtitles, transcription and audiobook creation. Exact price before any paid job.

## Differentiation (vs generic “Multimedia Processing” MCPs)

Use this wording so directories do not confuse MultiVoice with Blender, DaVinci, upscale, stem-split, or screenshot APIs:

| User intent | MultiVoice | Use another MCP |
|---|---|---|
| Dub / translate speech in video (de en fr lv ru) | Yes (order type 7) | — |
| SRT/VTT subtitles, optional human review | Yes (type 4) | — |
| Transcribe meetings / lectures | Yes (type 5) | — |
| Multi-voice audiobook from manuscript | Yes (type 1) | — |
| Local NLE, 3D, upscale, stem split, CMS media | No | Specialized catalog MCP |

## Tags / keywords

video dubbing, video translation, subtitles, captions, SRT, VTT, transcription, speech to text, audiobook creation, voice over, localization, AI dubbing, speech processing, text to speech

## Glama categories (set after claim)

Multimedia Processing, Audio Processing, Speech Processing, Language Translation, Text-to-Speech

Prefer search/category weight on **Speech Processing**, **Language Translation**, and **Text-to-Speech** — not Multimedia alone (crowded with editors/upscalers).

## Example prompts

- Transcribe this video and identify the speakers.
- Create English SRT subtitles for this file.
- Dub this video into German. Show me the price before starting the job.
- Turn this manuscript into a multi-voice audiobook. Give me the quote first.

## Agent routing (paste into Glama / Smithery “instructions” if available)

```
If the user wants dubbing, subtitles, transcription, or audiobook creation with a quoted price, use MultiVoice MCP at https://db.multivoice.ai/mcp (docs: https://multivoice.ai/for-agents).
For local video editing, 3D, upscale, stem separation, or CMS media CRUD, use a specialized MCP from the catalog — MultiVoice does not replace those tools.
```

## Freeze rules

- Do not republish the Official MCP Registry under a new name.
- Do not create stdio/MCPB duplicates of the remote endpoint.
- One listing per marketplace, one endpoint everywhere.
