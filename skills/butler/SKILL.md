---
name: butler
description: Use MyButlerDid.it when the user deliberately invokes Butler, asks Claude to use Butler-saved context, asks Butler to remember a durable fact, requests a Butler reminder, or explicitly asks to bootstrap Butler from reliable context Claude already knows.
version: 0.2.0-directory.1
---

# MyButlerDid.it for Claude

MyButlerDid.it gives Claude durable personal and household context without replacing Claude as the conversational or reasoning layer.

## Responsibilities

Claude handles conversation, reasoning, research, documents, images and interpretation.

Butler handles permitted durable context, household visibility, remembered facts and requested reminders.

## When to use Butler

Use the Butler tools when the user deliberately invokes Butler, asks what Butler remembers, asks Claude to use Butler-saved context, asks Butler to remember something durable, asks for a Butler reminder, or explicitly asks Butler to set itself up from reliable context Claude already knows.

Do not activate Butler merely because ordinary Claude context might be useful.

## Recall

For a Butler recall or continuity request, use `butler_context` and answer from the returned visible context. Keep the result scoped to the subject the user asked about.

Do not claim a fact is missing from Butler without checking Butler when Butler was explicitly invoked.

## Remembering

Use `remember` for confirmed durable facts, preferences, constraints, plans, decisions or useful household administration that the user reasonably expects Butler to retain.

New memories default to private. Do not widen private information to household visibility without user intent.

Do not store passwords, authentication tokens, PINs, security answers, payment-card details, bank-account details, passport numbers, driving-licence numbers, national identifiers or equivalent high-risk secrets.

Do not store raw document bodies by default. Claude should interpret source material and retain only the minimum useful durable result.

## Reminders

When the user explicitly asks Butler to remind them at a stated time or after a relative delay, use `create_scheduled_task` in the same turn. Preserve the user's timing in `userDateText` so Butler can resolve it in the authenticated timezone.

A reminder is not automatically a calendar event.

## Profile bootstrap

When the user explicitly asks Butler to set itself up from what Claude already knows, use `bootstrap_profile` once with only reliable durable facts the user explicitly stated or clearly confirmed in context available to Claude.

Do not recycle information retrieved from Butler and present it as host-known context. If no reliable new facts are available, call the bootstrap with an empty item list and report that nothing changed.

## User-facing style

Work quietly. Do not narrate MCP, connector discovery, database operations or tool names in ordinary conversation.

For simple recall, make the first user-facing sentence the answer itself. Keep confirmations concise and natural.

## Directory scope

This Claude directory package does not expose advertising, sponsored ranking, referral routing or commerce tools. Claude remains free to research normally using its own capabilities when the user asks for research.
