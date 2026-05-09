# Facebook Network Explorer

Built live at the **SCSP AI+ Expo · May 9, 2026** as part of the *Building Apps with AI Coding Agents* workshop.

An interactive visualization of the [Stanford SNAP Facebook dataset](https://snap.stanford.edu/data/ego-Facebook.html) — 4,039 anonymized people and 88,234 friendships — rendered as a force-directed graph in the browser.

---

## How it works

**Data preprocessing (Python)**

The raw edge list (`facebook_combined.txt.gz`) is processed into `graph.json` using a label propagation community detection algorithm. It runs for up to 30 iterations, assigning each person to a cluster based on majority neighbour label. The output includes each node's ID, degree (friend count), and community assignment, plus the full edge list.

Result: 59 communities detected across 4,039 nodes and 88,234 edges.

**Visualization (D3.js + Canvas)**

- Force-directed layout using D3 v7 — nodes repel each other and edges act as springs, so clusters naturally emerge without manual placement
- Rendered on an HTML `<canvas>` (not SVG) for performance — 88k edges would be too slow as DOM elements
- Node size scales with `sqrt(degree)` so high-degree hubs are visible without dominating the layout
- 20-colour palette cycling across 59 communities
- D3 quadtree for O(log n) click and hover hit detection
- Force simulation runs with `alphaDecay(0.02)` then freezes — a progress bar tracks settlement in real time

**Interactions**

| Action | Effect |
|---|---|
| Click a node | Highlights the node and all its direct friends; dims everyone else |
| Click the same node again | Deselects |
| Click background | Resets to full view |
| Scroll | Zoom in / out |
| Drag | Pan |

---

## Run locally

```bash
python3 -m http.server 8080
```

Open [http://localhost:8080](http://localhost:8080). The graph takes ~10–20 seconds to settle on first load.

## Files

| File | Description |
|---|---|
| `index.html` | Single-file visualization — D3 force layout, canvas renderer, zoom/pan, click interaction |
| `graph.json` | Preprocessed graph data — nodes with degree + community, edge list (~2.7 MB) |
| `facebook_combined.txt.gz` | Raw SNAP edge list (not committed — download from SNAP) |
