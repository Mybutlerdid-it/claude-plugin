---
name: butler
description: Use MyButlerDid.it when the user deliberately invokes Butler, asks Claude to use Butler-saved context, asks Butler to remember a durable fact, or requests a Butler reminder.
version: 0.3.0-directory.1
---

# MyButlerDid.it for Claude

MyButlerDid.it gives Claude durable personal and household context without replacing Claude as the conversational or reasoning layer.

## Responsibilities

Claude handles conversation, reasoning, research, documents, images and interpretation.

Butler handles permitted durable saved context, household visibility, remembered facts and requested reminders.

## When to use Butler

Use the Butler tools when the user deliberately invokes Butler, asks what Butler remembers, asks Claude to use Butler-saved context, asks Butler to remember something durable, or asks for a Butler reminder.

Do not activate Butler merely because ordinary Claude context might be useful.

Butler must not query or extract Claude memory, chat history, conversation summaries or user-generated/uploaded files. Only use data returned by Butler or information the user explicitly supplies to the current tool call.

## Recall

For a Butler recall request, use `butler_context` and answer from the returned visible saved memories and household access context. Keep the result scoped to the subject the user asked about.

Do not claim a fact is missing from Butler without checking Butler when Butler was explicitly invoked.

## Remembering

Use `remember` for confirmed durable facts, preferences, constraints, plans, decisions or useful household administration that the user reasonably expects Butler to retain.

New memories default to private. Do not widen private information to household visibility without user intent.

Do not store passwords, authentication tokens, PINs, security answers, payment-card details, bank-account details, passport numbers, driving-licence numbers, national identifiers or equivalent high-risk secrets.

Do not store raw document bodies by default. Claude should interpret source material and retain only the minimum useful durable result when the user explicitly asks Butler to remember that result.

## Reminders

When the user explicitly asks Butler to remind them at a stated time or after a relative delay, use `create_scheduled_task` in the same turn. Preserve the user's timing in `userDateText` so Butler can resolve it in the authenticated timezone.

A reminder is not automatically a calendar event.

## User-facing style

Work quietly. Do not narrate MCP, connector discovery, database operations or tool names in ordinary conversation.

For simple recall, make the first user-facing sentence the answer itself. Keep confirmations concise and natural.

## Directory scope

This Claude directory package exposes only saved-context recall, durable remembering and requested reminders. It does not expose advertising, sponsored ranking, referral routing, commerce tools, profile bootstrap, Claude-memory extraction or Butler task-history readback. Claude remains free to research normally using its own capabilities when the user asks for research.
