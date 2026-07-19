<!--
title: Building JARVIS
date: 2025-09-25
-->

For some reason, I've not caught onto using ChatGPT or Gemini. Instead, I've ended up using Q CLI most. The issue though is that AI interactions start from scratch every time. No memory of previous conversations, preferences, or context. This makes Q cli a useful tools but a poor assistant.

## The Solution
I built a persistent memory system using Model Context Protocol (MCP) to connect Amazon Q CLI to specialized servers. The JARVIS agent configuration includes:

### Core MCP Servers

**Memory Server** - Persistent conversation storage
```json
"memory": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-memory"],
  "env": {
    "MEMORY_FILE_PATH": "~/Documents/Obsidian/AI-brain/memory.json"
  }
}
```

**Home Assistant** - Smart home integration via local server
```json
"home-assistant": {
  "command": "mcp-proxy",
  "env": {
    "SSE_URL": "http://homeserver:8123/mcp_server/sse",
    "API_ACCESS_TOKEN": "[your-home-assistant-token]"
  }
}
```

**Fetch Server** - Web content retrieval and processing
```json
"fetch": {
  "command": "uvx",
  "args": ["mcp-server-fetch"]
}
```

### JARVIS Identity & Bootstrap Protocol

The agent prompt defines JARVIS as a sophisticated AI assistant with:
- British communication style and wit
- Proactive strategic insights
- Technical expertise across all domains
- Automatic context loading from knowledge management system
- Continuous memory updates after significant developments

### Resource Integration

```json
"resources": [
  "file://~/Documents/Obsidian/AI-brain/**/*.md"
]
```

All markdown files in the AI brain directory are automatically accessible, creating seamless integration with my knowledge management system.

## Technical Architecture

```
Amazon Q CLI + JARVIS Agent
├── MCP Servers
│   ├── Memory (persistent storage)
│   ├── Home Assistant (smart home)
│   └── Fetch (web content)
├── Obsidian Vault Integration
├── Bootstrap Protocol (identity & context)
└── File System Tools (local access)
```

## Real Results

The system remembers and builds on:
- Technical solutions (MacBook battery optimization: 825+ cycles → 1-2% drain)
- Personal projects and writing goals
- Smart home status and automation
- Web research and content analysis
- Family context and daily patterns

## Key Benefits

1. **Continuity**: Each conversation builds on previous ones via memory server
2. **Context**: Understands personal and technical background from Obsidian vault
3. **Integration**: Controls smart home, fetches web content, manages local files
4. **Identity**: Maintains consistent JARVIS personality across sessions

## Implementation Files

The complete setup uses:
- `~/.aws/amazonq/cli-agents/jarvis.json` - JARVIS agent configuration
- `~/Documents/Obsidian/AI-brain/` - Knowledge management system
- `memory.json` - Persistent conversation storage
- Home Assistant integration for smart home control

This creates an AI that truly knows you, learns from interactions, and integrates with your digital life - moving from tool to cognitive partner.


## 2026 Update — Evolution to Claude Code

The Amazon Q CLI / JARVIS setup above has been superseded. The architecture has evolved significantly:

### What Changed

The persistent memory system has moved from Amazon Q CLI to a **Claude Code agent** running inside a containerised WhatsApp bridge (nanoclaw). This means:

- **No more Q CLI** — JARVIS now runs as Claude (Anthropic's model), accessed directly via WhatsApp
- **Memory lives in the workspace** — `/workspace/group/` replaces `~/Documents/Obsidian/AI-brain/` as the primary agent memory store, with structured `.md` files for profile, home assistant notes, etc.
- **Obsidian still used for content** — but as a publishing/blogging platform rather than the AI's primary brain
- **Home Assistant** integration is retained — connection details and API patterns now stored in `/workspace/group/home-assistant.md`
- **MCP servers** still power tool access (Home Assistant, web fetch, Obsidian), but are configured in the nanoclaw container rather than a local Q CLI agent file

### Current Architecture

```
WhatsApp → nanoclaw bridge → Claude Code agent
├── Workspace memory (/workspace/group/)
│   ├── yusuf.md          (profile & context)
│   ├── home-assistant.md (HA integration notes)
│   └── CLAUDE.md         (identity & instructions)
├── MCP Servers
│   ├── Home Assistant (http://cappucino:8123)
│   ├── Obsidian vault (read/write)
│   └── Web fetch
└── Scheduled tasks (via nanoclaw)
```

The core goal remains the same — an AI that knows you, remembers context across sessions, and integrates with your digital life. The delivery mechanism just got a whole lot more seamless.

