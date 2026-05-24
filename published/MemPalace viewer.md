<!--
title: MemPalace Viewer - Visualising AI Memory in 3D
date: 2026-05-24
-->

# MemPalace Viewer - Visualising AI Memory in 3D

I've iterated over different forms of memory and RAG over the past few years and settled into using/sharing my Obsidian notes with my AI assistant, JARVIS, which now has nearly 2,000 memories. The last major change I made involved switching to MemPalace, an open source project which stores memories in a ChromaDB-backed "memory palace." 

After the migration I was curious to *see* how the memories were organised so I built a 3D viewer to find out.

## The concept

The memory palace technique is ancient - assign memories to locations in an imagined building, then mentally walk through it to recall them. MemPalace (the MCP server) uses this metaphor: wings for projects, rooms for categories, drawers for individual memories.

The viewer makes the metaphor literal. It renders the palace as a 3D wireframe mansion you can navigate - click on drawers to read memories, search semantically, toggle visibility of wings and rooms.

## What you see

A blueprint-aesthetic 3D scene: dark background, cyan wireframes, fog, grid floor. Wings are rendered as building sections, rooms as spaces within them, and memories as small cubes you can click. Every 3 wings get their own floor, connected by curved staircases.

Search results highlight in 3D - type a query and matching drawers glow, with results listed in a sidebar panel.

## Tech stack

- **Frontend**: React + Three.js via @react-three/fiber
- **API**: Python HTTP server reading directly from ChromaDB
- **Data**: The same `~/.mempalace/palace/` database my AI agents use daily

The viewer is read-only - it doesn't modify the palace, just visualises it. The API exposes structure, drawer contents, and semantic search endpoints.

## Running it

```bash
git clone https://github.com/yusufk/mempalace-viewer
cd mempalace-viewer
npm install
python api/server.py &
npm run dev
```

Requires a mined MemPalace at `~/.mempalace/palace/`.

## Links

- [MemPalace Viewer - GitHub](https://github.com/yusufk/mempalace-viewer)
- [MemPalace MCP Server](https://github.com/milla-jovovich/mempalace) - the original project

#ai #threejs #react #visualisation #opensource
