# AI-Home-Care

AI 驱动的家属远程陪诊平台 — 让不在身边的家属，也能全程安心参与患者就医。

## 在线访问

> 🔗 **访问地址**：https://victoria0904.github.io/AI-Home-Care/

支持 **PC / iOS / Android / 鸿蒙(HarmonyOS)** 等主流系统直接打开，无需安装、无需登录。

## 鸿蒙系统适配

针对华为鸿蒙系统 WebView 的已知兼容性问题做了专项修复：

| 问题 | 修复方案 |
|------|----------|
| `scroll-snap` 渲染异常 | 鸿蒙下禁用 scroll-snap，改为自然滚动 |
| `transform: scale()` 缩放失效 | 增强版 `fit()` 函数，鸿蒙专用计算逻辑 |
| `innerWidth` 返回异常 | 多源取值 + fallback |
| 双指/双击缩放误触 | 禁用 gesture 事件 |
| 布局重排不触发 | 连续 5 次强制重排 + resize 事件 |
| 100vh 计算偏差 | 动态 `--vh` 变量 + `-webkit-fill-available` |
| 横向溢出错版 | `overflow-x: hidden` + `max-width: 100vw` |
| 安全区域遮挡 | `env(safe-area-inset-*)` 适配 |

## 多端适配

| 系统 | 展示方式 | 特殊处理 |
|------|----------|----------|
| **PC (Windows/Mac/Linux)** | 完整 7 页演示 | 滚轮/方向键/数字键翻页 |
| **iOS (Safari/Chrome)** | 缩放适配 | 100vh 修复 + 安全区域适配 |
| **Android (Chrome)** | 缩放适配 | 防 WebView 滚动卡顿 |
| **HarmonyOS (华为浏览器)** | 专项修复 | 重排机制 + UA 检测 + CSS 修复 |

## 技术实现

- 直接嵌入 Coze 发布页面，注入多端兼容补丁
- 零外部依赖，所有内容自包含
- GitHub Pages 静态托管
