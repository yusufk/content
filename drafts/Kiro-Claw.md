<!--
title: Kiro-Claw - AI Assistant on Telegram
date: 2026-05-24
-->

# Kiro-Claw - AI Assistant on Telegram

I wanted my AI assistant available on my phone, not just at my laptop. Kiro-Claw bridges Telegram to a containerised AI agent, giving me JARVIS in my pocket.

## Architecture

```
Telegram → python-telegram-bot → Docker container (kiro-cli) → IPC → Telegram
```

A Python bot receives messages, routes them to a persistent Docker container running kiro-cli, and delivers responses back. The container has access to my memory system, Home Assistant, and project files.

## Key design decisions

**Persistent container** - not one-per-message. The first message takes ~45s (cold start), subsequent messages respond in 11-18s. The container maintains conversation context across messages.

**Silent architecture** - container stdout is internal dialogue, never forwarded to Telegram. The agent communicates deliberately via `jarvis-send` IPC. This eliminates tool execution noise leaking into chat.

**Event processing** - Home Assistant events arrive via webhook, get batched and routed through the agent. FRIDAY (the container persona) decides what's noteworthy and what to ignore. No "ok" spam for routine motion events.

**DEFCON system** - controls which events reach the agent based on time of day and threat level. Night-time automatically escalates to include movement events.

## Features

- Streaming message drafts (Telegram Bot API 9.3 `sendMessageDraft`)
- Task scheduling (`/remind 30m Check server`, cron expressions)
- Proactive messaging (agent → Telegram without user prompt)
- Camera snapshots via Home Assistant API
- Project file access (mounted read-write)
- Shared memory with the laptop JARVIS instance

## The FRIDAY persona

The container agent is named FRIDAY (like Stark's second AI). It handles security monitoring, casual queries, and always-on tasks. JARVIS (laptop) handles deep development work. They share the same memory system via git-synced brain files.

## Links

- [GitHub](https://github.com/yusufk/kiro-claw)

#ai #telegram #docker #python #homeautomation
