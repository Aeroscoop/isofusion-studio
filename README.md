# IsoFusion Studio

[![Live Demo](https://img.shields.io/badge/demo-online-brightgreen.svg)](https://aeroscoop.github.io/isofusion-studio/)

**IsoFusion Studio** is a browser-based, color-based region fusion isometric vector generator. It deterministically creates 3D voxel structures from PRNG seeds, projects them into isometric vector artwork, and intelligently merges adjacent coplanar faces of matching color clusters into unified vector boundaries with smooth linear gradients.

🚀 **Live Demo:** [https://aeroscoop.github.io/isofusion-studio/](https://aeroscoop.github.io/isofusion-studio/)

---

## ✨ Key Features

- **Color-Based Region Fusion**: Automatically detects adjacent voxels with matching colors, cancels internal shared edges, and fuses coplanar faces into single seamless vector polygons.
- **Deterministic Seeded PRNG**: Uses `cyrb128` hashing and `sfc32` random number generation to produce reproducible matrix variations from any seed string.
- **4x4 Matrix Variations**: Displays 16 unique variations per seed simultaneously for fast exploration and selection.
- **Interactive Inspector View**: Select any cell variation to view an enlarged interactive preview along with real-time statistics (voxel count, active color clusters, visible faces, and boundary loops).
- **Procedural Symmetry Rules**: Supports asymmetric organic structures, X-Axis Mirroring, XY Dual Mirroring, and 4-Fold Rotational Symmetry.
- **Customizable Color Strategies & Palettes**:
  - **Palettes**: Cyberpunk Neon, Pastel Sunset, Emerald Forest, Monochrome Tech, Warm Isometric, and Deep Ocean.
  - **Color Strategies**: Height Bands (Z-Layers), Radial Distance from center, and Connected Clusters.
- **3D Fusion Awareness**: Choose between strict 3D Coplanar Plane fusion or 2D Flat Projection Union.
- **Stroke & Outline Styling**: Toggle visible strokes, adjust line weights, and pick custom stroke colors or auto-contrast shades.
- **Zero Dependencies**: Built with pure HTML5, vanilla JavaScript, and Tailwind CSS (via CDN)—no build tools or node modules required!

---

## 🛠️ How It Works

IsoFusion Studio follows a multi-stage vector pipeline:

1. **Procedural Voxel Generation**: Generates 3D spatial voxel grids using 6-connected neighbor traversal constrained by target volume density and chosen symmetry rules.
2. **Color Assignment & 3D CCL**: Maps colors to active voxels according to the selected strategy, then runs a 3D Connected Component Labeling (CCL) algorithm to group connected voxels of matching color into distinct clusters.
3. **Isometric Projection**: Converts 3D coordinates $(x, y, z)$ into 2D isometric screen space $(px, py)$.
4. **Contour Extraction & Edge Cancellation**:
   - In **Fused Mode**, shared internal edges between faces of the same cluster and plane depth cancel out, leaving continuous boundary contours.
   - In **Grid Mode**, individual voxel faces are rendered separately.
5. **SVG Vector Generation**: Outputs clean SVG paths with dynamic linear gradients calculated per color cluster.

---

## 🚀 Getting Started

Since IsoFusion Studio is a lightweight static web app, no build step or installation is necessary:

1. Clone the repository:
   ```bash
   git clone https://github.com/aeroscoop/isofusion-studio.git
   cd isofusion-studio
   ```
2. Open `index.html` directly in your web browser, or serve it locally using any static file server:
   ```bash
   # Python 3
   python3 -m http.server 8000
   ```
3. Open `http://localhost:8000` in your browser.

---

## 📄 License

MIT License. Feel free to use, modify, and build upon IsoFusion Studio!
