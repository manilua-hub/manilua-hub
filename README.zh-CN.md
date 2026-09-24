<div align="center">

![ManiLuaHub — The Open Steam Manifest & Lua Ecosystem](og-home.png)

# 🌐 ManiLuaHub (`manilua-hub`)

**为 [ManiLuaHub.com](https://maniluahub.com) 提供支持的开源 Steam 清单与 Lua 脚本生态系统。**

[![Official Portal](https://img.shields.io/badge/Portal-maniluahub.com-6366f1?style=for-the-badge&logo=google-chrome&logoColor=white)](https://maniluahub.com/zh)
[![GitHub Organization](https://img.shields.io/badge/GitHub-@manilua--hub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/manilua-hub)
[![Catalog Size](https://img.shields.io/badge/Catalog-62%2C257%20Verified%20Branches-10b981?style=for-the-badge&logo=steam&logoColor=white)](https://maniluahub.com/zh/explore)
[![OpenAPI 3.0](https://img.shields.io/badge/API-Free%20%26%20Keyless-8b5cf6?style=for-the-badge&logo=openapi-initiative&logoColor=white)](https://maniluahub.com/zh/docs)
[![License](https://img.shields.io/badge/License-MIT-amber?style=for-the-badge)](LICENSE)

<p align="center">
  <a href="https://maniluahub.com/zh">🌐 <b>官方网页端</b></a> •
  <a href="https://github.com/manilua-hub/ManifestHub3">⚡ ManifestHub3 数据集</a> •
  <a href="https://maniluahub.com/zh/explore">🎮 62k 游戏清单</a> •
  <a href="https://maniluahub.com/zh/docs">🔌 OpenAPI 文档</a> •
  <a href="https://maniluahub.com/zh/how-to-use">📖 使用教程</a> •
  <a href="https://maniluahub.com/zh/download">💻 客户端中心</a> •
  <a href="https://maniluahub.com/zh/faq">❓ 常见问题</a>
</p>

<p align="center">
  <a href="README.md">English</a> • <b>简体中文</b>
</p>

</div>

---

> [!TIP]
> ### ⚡ 官方 Web 探索器现已上线！
> 
> 无需本地克隆 62,000+ 个 Git 分支，直接在网页端秒级检索、代码审查与一键打包下载：
> 
> 👉 **[立即体验 ManiLuaHub.com (进入网页端)](https://maniluahub.com/zh)**
> 
> - 🔍 **瞬时搜索**：支持游戏中文名、英文名及 Steam AppID 极速检索。
> - 👁️ **透明代码审计**：在线查看语法高亮的 Lua 清单蓝图与 Depot 解密密钥树。
> - 📦 **一键打包**：直接下载免配置的 `<AppID>.lua` 与 `key.vdf` ZIP 压缩包，解压即用。
> - 🔌 **免费 OpenAPI**：为机器人、社区工具及自动化脚本提供毫秒级 JSON 接口。

---

## 🧭 组织简介

**ManiLuaHub** 是一个开源的社区化数据服务平台，致力于为全球玩家与开发者整理、索引并提供超 **62,257+ 款 Steam 游戏与 DLC** 的标准清单配置、Lua 蓝图与开放接口服务。

我们的目标是让 Steam 清单数据的获取更加**透明、去中心化、可审计且极速响应**。

---

## 🏛️ 生态架构

ManiLuaHub 组织维护以下开源项目与服务：

| 仓库 / 服务 | 描述 | 技术栈 | 状态 |
| :--- | :--- | :--- | :--- |
| **[`manilua-hub/ManifestHub3`](https://github.com/manilua-hub/ManifestHub3)** | 采用 Branch-per-AppID 分支架构索引 62,257+ 款游戏的分布式清单库 | Git, VDF, Lua | 🟢 Active |
| **[`manilua-hub/maniluahub.com`](https://maniluahub.com)** | 高性能网页探索器，支持实时语法审查、Depot 分卷树与一键 ZIP 打包 | Next.js, React, Tailwind CSS | 🟢 Active |
| **[OpenAPI Edge Gateway](https://maniluahub.com/zh/docs)** | 全球边缘 API 路由，提供 35ms 超低延迟清单解析与流式下载 | Cloudflare Workers | 🟢 Active |
| **[`manilua-hub/manilua-hub`](https://github.com/manilua-hub/manilua-hub)** | 组织门户与生态文档中心 | Markdown | 🟢 Active |

---

## 💡 核心设计原则

- 🔒 **纯文本安全审计**：仅收录只读 `<AppID>.lua` 指令脚本与 `key.vdf` Valve 标准密钥描述文件，**绝对不包含任何二进制可执行文件或第三方注入器**。
- 🌿 **Branch-per-AppID 架构**：每个收录的 Steam 游戏分配独立 Git 分支（例如 `origin/730` 对应 CS2，`origin/2358720` 对应黑神话悟空），支持轻量按需检索。
- ⚡ **全球 Anycast 边缘加速**：基于 Cloudflare Workers 边缘节点分发，亚欧及北美地区均可秒级响应。
- 🔌 **开发者友好**：100% 开放、免 Key、免限制的 REST 规范接口。

---

## 🎮 兼容客户端

- **Watt Toolkit (Steam++ / Bimorphism)**
- **SteamTools**
- **GreenLuma**
- **SmokeAPI & Koaloader**
- **SteamOS / Steam Deck**
- **macOS Whisky & CrossOver**

---

## 🔌 开放接口快速上手

### 1. 查询游戏元数据
```bash
curl -s "https://maniluahub.com/api/v1/manifest/2358720" | jq .
```

### 2. 流式获取纯净 Lua 蓝图脚本
```bash
curl -s "https://maniluahub.com/api/files/2358720/lua" -o 2358720.lua
```

### 3. 一键下载完整 ZIP 压缩包
```bash
curl -s -O -J "https://maniluahub.com/api/files/2358720/zip"
```

---

<div align="center">

Made with ❤️ by the **ManiLuaHub Community** • **[maniluahub.com](https://maniluahub.com/zh)**

</div>
