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
| Circos link 文件不能直接用 | 直接上传 Circos link 文件，颜色自动识别 |

## 🎯 Features / 功能

### Atlas Support / 图谱支持 (8 atlases)
- **Brainnetome 246** — 完整三级层次 (Lobe → Gyrus → Subregion)，数据来自官方 Excel
- **AAL-90 / AAL-116** — 经典解剖学图谱（含小脑）
- **Schaefer 100 / 200 / 400** — Yeo 7-Network 功能分区
- **Power 264** — 14 功能网络，264 节点
- **Dosenbach 160** — 7 功能网络，160 ROIs

### Visualization / 可视化
- 🌓 **深色 / 浅色主题**: 主题只影响画布，面板保持深色 UI
- 🏷️ **多级标签**: Lobe 名 / Gyrus 名(环上) / 子脑区 / 编号，自由组合
- 📐 **全参数可调**: 圆环宽度(4-100)、弧间距、线条粗细、透明度、Gyrus 字号
- 🎨 **6 套配色方案**: Classic / Neon / Pastel / Earth / BNA / Mono
- 🔄 **颜色深度调节**: 滑块控制整体颜色明暗，配色预设栏不受影响
- 🔃 **旋转角度**: 0°-360° 滑块旋转整个圆盘
- ✂️ **三种分隔模式**: 无分隔 / 细线分隔 / 间隔分隔（Circos 风格）

### Edge Control / 边控制
- 🔝 **Top-N 筛选**: 展示最强/最弱/绝对值最大的 N 条连接
- 📊 **阈值筛选**: 按 FC 值阈值过滤
- 🎯 **手动添加边**: 输入 `[234,16]` 即可画指定连接
- 🖱️ **点击改色**: 点击任意连接线，弹出颜色选择器单独设色
- 🎨 **全局边颜色**: 跟随脑区 / 固定颜色 两种模式

### Gyrus Text / Gyrus 文字交互
- ✏️ **点击编辑**: 点击圆环上任意 Gyrus 名可改名、改色、隐藏
- 🎨 **文字颜色模式**: 自动黑/白、固定颜色、跟随脑区三种模式
- 📏 **统一字号**: Gyrus 字号滑块控制，所有标签统一大小

### Reorder / 脑区排列
- 🔀 **Gyrus 级别拖排**: 选择一个 Gyrus 移动到任意位置，其他脑区自动补位
- ↩️ **一键重置**: 恢复默认排列顺序
- 🔗 **数据跟随**: FC 矩阵、选中状态、手动边、自定义颜色全部跟着重映射

### Data I/O / 数据导入导出
- 📂 **上传 FC 矩阵**: CSV/TXT/TSV 格式的 N×N 连接矩阵
- 📂 **上传边列表**: 每行 `i, j, weight` 格式
- 📂 **上传 Circos Link 文件**: 支持 `hs33 20000 800000 hs69 20000 800000 color=170,170,170 value=0.027` 格式，自动识别颜色
- 💾 **导出 SVG**: 带背景色的矢量图，直接用于论文
- 💾 **导出 FC 矩阵**: 当前数据导出为 CSV

## 🚀 Quick Start / 快速开始

### Online / 在线使用

访问: **https://XiuFan719.github.io/brain-connectivity-viz/**

### Local / 本地使用

下载 `index.html`，双击用浏览器打开即可。

## 📖 Usage / 使用说明

### 导入 FC 矩阵

1. 用 Nilearn / DPABI / CONN 等工具提取 FC 矩阵，保存为 CSV
2. 左侧面板点击 "FC 矩阵"
3. 工具自动识别矩阵大小、选中强连接节点、调整显示

### 导入 Circos Link 文件

1. 准备好 Circos 格式的 link 文件（如 `feng.txt`）
2. 点击 "Circos Link" 上传
3. 自动解析 `hs编号`、`value=` 权重、`color=r,g,b` 颜色
4. 所有边及其颜色自动显示

### 手动指定连接

在输入框中输入（支持 1-indexed 编号）:
```
[234,16]          ← 单条边
[1,2],[3,4],[5,6] ← 批量
```

### 单独改边颜色

1. 在图上点击一条连接线
2. 弹出颜色面板，选择预设色或自定义
3. 自定义颜色会保留，不受其他参数调节影响

### 编辑 Gyrus 文字

1. 点击圆环上任意 Gyrus 名称
2. 弹出编辑面板：可改名称、颜色、或隐藏
3. 例如把 "SFG" 改成 "额上回"

### 脑区重排

1. 左侧面板 "Reorder" 区块
2. 选择要移动的 Gyrus 和目标位置
3. 点击 "移动"，所有数据自动重映射

### 导出论文插图

1. 切换到 "浅色" 主题（白底）
2. 选择 "间隔分隔" 获得 Circos 经典效果
3. 调整颜色深度让配色更饱和
4. 调整圆环宽度和线条粗细
5. 点击 "导出 SVG"
6. 用 Inkscape / Illustrator 做最终编辑

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

## 📬 Contact

有问题、建议或合作意向，欢迎联系：

**Email**: xdfanxiao@163.com
**GitHub**: [@XiuFan719](https://github.com/XiuFan719)

## 📄 License

MIT License — 学术和商业用途均可自由使用。

## 📝 Citation

如果 BrainRing 对你的研究有帮助，欢迎引用：

```
BrainRing: Interactive Brain Connectivity Chord Diagram Visualizer
https://github.com/XiuFan719/brain-connectivity-viz
```

---

**Keywords / 关键词**: brain connectivity, chord diagram, circos, fMRI, functional connectivity, neuroimaging visualization, 脑连接可视化, 脑功能连接, 弦图, fMRI可视化, Brainnetome, AAL, Schaefer, Power264, Dosenbach, connectome
