[English](https://github.com/Anan-up/Windows-Blue-Screen-Update-Webpage/blob/main/README.md) | [简中](https://github.com/Anan-up/Windows-Blue-Screen-Update-Webpage/blob/main/README_Simplified_Chinese.md) | [文言](https://github.com/Anan-up/Windows-Blue-Screen-Update-Webpage/blob/main/README_Classical_Chinese.md)

## 文件概况

**`win-screens.html`**（约 17KB，单文件，无任何外部依赖）是一个 **Windows 蓝屏/系统更新界面模拟器**。纯 HTML + CSS + 原生 JavaScript 实现，打开即用，全屏沉浸式展示 6 个高还原度的系统界面。

## 功能架构：3×2 界面矩阵

| 系统版本 | 蓝屏界面 | 更新界面 |
|---|---|---|
| **Windows 7** | 经典文本模式蓝屏，报错 `DRIVER_IRQL_NOT_LESS_OR_EQUAL`，附带 STOP 代码 `0x000000D1` 和 `nvlddmkm.sys` 驱动崩溃信息，含完整内存转储流程文本 | 黑色"正在配置 Windows 更新"界面，蓝色渐变进度条 + "请勿关闭计算机" |
| **Windows 10** | 现代 `:(` 风格蓝屏，SVG 手绘二维码，停止代码 `CRITICAL_PROCESS_DIED`，Bing 查询链接 | 深色界面 + 圆形进度环（SVG stroke-dashoffset 动画） |
| **Windows 11** | 更简洁的 `:(` 蓝屏（`#0067c0` 更深的蓝，留白更多），二维码 + support.microsoft.com 链接 | 圆形进度环 + "正在处理更新 X%" |

## 交互设计

- **HUD 悬浮面板**（右上角，毛玻璃效果）：实时显示当前位置（如"Windows 10 · 蓝屏"），内含 3×2 网格按钮（`1B/1U/2B/2U…`）可直接点击跳转
- **键盘快捷键**：`↑↓` 切换系统版本、`←→` 切换界面类型、`H` 隐藏/显示 HUD
- **动画模拟**：三套独立进度动画（Win7 进度条、蓝屏"收集信息百分比"、圆形更新进度环），用 `Math.random()` 模拟不规律的进度变化，营造"真实感"

## 技术亮点

1. **高度还原细节**：Win7 蓝屏用等宽字体 + `white-space: pre-wrap` 还原文本排版；Win10/11 蓝屏颜色、表情符号、右下角白色二维码（SVG path 绘制）均还原真实系统
2. **响应式设计**：全屏字号用 `clamp()` 自适应，布局用 vw/vh 单位，任何分辨率下都完整呈现
3. **无依赖零构建**：一个文件直接浏览器打开即可运行，适合演示/恶搞/前端练习场景

## 项目截图

![项目截图](project_screenshot.png)
