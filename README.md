# 🧠 BrainRing

**Interactive Brain Connectivity Chord Diagram Visualizer**
**交互式脑连接环形可视化工具**

> No install. No backend. No Python. Just open and visualize.
> 无需安装，无需后端，无需Python，打开即用。

[![Version](https://img.shields.io/badge/version-1.0-blue)]()
[![License](https://img.shields.io/badge/license-MIT-green)]()
[![GitHub Pages](https://img.shields.io/badge/demo-live-brightgreen)](https://XiuFan719.github.io/brain-connectivity-viz/)

---

## ✨ Why BrainRing?

| Pain Point | BrainRing Solution |
|---|---|
| Circos 需要写 conf 配置文件 | 纯可视化交互，点击即出图 |
| BrainNet Viewer 需要 MATLAB | 纯网页，任何设备都能用 |
| 画一张图要反复调参跑脚本 | 实时预览，所有参数滑块调节 |
| 想改一条边的颜色很麻烦 | 点击连接线直接改色 |
| 不同图谱要切换不同工具 | 内置 8 套图谱一键切换 |

## 🎯 Features / 功能

### Atlas Support / 图谱支持
- **Brainnetome 246** — 完整三级层次 (Lobe → Gyrus → Subregion)，数据来自官方 Excel
- **AAL-90 / AAL-116** — 经典解剖学图谱（含小脑）
- **Schaefer 100 / 200 / 400** — Yeo 7-Network 功能分区
- **Power 264** — 14 功能网络，264 节点
- **Dosenbach 160** — 7 功能网络，160 ROIs

### Visualization / 可视化
- 🎨 **两种绘制风格**: 默认紧凑风格 / Circos 经典分隔风格
- 🌓 **深色 / 浅色主题**: 适配屏幕查看和论文出图
- 🏷️ **多级标签**: Lobe 名 / Gyrus 名(环上) / 子脑区 / 编号，自由组合
- 📐 **全参数可调**: 圆环宽度、弧间距、线条粗细、透明度

### Edge Control / 边控制
- 🔝 **Top-N 筛选**: 展示最强/最弱/绝对值最大的 N 条连接
- 🎯 **手动添加边**: 输入 `[234,16]` 即可画指定连接
- 🖱️ **点击改色**: 点击任意连接线，弹出颜色选择器单独设色
- 🎨 **全局边颜色**: 跟随脑区 / 固定颜色 两种模式

### Data I/O / 数据导入导出
- 📂 **上传 FC 矩阵**: CSV/TXT/TSV 格式的 N×N 连接矩阵
- 📂 **上传边列表**: 每行 `i, j, weight` 格式
- 💾 **导出 SVG**: 带背景色的矢量图，直接用于论文
- 💾 **导出 FC 矩阵**: 当前数据导出为 CSV

## 🚀 Quick Start / 快速开始

### Online / 在线使用

访问: **https://XiuFan719.github.io/brain-connectivity-viz/**

### Local / 本地使用

下载 `index.html`，双击用浏览器打开即可。

## 📖 Usage / 使用说明

### 导入你的 FC 矩阵

1. 用 Nilearn / DPABI / CONN 等工具提取 FC 矩阵，保存为 CSV
2. 左侧面板点击 "上传 FC 矩阵"
3. 工具自动识别矩阵大小、选中强连接节点、调整显示

### 手动指定连接

在输入框中输入（支持 1-indexed 的 BNA 编号）:
```
[234,16]          ← 单条边
[1,2],[3,4],[5,6] ← 批量
```

### 单独改边颜色

1. 在图上点击一条连接线
2. 弹出颜色面板，选择预设色或自定义
3. 自定义颜色会保留，不受其他参数调节影响

### 导出论文插图

1. 切换到 "浅色" 主题
2. 选择 "Circos经典" 风格
3. 调整圆环宽度和线条粗细
4. 点击 "导出 SVG"
5. 用 Inkscape / Illustrator 做最终编辑

## 🛠️ Tech Stack

- **D3.js** v7 — SVG 渲染
- 纯 HTML/CSS/JS 单文件，无需构建工具
- Google Fonts (JetBrains Mono, DM Sans)

## 📋 Roadmap

- [ ] Glass brain (3D 玻璃脑) 视图
- [ ] NIfTI 文件在线解析 (需后端)
- [ ] FC 矩阵热力图联动
- [ ] 更多图谱 (Desikan-Killiany, Gordon 333, Glasser 360)
- [ ] 分组对比可视化 (Group A vs Group B)

## 📄 License

MIT License — 学术和商业用途均可自由使用。

## 📝 Citation

如果 BrainRing 对你的研究有帮助，欢迎Star：

```
BrainRing: Interactive Brain Connectivity Chord Diagram Visualizer
https://github.com/XiuFan719/brain-connectivity-viz
```

---

**Keywords / 关键词**: brain connectivity, chord diagram, circos, fMRI, functional connectivity, neuroimaging visualization, 脑连接可视化, 脑功能连接, 弦图, fMRI可视化, Brainnetome, AAL, Schaefer, Power264
