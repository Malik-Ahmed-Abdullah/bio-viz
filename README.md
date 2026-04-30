# 🧬 bio-viz — Tree & Graph Visualization

Interactive visualizations of two biological datasets using Python and NetworkX — an evolutionary phylogenetic tree and a Monarch butterfly migration network.

---

## 📁 Repository Structure

```
bio-viz/
├── bio-viz.ipynb        # Main notebook (all code + outputs)
├── index.html           # Github page export for the notebook
└── README.md
```

---

## 🌳 Dataset 1 — Evolutionary Tree of Life

**Source:** Curated from the [Open Tree of Life](https://tree.opentreeoflife.org/) project and published phylogenetic literature.

| | |
|---|---|
| **Nodes** | 68 — species (leaves) or common ancestors/clades (internal nodes) |
| **Edges** | 67 — directed evolutionary/ancestral relationships (parent → descendant) |
| **Root** | Life (LUCA) — Last Universal Common Ancestor |

**Why a tree?** Phylogenetic data is inherently hierarchical and acyclic — every organism traces back to a single common ancestor with no cycles, making it a perfect tree structure.

### Layouts

**Layout 1 — Radial (Dendrogram)**

Nodes radiate outward from the root (LUCA) in a circular pattern. Each domain gets a wedge of the circle proportional to its diversity. Colour-coded by domain/kingdom.

![Radial Layout](tree_radial.png)

**Layout 2 — Hierarchical (Top-Down)**

Classic top-down tree with the root at the top and species at the bottom. Node x-positions are computed from leaf counts so that deep branches (e.g. Animalia) get proportionally more horizontal space. Leaf labels are rotated 45° for readability.

![Hierarchical Layout](tree_hierarchical.png)

---

## 🦋 Dataset 2 — Monarch Butterfly Migration Network

**Source:** Derived from [Journey North](https://journeynorth.org/monarchs) citizen science data and USGS Monarch butterfly migration studies.

| | |
|---|---|
| **Nodes** | 21 — geographic waypoint regions across North America |
| **Edges** | 31 — recorded migration corridors between regions |
| **Edge weight** | Relative volume of butterfly movement (1–10 scale) |

**Why a graph?** Migration networks contain cycles (butterflies travel north in spring and south in autumn), multiple paths between nodes, and weighted edges — making it a true weighted undirected graph rather than a tree.

### Layouts

**Layout 1 — Geographic (Lat/Lon)**

Nodes are placed at their real geographic coordinates. Edge colour and thickness encode migration volume. Reveals the physical flyways over North America — the central corridor (Texas → Great Plains → Great Lakes) carries the heaviest traffic.

![Geographic Layout](graph_geographic.png)

**Layout 2 — Force-Directed (Spring)**

Nodes are positioned by connectivity strength. High-traffic hubs (Michoacán, Michigan, Ontario) are pulled to the centre. A glowing edge effect highlights the busiest corridors.

![Spring Layout](graph_spring.png)

---

## 🚀 Running the Notebook

### Requirements

```bash
pip install networkx matplotlib numpy jupyter
```

### Run locally

```bash
git clone https://github.com/Malik-Ahmed-Abdullah/bio-viz.git
cd bio-viz
jupyter notebook bio-viz.ipynb
```

### View online

The rendered notebook is published via GitHub Pages at:
`https://Malik-Ahmed-Abdullah.github.io/bio-viz/`

---

## 🛠 Tech Stack

| Library | Purpose |
|---|---|
| `networkx` | Graph construction and layout algorithms |
| `matplotlib` | Rendering and styling all visualizations |
| `numpy` | Coordinate calculations for radial layout |

---

## 📊 Summary

| | Dataset | Nodes | Edges | Layouts |
|---|---|---|---|---|
| 🌳 Tree | Evolutionary Tree of Life | 68 | 67 | Radial, Hierarchical |
| 🦋 Graph | Monarch Butterfly Migration | 21 | 31 | Geographic, Force-Directed |
