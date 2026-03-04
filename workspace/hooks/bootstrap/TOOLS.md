## AlphaClaw Harness

AlphaClaw is the setup and management harness that runs alongside OpenClaw. It provides a web-based Setup UI and manages environment variables, channel connections, Google Workspace integration, and the gateway lifecycle.

AlphaClaw UI: `https://openclaw-railway-template-production-7207.up.railway.app`

### Tabs

| Tab       | URL                          | What it manages                                                                                                                                                                            |
| --------- | ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| General   | `https://openclaw-railway-template-production-7207.up.railway.app#general`   | Gateway status & restart, channel health (Telegram/Discord), pending pairings, feature health (Embeddings/Audio), Google Workspace connection, repo auto-sync schedule, OpenClaw dashboard |
| Watchdog  | `https://openclaw-railway-template-production-7207.up.railway.app#watchdog`  | Gateway watchdog lifecycle, crash-loop visibility, restart diagnostics, and auto-repair feature                                                                                            |
| Providers | `https://openclaw-railway-template-production-7207.up.railway.app#providers` | AI provider credentials (Anthropic, OpenAI, Gemini, Mistral, Voyage, Groq, Deepgram), feature capabilities, Codex OAuth                                                                    |
| Envars    | `https://openclaw-railway-template-production-7207.up.railway.app#envars`    | View/edit/add environment variables (saved to `/data/.env`), gateway restart to apply changes                                                                                              |
| Webhooks  | `https://openclaw-railway-template-production-7207.up.railway.app#webhooks`  | Webhook endpoint visibility, create flow, request history, and gateway delivery debugging                                                                                                  |
| Browse    | `https://openclaw-railway-template-production-7207.up.railway.app#browse`    | File browser and editor rooted at `.openclaw`, markdown preview/edit flow, and git-aware save workflow                                                                                     |

### Environment variables

Changes to env vars are made through the **Envars** tab (`https://openclaw-railway-template-production-7207.up.railway.app#envars`). After saving, a gateway restart may be required to pick up the changes — the UI prompts for this automatically. Do not edit `/data/.env` directly; use the Setup UI so changes are validated and the gateway restart is handled.

### Google Workspace

Google Workspace is connected via the **General** tab (`https://openclaw-railway-template-production-7207.up.railway.app#general`). The user provides OAuth client credentials from Google Cloud Console, then authorizes access to the services they need (Gmail, Calendar, Drive, Sheets, Docs, Tasks, Contacts, Meet).

## Git Discipline

**Commit and push after every set of changes.** Your entire .openclaw directory (config, cron, workspace) is version controlled. This is how your work survives container restarts.

Never force push. Always pull before pushing if there might be remote changes.
After pushing, include a link to the commit using the abbreviated hash: [abc1234](https://github.com/owner/repo/commit/abc1234) format. No backticks.

## Telegram Formatting

- **Links:** Use markdown syntax `[text](URL)` — HTML `<a href>` does NOT render

## Webhooks

You can create webhooks yourself or the user can create them through the AlphaClaw UI.

Webhook transform files must follow this convention:

- Path: hooks/transforms/{hook-name}/{hook-name}-transform.mjs
- Signature: export default async function transform(payload, context)
- Webhook data is at payload.payload (nested)
- Never create transform files outside of hooks/transforms/
- When modifying a transform, read the existing file first

## Topic Registry

When sending messages to group topics, use these thread IDs:

| Group | Topic | Thread ID |
| ----- | ----- | --------- |
| OpenClaw (-1003805134407) | Daily Briefing | 5 |

### Sync Rules

When Telegram workspace is enabled, keep topic mappings in sync with real Telegram activity:

- If a message arrives in an unregistered Telegram topic, ask the user to name it for addition to the registry.
- When adding a topic (new or missing) run `alphaclaw telegram topic add --thread <threadId> --name "<topicName>"` immediately, no confirmation needed.
- Never edit `hooks/bootstrap/TOOLS.md` directly for topic changes


## Available Google Accounts

Configured in AlphaClaw (use `--client <client> --account <email>` for gog commands):

- lhaile7@gmail.com (type: personal; client: personal; status: authenticated; services: gmail:read, sheets:read, calendar:write, drive:read, calendar:read, docs:read, gmail:write)
- lauren.haile@superhuman.com (type: company; client: default; status: awaiting sign-in; services: gmail:read, calendar:read, calendar:write, drive:read, sheets:read, docs:read)
