---
name: get-started
description: Connect MultiVoice MCP and run quote-first dubbing, subtitles, transcription, or audiobook jobs.
---

# MultiVoice — get started

Use the remote MCP at `https://db.multivoice.ai/mcp` (already declared in this plugin).

## Rules

1. Always call `multivoice_orders_get_create_options` before preparing an order.
2. For URL media use `multivoice_sources_inspect`; for local files use `multivoice_sources_prepare_upload` then the upload tools after execute.
3. Show `commitment_amount` from `multivoice_orders_prepare_create` and wait for explicit user confirmation of that amount before `multivoice_orders_execute_create`.
4. Never ask for passwords or paste OAuth tokens.
5. Reuse the same `operation_id` on retry. Poll status at most once every 10 seconds.

## Example flows

- **Subtitles / transcription / dubbing:** inspect or prepare upload → prepare_create → confirm price → execute_create → (uploads if needed) → get_status / get_artifacts → prepare_download.
- **Audiobook (type 1):** prepare_create with nested book payload → confirm price → execute_create.

Docs: https://multivoice.ai/for-agents
