# Best Designs · 设计师作品聚合 + Pin 风收藏

一个面向设计师的作品发现站，灵感来自 [bestdesignsonx.com](https://bestdesignsonx.com) 与 Pinterest。
单页 HTML 应用，零依赖、零构建、无后端，**双击 `index.html` 即可运行**。

数据来源：[bestdesignsonx](https://bestdesignsonx.com) 的公开 Supabase 接口（运营人工精选的 𝕏 设计帖）。

## 功能

- **极简作品流**：纯瀑布流网格，hover 才显示标签 / 收藏按钮
- **视频自动播放**：卡片视频进入视口时静音循环播放，离开自动暂停（省带宽）
- **沉浸式预览**：详情弹窗 1280px 宽，原生进度条可拖动 seek 视频
- **Pin 风收藏夹**：
  - 点心形 → 弹出收藏夹气泡 → 选/新建收藏夹即保存
  - 一个作品归属一个收藏夹（Pin Board 语义）
  - 默认"未分类"兜底，删除收藏夹时作品自动回退
  - 快速保存按钮（一键存到未分类）
- **数据持久化**：localStorage 本地存储，刷新不丢失
- **响应式**：桌面网格、移动端单列堆叠
- **键盘**：ESC 关闭弹窗

## 数据来源说明

本项目只用作技术演示，作品数据通过原站前端公开的 Supabase 匿名 key 只读获取。
图/视频走原站 CDN（`cdn.bestdesignsonx.com`）。
**请尊重原作者版权与原站运营成果。** 如需商用或大规模引用，请联系原站方。

## 如何运行

### 方式一：直接打开
```bash
open index.html
```

### 方式二：本地静态服务
```bash
# 任选其一
python3 -m http.server 5180
# 或
npx serve .
```
然后访问 http://localhost:5180

## 技术栈

- 纯 HTML + CSS + 原生 JavaScript（无框架、无构建）
- Supabase REST API（PostgREST）
- IntersectionObserver 控制视频懒播放
- localStorage 数据持久化

## 目录结构

```
best-designs/
├── index.html      # 全部代码都在这里
├── README.md
├── LICENSE
└── .gitignore
```

## 自定义

想接入自己的作品数据？修改 `index.html` 顶部的 `SB_URL` / `SB_KEY` / `fetchWorks` 即可，
或者把 `state.works` 替换成你自己的静态数据数组。

## License

MIT — 见 [LICENSE](./LICENSE)
