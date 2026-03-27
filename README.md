# 🧠 BrainRing

**Interactive Brain Connectivity Chord Diagram Visualizer**
**交互式脑连接环形可视化工具**

> No install. No backend. No Python. Just open and visualize.
> 无需安装，无需后端，无需Python，打开即用。

[![Version](https://img.shields.io/badge/version-1.0-blue)]()
[![License](https://img.shields.io/badge/license-MIT-green)]()
[![GitHub Pages](https://img.shields.io/badge/demo-live-brightgreen)](https://XiuFan719.github.io/brain-connectivity-viz/)

**Live Demo / 在线体验**: [https://XiuFan719.github.io/brain-connectivity-viz/](https://XiuFan719.github.io/brain-connectivity-viz/)

---

## ✨ Why BrainRing? / 为什么选择 BrainRing？

| Pain Point | BrainRing Solution |
|---|---|
| Circos requires writing config files / Circos 需要写配置文件 | Pure visual interaction, click to generate / 纯可视化交互，点击即出图 |
| BrainNet Viewer requires MATLAB / BrainNet Viewer 需要 MATLAB | Pure web, works on any device / 纯网页，任何设备都能用 |
| Repeated script runs to adjust a figure / 反复跑脚本调参 | Real-time preview, all parameters via sliders / 实时预览，滑块调节 |
| Changing one edge color is tedious / 改一条边颜色很麻烦 | Click any connection to recolor / 点击连接线直接改色 |
| Switching between tools for different atlases / 不同图谱切换工具 | 8 built-in atlases, one-click switch / 内置 8 套图谱一键切换 |
| Circos link files need preprocessing / Circos link 文件需要预处理 | Direct upload, colors auto-detected / 直接上传，颜色自动识别 |

---

## 🎯 Features / 功能

### Atlas Support / 图谱支持 (8 atlases)

| Atlas | Regions | Type | Structure |
|-------|---------|------|-----------|
| **Brainnetome 246** | 246 | Anatomical | Lobe → Gyrus → Subregion (L/R) |
| **AAL-90** | 90 | Anatomical | Lobe → Region (L/R) |
| **AAL-116** | 116 | Anatomical | Lobe → Region + Cerebellum (L/R) |
| **Schaefer-100** | 100 | Functional | Yeo 7-Network → Parcels (L/R) |
| **Schaefer-200** | 200 | Functional | Yeo 7-Network → Parcels (L/R) |
| **Schaefer-400** | 400 | Functional | Yeo 7-Network → Parcels (L/R) |
| **Power-264** | 264 | Functional | 14 Networks → Nodes |
| **Dosenbach-160** | 160 | Functional | 7 Networks → ROIs |

### Visualization / 可视化

- **Dark / Light Theme** — Theme only affects the canvas; panels stay dark. Useful for white-background publication figures.
  深色/浅色主题 — 主题只影响画布，面板保持深色 UI。白底适合论文出图。
- **Multi-level Labels** — Toggle Lobe names, Gyrus names (on ring), sub-region labels, and index numbers independently.
  多级标签 — Lobe 名 / Gyrus 名(环上) / 子脑区 / 编号，自由组合。
- **6 Color Schemes** — Classic, Neon, Pastel, Earth, BNA, Mono.
  6 套配色方案。
- **Color Intensity Slider** — Adjust overall color brightness/darkness (-80 to +80) without changing the scheme.
  颜色深度滑块 — 不改配色方案，直接调明暗。
- **Arc Color Mode** — Flat (uniform per lobe) or Gradient (smooth variation within each lobe).
  圆环配色模式 — 纯色或渐变（同一脑叶内从深到浅渐变）。
- **3 Separator Modes** — None / Fine lines / Gap separation (Circos-style), with adjustable gap size (20%–300%).
  三种分隔模式 — 无 / 细线 / 间隔（类 Circos），间隔大小可调（20%-300%）。
- **Rotation** — 0°–360° slider to rotate the entire ring.
  旋转角度 — 滑块旋转整个圆盘。
- **Circle Size** — Scale the chart from 30% to 100%.
  圆环大小 — 整体缩放。
- **Arc Highlight Toggle** — Choose whether selected regions darken or all arcs stay uniform.
  选中加深开关 — 选择是否加深有连接的脑区弧段。
- **Full Parameter Control** — Ring width (4–100), arc padding, line width, opacity, Gyrus font size — all adjustable via sliders.
  全参数可调 — 圆环宽度、弧间距、线条粗细、透明度、Gyrus 字号。

### Edge Control / 边控制

- **Threshold Filtering** — Show only edges above a FC threshold.
  阈值筛选 — 只显示大于阈值的连接。
- **Top-N Filtering** — Show the N strongest / weakest / highest absolute value edges.
  Top-N 筛选 — 展示最强/最弱/绝对值最大的 N 条。
- **Manual Edge Input** — Type `[234,16]` to add specific connections. Batch input supported.
  手动添加边 — 输入 `[234,16]`，支持批量。
- **Click-to-Connect Mode** — Switch to connect mode, click region A then region B to create an edge. Auto-resets after each pair.
  点击连边模式 — 在图上依次点击两个脑区即可连线，连完自动重置。
- **Click-to-Recolor Edges** — Click any connection line to open a color picker with preset swatches and custom colors.
  点击改色 — 点击任意连接线弹出颜色选择器。
- **Edge Color Mode** — Follow region color or use a fixed global color.
  边颜色模式 — 跟随脑区或固定颜色。
- **Edge List with Delete** — All manual edges listed with full region labels and individual delete buttons.
  边列表管理 — 显示完整脑区名称，逐条删除。

### Gyrus Text Interaction / Gyrus 文字交互

- **Click to Edit** — Click any Gyrus name on the ring to open an edit popup: rename, recolor, resize font, or hide.
  点击编辑 — 点击圆环上任意 Gyrus 名，可改名、改色、改字号、隐藏。
- **Per-Gyrus Font Size** — Individually set font size for each Gyrus (e.g., shrink long names, enlarge important ones).
  单独调字号 — 每个 Gyrus 可以设置不同字号。
- **3 Text Color Modes** — Auto black/white (adapts to theme), Fixed color, Follow lobe color.
  三种文字颜色模式 — 自动黑/白、固定颜色、跟随脑区。
- **One-Click All Color** — Set all Gyrus text to a single color instantly (e.g., black for white-background export).
  一键全部改色 — 白底出图时一键设为黑色。

### Reorder / 脑区排列

- **Gyrus-Level Reorder** — Select a Gyrus and move it to any position. Other regions auto-fill.
  Gyrus 级别重排 — 选择一个 Gyrus 移到任意位置，其他脑区自动补位。
- **Data Remapping** — FC matrix, selections, manual edges, custom colors all remap automatically.
  数据跟随 — FC 矩阵、选中状态、手动边、自定义颜色全部自动重映射。
- **Reset** — One click to restore default order.
  一键重置。

### Data I/O / 数据导入导出

- **Upload FC Matrix** — CSV/TXT/TSV, N×N format. Auto-detects delimiter.
  上传 FC 矩阵 — 支持 CSV/TXT/TSV。
- **Upload Edge List** — One edge per line: `i, j, weight`.
  上传边列表。
- **Upload Circos Link File** — Supports `hs33 20000 800000 hs69 20000 800000 color=170,170,170 value=0.027` format. Auto-parses region IDs, edge weights, and per-edge colors.
  上传 Circos link 文件 — 自动解析编号、权重、颜色。
- **Export SVG** — Publication-ready vector graphics with background color.
  导出 SVG — 带背景色的矢量图。
- **Export PNG** — 4× resolution raster image for presentations and sharing.
  导出 PNG — 4 倍分辨率。
- **Export FC Matrix** — Download current FC data as CSV.
  导出 FC 矩阵。

---

## 🚀 Quick Start / 快速开始

### Online / 在线使用

Visit / 访问: **[https://XiuFan719.github.io/brain-connectivity-viz/](https://XiuFan719.github.io/brain-connectivity-viz/)**

### Local / 本地使用

Download `index.html` and open in any modern browser. That's it.
下载 `index.html`，双击用浏览器打开即可。

---

## 📖 Usage Guide / 使用说明

### Import FC Matrix / 导入 FC 矩阵

1. Extract FC matrix using Nilearn / DPABI / CONN, save as CSV.
   用 Nilearn / DPABI / CONN 提取 FC 矩阵，保存为 CSV。
2. Click "FC 矩阵" in the left panel.
   左侧面板点击 "FC 矩阵"。
3. The tool auto-detects matrix size and displays top connections.
   工具自动识别矩阵大小并显示连接。

### Import Circos Link File / 导入 Circos link 文件

1. Prepare a Circos-format link file (e.g., `feng.txt`).
2. Click "Circos Link" to upload.
3. Auto-parses `hs` region IDs, `value=` weights, and `color=r,g,b` per-edge colors.
   自动解析编号、权重、颜色。

### Manual Edge Input / 手动指定连接

Type in the input box (1-indexed region IDs):
在输入框中输入（1-indexed 编号）：
```
[234,16]          ← single edge / 单条边
[1,2],[3,4],[5,6] ← batch / 批量
```

### Click-to-Connect / 点击连边

1. Switch to "点击连边" mode in the left panel.
   切到"点击连边"模式。
2. Click region A on the ring → status shows selected region.
   点击第一个脑区。
3. Click region B → edge created, auto-resets for next pair.
   点击第二个，连线完成，自动重置。

### Edit Gyrus Text / 编辑 Gyrus 文字

1. Click any Gyrus name on the ring.
   点击圆环上任意 Gyrus 名称。
2. Popup: rename, change color, adjust font size, or hide.
   弹出面板：改名、改色、调字号、隐藏。

### Reorder Regions / 脑区重排

1. Left panel → "Reorder" section.
   左侧面板 → "Reorder" 区块。
2. Select source Gyrus → target position → Click "移动".
   选择源 Gyrus → 目标位置 → 点击"移动"。
3. All data remaps automatically.
   所有数据自动重映射。

### Export for Publication / 导出论文插图

1. Switch to Light theme (white background).
   切换浅色主题（白底）。
2. Select Gap separation for Circos-style spacing.
   选择间隔分隔。
3. Adjust color intensity for more saturated colors.
   调整颜色深度。
4. Use "一键设置所有Gyrus文字颜色" → enter `#000000` for black text.
   一键设置文字为黑色。
5. Click "导出 SVG" or "导出 PNG".
6. Optionally refine in Inkscape / Illustrator.
   可选：用 Inkscape / Illustrator 做最终编辑。

---

## 🛠️ Tech Stack

- **D3.js** v7 — SVG rendering
- Pure HTML/CSS/JS — single file, no build tools
- Google Fonts (JetBrains Mono, DM Sans)

---

## 📋 Roadmap

- [ ] Glass brain (3D) view / 3D 玻璃脑视图
- [ ] FC matrix heatmap linked view / FC 矩阵热力图联动
- [ ] More atlases: Desikan-Killiany, Gordon 333, Glasser 360 / 更多图谱
- [ ] Group comparison visualization (A vs B) / 分组对比可视化
- [ ] Edge bundling for dense connections / 密集连接的边捆绑

---

## 📬 Contact

Questions, suggestions, or collaboration inquiries are welcome.
有问题、建议或合作意向，欢迎联系。

**Email**: xdfanxiao@163.com
**GitHub**: [@XiuFan719](https://github.com/XiuFan719)

---

## 📄 License

MIT License — Free for academic and commercial use.
MIT 许可证 — 学术和商业用途均可自由使用。

## 📝 Citation

If BrainRing helps your research, please consider citing:
如果 BrainRing 对你的研究有帮助，欢迎引用：

```
BrainRing: Interactive Brain Connectivity Chord Diagram Visualizer
https://github.com/XiuFan719/brain-connectivity-viz
```

---

**Keywords / 关键词**: brain connectivity, chord diagram, circos, fMRI, functional connectivity, neuroimaging visualization, brain atlas, connectome, 脑连接可视化, 脑功能连接, 弦图, fMRI可视化, Brainnetome, AAL, Schaefer, Power264, Dosenbach
