# MyButlerDid.it for Claude

MyButlerDid.it gives Claude durable personal and household context while Claude remains the conversational, reasoning, research and document-understanding layer.

Butler is not a second chatbot. It stores only the durable context and follow-through the user chooses or reasonably expects Butler to keep.

## What the Claude directory package supports

- Read relevant Butler memories and visible open tasks.
- Remember or update durable facts, preferences, constraints, plans and decisions.
- Create requested Butler reminders and scheduled tasks.
- Bootstrap a private Butler profile from reliable durable context Claude already knows because the user explicitly stated or confirmed it.
- Respect Butler household roles and private/shared visibility.

This directory package intentionally does **not** expose advertising, sponsored ranking, referral routing or commerce tools.

## Connection

The directory candidate uses Butler's production OAuth-protected remote MCP service over Streamable HTTP.

Candidate endpoint:

`https://mybutlerdid.it/mcp?surface=claude-directory`

Users authenticate with their Butler account. No Butler password, API key or static connector secret is placed in this package.

The public wrapper repository is `https://github.com/Mybutlerdid-it/claude-plugin`, published by the `Mybutlerdid-it` GitHub organisation. The `claude-directory` route must not be published externally until the corresponding production routing change has been enabled and acceptance-tested.

## Example prompts

- “Butler, what do you remember about our October trip?”
- “Butler, remember that the utility cupboard opening is 605 mm wide.”
- “Butler, remind me tomorrow at 3pm to call the boiler engineer.”
- “Butler, set yourself up from the reliable things Claude already knows about me.”

## Privacy model

New directory-surface memories default to private. Butler enforces the authenticated household boundary and visibility rules server-side.

Butler does not automatically store passwords, authentication tokens, PINs, payment-card details, bank-account details, passport numbers, driving-licence numbers, national identifiers or equivalent high-risk secrets.

Claude interprets documents and images; Butler should retain only the minimum useful durable result rather than raw source bodies by default.

Public policies:

- Privacy: https://mybutlerdid.it/privacy
- Security: https://mybutlerdid.it/security
- Terms: https://mybutlerdid.it/terms

## Disconnecting and data control

Users can disconnect Butler from Claude without deleting their Butler account. Butler account controls remain the source of truth for household membership, privacy, export and deletion.

## Support

During beta, use the feedback/support route exposed from the Butler account and beta experience.

## Publisher packaging

The public wrapper repository contains only this Claude-facing package and public documentation. It must not contain the Butler Worker source, database schema, OAuth internals, Cloudflare configuration, commercial routing, secrets or other private backend implementation.
