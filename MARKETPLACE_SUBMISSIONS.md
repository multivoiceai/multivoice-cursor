# Marketplace submissions — owner checklist

Agent-prepared materials live in this repo. Official Registry stays frozen:
`ai.multivoice/video-dubbing-subtitles-transcription-audiobooks` → `https://db.multivoice.ai/mcp`.

Paste title / description / tags from [LISTING.md](./LISTING.md).

## 1. Glama (claim + health)

1. Open https://glama.ai/mcp/connectors/ai.multivoice/video-dubbing-subtitles-transcription-audiobooks
2. Sign in → **Claim ownership** (domain `multivoice.ai`).
3. Copy the claim token (`glama_claim_...`).
4. Set site env `GLAMA_CLAIM_TOKEN=<token>` on the Next deploy for `web-multivoice-next`, redeploy.
5. Confirm https://multivoice.ai/.well-known/glama.json returns `{"$schema":"...","claim":"glama_claim_..."}` (HTTPS, no cross-domain redirect).
6. In Glama UI press **Check**.
7. After claim: set categories **Multimedia Processing, Audio Processing, Speech Processing, Language Translation, Text-to-Speech**; enable Glama listing details as source of truth if editing title/description.
8. Admin → **Test Profile**: OAuth with a dedicated MultiVoice test account (not a personal session). Re-run health until tools discover.

Route already implemented: `web-multivoice-next/src/app/.well-known/glama.json/route.ts`.

## 2. Smithery

```bash
npx @smithery/cli auth login
npx @smithery/cli mcp publish "https://db.multivoice.ai/mcp" -n @multivoice/video-dubbing-subtitles-transcription-audiobooks
```

Or UI: https://smithery.ai/new

- Transport: Streamable HTTP
- OAuth when scan asks
- Title / description / tags from LISTING.md
- Do **not** publish a stdio/MCPB duplicate

## 3. Claude Directory

1. https://claude.ai/directory/manage (docs: https://claude.com/docs/directory/publish)
2. Submit → **MCP connector** (one connector, not four services)
3. Title / description from LISTING.md; docs https://multivoice.ai/for-agents
4. Privacy https://multivoice.ai/privacy · Terms https://multivoice.ai/terms
5. Preflight: MCP Inspector + Claude custom connector against `https://db.multivoice.ai/mcp`
6. If reviewers ask for credentials: dedicated MultiVoice test account with balance; never paste prod secrets

## 4. OpenAI Plugin Directory

Package ready:

- Folder: `openai-plugin/`
- ZIP: `openai-plugin.zip`
- Remote MCP: `https://db.multivoice.ai/mcp` (streamable-http)

Steps (owner OpenAI developer / org):

1. https://developers.openai.com/plugins/deploy/submission
2. Upload ZIP; connect remote MCP; complete domain verification if asked
3. Submit for review with LISTING.md copy and review test cases already in `openai-plugin/plugin.json`

## 5. mcp.film

Submit one listing against the live Registry / capabilities (video dubbing, subtitles).
Endpoint `https://db.multivoice.ai/mcp`. Categories: filmmaking / localization.
Use LISTING.md title and description.

## 6. Cursor Marketplace

Plugin version **1.1.0** — task-first `displayName`, description, keywords in `.cursor-plugin/plugin.json`.
Push this repo, then refresh / resubmit the Cursor Marketplace listing if the portal still shows the old blurb.
Do **not** open the MultiVoice backend.

## 7. mcp.so

Form requires a repository URL → `https://github.com/multivoiceai/multivoice-cursor`
(plugin-only; do not link SubtitleServer). Featured listing ($39) is optional.
