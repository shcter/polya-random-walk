# Polya's Random Walk — 波利亚随机游走

> 基于波利亚遍历定理的 1D / 2D / 3D 随机游走交互式可视化

[波利亚遍历定理 (Polya's Random Walk Theorem)](https://en.wikipedia.org/wiki/Polya%27s_random_walk_theorem)：
- **一维 & 二维**：随机游走是**常返的**（必然返回原点）
- **三维**：随机游走是**瞬过的**（可能永不返回原点）

## 预览

直接用浏览器打开 `index.html` 即可运行，无需任何服务器或构建工具。

## 功能

- **1D 可视化**：水平线上的随机游走动画
- **2D 可视化**：Canvas 网格上的 2D 随机游走路径
- **3D 可视化**：Three.js 渲染的 3D 随机游走，支持鼠标拖拽旋转/滚轮缩放
- **颜色渐变**：轨迹颜色随步数从蓝渐变到红
- **实时统计**：步数、当前位置、原点访问状态、最大曼哈顿距离
- **速度控制**：可调节动画速度

## 使用方法

1. 打开 `index.html`
2. 选择维度 (1D / 2D / 3D)
3. 输入步数（1-50000）
4. 点击 **Start** 开始随机游走
5. 3D 模式下：鼠标拖拽旋转，滚轮缩放

## 技术栈

- 纯前端：HTML5 + CSS3 + JavaScript（无框架）
- 2D 渲染：HTML5 Canvas
- 3D 渲染：Three.js (r128, CDN)
- 字体：JetBrains Mono + Noto Sans SC (Google Fonts)

## 项目结构

```
polya-random-walk/
├── index.html   # 主程序（单文件，可直接运行）
├── SPEC.md      # 规格说明
└── README.md    # 本文件
```

## License

MIT
