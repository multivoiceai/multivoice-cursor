# Claude Directory — MCP connector submission pack

Portal: https://claude.ai/directory/manage  
Docs: https://claude.com/docs/directory/publish · https://claude.com/docs/connectors/building/submission

Submit kind: **MCP connector** (not four services / not plugin-only).

## Listing fields

| Field | Value |
|---|---|
| Name / Title | Video Dubbing, Subtitles, Transcription & Audiobooks |
| Description | Dub and translate videos, create SRT/VTT subtitles, transcribe audio and video, and turn manuscripts into multi-voice audiobooks directly from AI agents. Paid jobs always show the exact price before execution. |
| MCP URL | `https://db.multivoice.ai/mcp` |
| Documentation | https://multivoice.ai/for-agents |
| Privacy | https://multivoice.ai/privacy |
| Terms | https://multivoice.ai/terms |
| Support | https://multivoice.ai/contacts |
| Homepage | https://multivoice.ai |

## Preflight (before Submit)

1. MCP Inspector → Streamable HTTP → `https://db.multivoice.ai/mcp` → OAuth → list tools.
2. Claude → custom connector with the same URL → exercise quote-first flow (`get_create_options` → `prepare_create` → stop before spend).
3. Confirm tools are annotated (already on server).

## Reviewer credentials

Provide a dedicated MultiVoice test account with wallet balance. Never paste production secrets or personal OAuth refresh tokens into the form.

## Owner action

Sign in with a paid Claude plan → Submit new → MCP connector → paste fields above → Test & launch confirmations → Submit.
