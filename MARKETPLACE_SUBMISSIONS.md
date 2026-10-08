# Marketplace submissions ù owner checklist

Agent-prepared materials live in this repo. Official Registry stays frozen:
`ai.multivoice/video-dubbing-subtitles-transcription-audiobooks` ? `https://db.multivoice.ai/mcp`.

Paste title / description / tags from [LISTING.md](./LISTING.md).

## 1. Glama (claim + health)

Connector: https://glama.ai/mcp/connectors/ai.multivoice/video-dubbing-subtitles-transcription-audiobooks

### Claim (site already serves token)

1. Sign in ? **Claim ownership** (domain `multivoice.ai`) if not already claimed.
2. Public proof: https://multivoice.ai/.well-known/glama.json must return
   `{"$schema":"https://glama.ai/mcp/schemas/connector.json","claim":"glama_claim_..."}` (HTTPS, no cross-domain redirect).
3. In Glama UI press **Check** until verified / official.

Route: `web-multivoice-next/src/app/.well-known/glama.json/route.ts` ù env `GLAMA_CLAIM_TOKEN`.

### Paste-ready listing fields

| Field | Value |
|---|---|
| Title | Video Dubbing, Subtitles, Transcription & Audiobooks |
| Description | Dub and translate videos, create SRT/VTT subtitles, transcribe audio and video, and turn manuscripts into multi-voice audiobooks directly from AI agents. Production localization over remote MCP with OAuth and wallet ù paid jobs always show the exact price before execution. Not a local video editor, upscaler, or 3D tool. |
| Categories | Multimedia Processing; Audio Processing; **Speech Processing**; **Language Translation**; **Text-to-Speech** |
| Tags | video dubbing, video translation, subtitles, captions, SRT, VTT, transcription, speech to text, audiobook creation, voice over, localization |
| Example prompts | (four lines from LISTING.md ù always include ùshow price / quoteù on paid examples) |
| Docs | https://multivoice.ai/for-agents |

### OAuth / Test Profile (after API ? 2.4.101)

1. Admin ? **Test Profile**: OAuth with a **dedicated** MultiVoice test account (not a personal session).
2. MCP Inspector Online: Connect ? consent (spend limits if shown) ? Allow ? tools/list must succeed.
3. Re-run connector **health** until green. Red Error after Connect loses users to other Multimedia listings.

### Optional

Glama Boost for Speech / Translation categories (product decision).

## 2. Smithery

```bash
npx @smithery/cli auth login
npx @smithery/cli mcp publish "https://db.multivoice.ai/mcp" -n "@info-k2tg/video-dubbing-subtitles-transcription-audiobooks"
# after OAuth authorize (test MultiVoice account):
npx @smithery/cli mcp publish --resume
```

Listing: https://smithery.ai/servers/@info-k2tg/video-dubbing-subtitles-transcription-audiobooks  
Releases / OAuth: https://smithery.ai/servers/@info-k2tg/video-dubbing-subtitles-transcription-audiobooks/releases/

### Paste after scan

- Transport: Streamable HTTP  
- Title / description / tags: LISTING.md  
- Keywords: dubbing, subtitles, transcription, audiobook, localization  
- Docs URL: https://multivoice.ai/for-agents  
- Do **not** publish a stdio/MCPB duplicate  
- Namespace `@multivoice` was unavailable (3-namespace limit); keep `@info-k2tg/...`

Owner: finish OAuth on the releases page with the test account until release is green.

## 3. Claude Directory

1. https://claude.ai/directory/manage (docs: https://claude.com/docs/directory/publish)
2. Submit ? **MCP connector** (one connector, not four services)
3. Title / description from LISTING.md; docs https://multivoice.ai/for-agents
4. Privacy https://multivoice.ai/privacy ù Terms https://multivoice.ai/terms
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

Submitted: https://github.com/c47-inc/mcp-film/issues/90  
Category: `transcription` ù install URL `https://db.multivoice.ai/mcp` ù docs link `https://multivoice.ai/for-agents`.

## 6. Cursor Directory (primary) / Marketplace (deferred)

Cursor Marketplace Team (2026-10): new marketplace submissions are limited ù submit to **cursor.directory** first for visibility and adoption; they evaluate directory adoption before marketplace adds.

Plugin version **1.1.0** ù task-first `displayName`, description, keywords in `.cursor-plugin/plugin.json`.
Repo-root **`.mcp.json`** (same remote URL as `mcp.json`) is required for cursor.directory Auto scan.

### Submit to cursor.directory

1. Ensure `main`/`master` has `.mcp.json` pushed to https://github.com/multivoiceai/multivoice-cursor
2. Open https://cursor.directory/plugins/new
3. Sign in with GitHub (account with access to `multivoiceai/multivoice-cursor`)
4. Auto tab: paste `https://github.com/multivoiceai/multivoice-cursor` ? **Scan repo**
5. Confirm MCP component detected from `.mcp.json`
6. **Publish Plugin** ù wait for automated safety scan (`safe`)
7. Manual tab (if needed): title / description / keywords from [LISTING.md](./LISTING.md); homepage https://multivoice.ai/for-agents

Do **not** open a second registry name or stdio duplicate. Do **not** open the MultiVoice backend.

Optional later: reply to Marketplace email that the plugin is on cursor.directory; re-apply when they evaluate adoption.

## 7. mcp.so

Form requires a repository URL ? `https://github.com/multivoiceai/multivoice-cursor`
(plugin-only; do not link SubtitleServer). Featured listing ($39) is optional.

## Metrics (periodic)

| Metric | Where |
|---|---|
| Connect / health | Glama connector admin + Inspector |
| Smithery release | releases page status |
| Site ? docs | UTM on `/for-agents` links: `utm_source=site&utm_medium=cta&utm_campaign=mcp-for-agents` (product landings use `mcp-product`) |
| Search | Google Search Console queries: multivoice mcp, dubbing mcp, subtitles mcp |

## Status snapshot (agent)

| Channel | Status |
|---|---|
| Official Registry | Frozen ù do not republish |
| Glama | Claim JSON live on multivoice.ai; owner: categories + Test Profile OAuth green (API ? 2.4.101) |
| Smithery | Listing `@info-k2tg/...`; owner: finish OAuth on releases + paste LISTING.md |
| mcp.film | https://github.com/c47-inc/mcp-film/issues/90 |
| Claude Directory | Pack ready ù sign in at https://claude.ai/directory/manage |
| OpenAI Plugin Directory | `openai-plugin.zip` ready ù upload in OpenAI portal |
| Cursor Marketplace | Deferred by Cursor team ó use cursor.directory first |
| cursor.directory | `.mcp.json` in repo; submit at https://cursor.directory/plugins/new |
| mcp.so | Form filled with plugin repo; free ticket needs Sign In |
| Site discovery | for-agents ùwhen to useù + llms routing + UTM CTAs (web-multivoice-next) |
