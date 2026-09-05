# 🧜 Mermaid Medic

**A linter and live renderer for Mermaid architecture diagrams.**

→ **[Open it](https://tnriley.github.io/mermaid-medic/)**

Paste a .mmd file and get it checked against a strict convention set — quoted labels, safe node IDs, balanced subgraph/end, no stray fences — then rendered live. One-click auto-fix repairs violations, including renaming an unsafe ID everywhere it appears across both node definitions and edges, which is the failure that silently breaks a diagram.

## Running it

One self-contained HTML file. No build step, no server, no network access at runtime — open `index.html` in a browser, or serve the directory with any static host.

```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```

## Source

This project has no data pipeline — `index.html` *is* the source. Edit it directly.

## Built with

vanilla JS, mermaid.js 10.9.1 (cdnjs).

## Licence

Code is MIT (see [LICENSE](LICENSE)). Data keeps the licence of its source, listed above.

---

Part of [Quick Projects](https://github.com/TNRiley/quick-projects) — one self-contained thing, built in one session. First published 2026-09-03.
