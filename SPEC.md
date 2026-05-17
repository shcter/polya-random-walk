# Polya's Random Walk — SPEC

## 1. Project Overview

**Name**: Polya's Random Walk (波利亚随机游走)
**Type**: Interactive visualization / educational demo
**Summary**: 基于波利亚遍历定理的随机游走演示，用户输入步数后，在1D/2D/3D空间中可视化随机游走路径。
**Target Users**: 数学爱好者、学生、教学演示

---

## 2. Theorem Background

**波利亚遍历定理 (Polya's Random Walk Theorem)**:
- 一维随机游走：**常返的** — 必然返回原点
- 二维随机游走：**常返的** — 必然返回原点  
- 三维随机游走：**瞬过的** — 可能永远不返回原点

---

## 3. Visual & Rendering Specification

### Scene Setup
- **1D**: 水平线动画，点在线上左右随机移动
- **2D**: 2D Canvas网格，点的随机游走路径绘制
- **3D**: Three.js 3D网格，轨迹线 + 散点

### Camera & Controls
- 1D: 固定视角
- 2D: 固定正交视角，拖拽平移
- 3D: OrbitControls 旋转/缩放

### Lighting & Environment
- 暗色主题背景 (#0a0a0f)
- 网格线: 细线框风格
- 轨迹: 渐变色发光效果

### Materials & Effects
- 轨迹线: 颜色随步数渐变 (蓝→青→绿→黄→红)
- 当前位置: 发光球体
- 原点: 特殊标记 (金色)
- 已访问点: 淡化显示

### Color Palette
- Background: #0a0a0f (deep dark)
- Grid lines: #1a1a2e (subtle blue-gray)
- Origin marker: #ffd700 (gold)
- Current position: #ff6b6b (coral red)
- Trail gradient: #4facfe → #00f2fe → #43e97b → #f6d365 → #ff6b6b

---

## 4. Simulation Specification

### Random Walk Algorithm
- 每步在每个维度上随机选择 ±1
- 1D: `x += random.choice([-1, 1])`
- 2D: `x += random.choice([-1, 1]), y += random.choice([-1, 1])`
- 3D: `x += random.choice([-1, 1]), y += random.choice([-1, 1]), z += random.choice([-1, 1])`

### Animation
- 步进模式: 逐步动画 (可调速度 10ms-500ms/步)
- 或直接渲染模式 (输入N，直接显示N步结果)
- 默认: 直接渲染 + 可重播动画

### Statistics Display
- 当前坐标
- 步数
- 是否返回过原点 (仅2D/3D)
- 总曼哈顿距离

---

## 5. Interaction Specification

### Controls
- **步数输入**: 正整数输入框 (1-10000)
- **维度切换**: 三个Tab按钮 (1D / 2D / 3D)
- **开始按钮**: 执行随机游走
- **重置按钮**: 清除当前路径
- **速度滑块**: 动画速度 (仅动画模式)

### UI Layout
```
┌─────────────────────────────────┐
│  Polya's Random Walk (波利亚随机游走)  │
├─────────────────────────────────┤
│  [1D] [2D] [3D]                 │
│  ┌───────────────────────────┐  │
│  │                           │  │
│  │     Canvas / WebGL       │  │
│  │                           │  │
│  └───────────────────────────┘  │
│  Step: 0/1000  |  Position: (0,0)│
│  [Start] [Reset] [Speed: ████]  │
└─────────────────────────────────┘
```

### Font
- 标题: JetBrains Mono 或 monospace
- 正文: system-ui

---

## 6. Acceptance Criteria

1. ✅ 输入正整数N，程序在对应维度执行N步随机游走
2. ✅ 1D模式: 水平线上显示点的移动轨迹
3. ✅ 2D模式: 网格上显示2D随机游走路径
4. ✅ 3D模式: Three.js渲染3D随机游走，可旋转缩放
5. ✅ 颜色渐变显示轨迹历史
6. ✅ 显示原点标记和当前位置
7. ✅ 实时显示统计信息 (步数、坐标、是否返回原点)
8. ✅ 响应式设计，支持不同屏幕尺寸
9. ✅ 代码上传至GitHub

---

## 7. Tech Stack

- **纯前端**: HTML5 + CSS3 + JavaScript
- **2D渲染**: HTML5 Canvas
- **3D渲染**: Three.js (CDN)
- **无构建工具**: 单HTML文件可直接运行

---

## 8. File Structure

```
polya-random-walk/
├── SPEC.md
├── index.html      # 主程序 (单文件)
└── README.md       # 项目说明
```
