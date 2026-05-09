# SCSP Workshop Demo

Facebook social network visualizer built at the SCSP AI+ Expo (May 9, 2026).

Visualizes the [Stanford SNAP Facebook dataset](https://snap.stanford.edu/data/ego-Facebook.html) — 4,039 anonymized people and ~88k friendships — as an interactive force-directed graph.

## Features

- Force-directed layout with community detection (label propagation)
- Nodes sized by degree; colors by cluster
- Click any node to highlight its direct friends
- Zoom and pan

## Run locally

```bash
python3 -m http.server 8080
```

Then open [http://localhost:8080](http://localhost:8080).
