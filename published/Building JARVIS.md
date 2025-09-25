## The Problem with Stateless AI

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
