# Rebuilding Mermaid Medic

> **Provenance note.** Reconstructed 2026-09-05 from the build log. No data pipeline —
> `index.html` is the source.

---

## 1. What you are building

A single self-contained HTML page: a linter and live renderer for Mermaid architecture diagrams,
built to serve the RELMermaid documentation repo's conventions.

## 2. The rules it enforces

- Labels must be **quoted**.
- Node IDs must match `[A-Za-z0-9_]` only.
- `subgraph` / `end` must balance.
- No stray code fences in the `.mmd` file.

## 3. The page

- Paste or drop a `.mmd` file; violations are listed with line references.
- **Live render** via `mermaid.js` — the one external dependency, loaded pinned from cdnjs
  (`https://cdnjs.cloudflare.com/ajax/libs/mermaid/10.9.1/mermaid.min.js`). This is the only
  project in the collection that loads anything external at runtime.
- **One-click auto-fix.** The important case: renaming an unsafe node ID must rewrite it
  **globally — in the node definitions *and* every edge that references it**. A partial rename is
  worse than none, because it silently breaks the diagram rather than failing loudly.

## 4. Verification

Feed it a diagram with an unsafe ID used in several edges, auto-fix, and confirm the rendered
output is unchanged in shape — same nodes, same connections, valid IDs.

## 5. Scope

It complements RELMermaid; it does not reimplement it. Keep it a helper for the docs repo.
