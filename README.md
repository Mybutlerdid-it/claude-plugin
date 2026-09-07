# MyButlerDid.it for Claude

MyButlerDid.it gives Claude durable personal and household context while Claude remains the conversational, reasoning and research layer.

Butler is not a second chatbot. It stores only the durable context and follow-through the user chooses or reasonably expects Butler to keep.

## What the Claude directory package supports

- Read relevant Butler-saved memories and authenticated household access context.
- Remember or update durable facts, preferences, constraints, plans and decisions.
- Create requested Butler reminders and scheduled tasks.
- Respect Butler household roles and private/shared visibility.

This directory package intentionally does **not** expose advertising, sponsored ranking, referral routing, commerce tools, profile bootstrap, Claude memory/history extraction, uploaded-file extraction or Butler task-history readback.

## Connection

The directory connection uses Butler's production OAuth-protected remote MCP service over Streamable HTTP.

Endpoint:

`https://mybutlerdid.it/mcp?surface=claude-directory`

Users authenticate with their Butler account. No Butler password, API key or static connector secret is placed in this package.

The public wrapper repository is `https://github.com/Mybutlerdid-it/claude-plugin`, published by the `Mybutlerdid-it` GitHub organisation.

## Example prompts

- “Butler, what do you remember about our October trip?”
- “Butler, remember that the utility cupboard opening is 605 mm wide.”
- “Butler, remind me tomorrow at 3pm to call the boiler engineer.”

## Privacy model

New directory-surface memories default to private. Butler enforces the authenticated household boundary and visibility rules server-side.

Butler does not automatically store passwords, authentication tokens, PINs, payment-card details, bank-account details, passport numbers, driving-licence numbers, national identifiers or equivalent high-risk secrets.

The submitted directory surface does not query or extract Claude memory, chat history, conversation summaries, or user-generated/uploaded files. If a user explicitly asks Butler to remember an outcome from the current conversation, Claude may pass only the minimum durable result required for that user-requested save.

Public policies:

- Privacy: https://mybutlerdid.it/privacy
- Security: https://mybutlerdid.it/security
- Terms: https://mybutlerdid.it/terms

## Disconnecting and data control

Users can disconnect Butler from Claude without deleting their Butler account. Butler account controls remain the source of truth for household membership, privacy, export and deletion.

## Support

General connector support and reproducible bugs: https://github.com/Mybutlerdid-it/claude-plugin/issues

Security vulnerabilities or sensitive reports: https://mybutlerdid.it/security

Do not post credentials, tokens, personal data or security-sensitive material in a public GitHub issue.

## Publisher packaging

The public wrapper repository contains only this Claude-facing package and public documentation. It must not contain the Butler Worker source, database schema, OAuth internals, Cloudflare configuration, commercial routing, secrets or other private backend implementation.
