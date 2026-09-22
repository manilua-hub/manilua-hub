<div align="center">

![ManiLuaHub — The Open Steam Manifest & Lua Ecosystem](og-home.png)

# 🌐 ManiLuaHub (`manilua-hub`)

**The Open-Source Steam Manifest & Lua Script Ecosystem powering [ManiLuaHub.com](https://maniluahub.com).**

[![Official Portal](https://img.shields.io/badge/Portal-maniluahub.com-6366f1?style=for-the-badge&logo=google-chrome&logoColor=white)](https://maniluahub.com)
[![GitHub Organization](https://img.shields.io/badge/GitHub-@manilua--hub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/manilua-hub)
[![Catalog Size](https://img.shields.io/badge/Catalog-62%2C288%20Game%20Branches-10b981?style=for-the-badge&logo=steam&logoColor=white)](https://maniluahub.com/explore)
[![OpenAPI 3.0](https://img.shields.io/badge/API-Free%20%26%20Keyless-8b5cf6?style=for-the-badge&logo=openapi-initiative&logoColor=white)](https://maniluahub.com/docs)
[![License](https://img.shields.io/badge/License-MIT-amber?style=for-the-badge)](LICENSE)

<p align="center">
  <a href="https://maniluahub.com">🌐 Official Portal</a> •
  <a href="https://github.com/manilua-hub/ManifestHub3">⚡ ManifestHub3 Dataset</a> •
  <a href="https://maniluahub.com/explore">🎮 Manifest Catalog</a> •
  <a href="https://maniluahub.com/docs">🔌 OpenAPI Docs</a> •
  <a href="https://maniluahub.com/download">💻 Client Center</a> •
  <a href="https://maniluahub.com/faq">❓ FAQ</a>
</p>

</div>

---

## 🧭 About ManiLuaHub

**ManiLuaHub** is an open-source, community-driven platform dedicated to organizing, indexing, and serving Steam depot manifests, verified Lua automation blueprints, and developer-friendly data services for more than **62,000+ games and DLCs**.

Our goal is to make Steam manifest discovery **transparent, decentralized, auditable, and lightning-fast** for researchers, game archivists, and loader tool developers worldwide.

---

## 🏛️ Ecosystem Overview

The ManiLuaHub organization orchestrates several interconnected repositories and services:

| Repository / Service | Description | Tech Stack | Status |
| :--- | :--- | :--- | :--- |
| **[`manilua-hub/ManifestHub3`](https://github.com/manilua-hub/ManifestHub3)** | Decentralized Git storage indexing 62,000+ Steam titles via branch-per-AppID architecture | Git, VDF, Lua | 🟢 Active |
| **[`manilua-hub/maniluahub.com`](https://maniluahub.com)** | High-performance web portal with live syntax inspection, depot tree browser, and one-click ZIP packaging | Next.js, React, Tailwind CSS | 🟢 Active |
| **[OpenAPI Edge Gateway](https://maniluahub.com/docs)** | Global edge API resolving manifest branches and raw data streams under 35ms latency | Cloudflare Workers, Fastly CDN | 🟢 Active |
| **[`manilua-hub/maniluahub`](https://github.com/manilua-hub/maniluahub)** | Organization entry point, ecosystem documentation, community governance, and shared assets | Markdown, Community RFCs | 🟢 Active |

---

## 💡 Core Principles & Design

```text
               ┌────────────────────────────────────────────────────────┐
               │              ManiLuaHub Community & Web               │
               │   https://maniluahub.com  •  Edge Caching (Cloudflare) │
               └───────────────────────────┬────────────────────────────┘
                                           │
                        ┌──────────────────┴──────────────────┐
                        ▼                                     ▼
      ┌───────────────────────────────────┐ ┌───────────────────────────────────┐
      │   manilua-hub/ManifestHub3        │ │         OpenAPI Services          │
      │   Decentralized Git Registry      │ │   Public REST Endpoints           │
      │   62,000+ AppID Git Branches      │ │   Fastly CDN Global Stream        │
      └─────────────────┬─────────────────┘ └─────────────────┬─────────────────┘
                        │                                     │
                        └──────────────────┬──────────────────┘
                                           ▼
                 ┌─────────────────────────────────────────────────┐
                 │       Universal Client & Loader Ecosystem       │
                 │   Watt Toolkit • SteamTools • GreenLuma • Deck   │
                 │   SmokeAPI • Koaloader • Whisky (macOS)         │
                 └─────────────────────────────────────────────────┘
```

- 🔒 **Zero Binary Tampering**: We strictly store and serve human-readable `.lua` blueprints and standard `key.vdf` decryption descriptors. No third-party executables, binaries, or proprietary loaders are ever hosted.
- 🌿 **Branch-per-AppID Storage**: Every Steam game title is isolated into its own independent Git branch (e.g. `730` for *Counter-Strike 2*, `105600` for *Terraria*, `2358720` for *Black Myth: Wukong*), allowing lightweight, pinpoint fetching without multi-gigabyte repository clones.
- ⚡ **Sub-35ms Edge Resolution**: Multi-tiered edge caching powered by Cloudflare Workers and Fastly CDN ensures instant responses across North America, Europe, and the Asia-Pacific region.
- 🔌 **Developer-First Architecture**: 100% keyless, rate-limit-friendly REST APIs for community bots, CI/CD pipelines, and downloader clients.

---

## 🎮 Universal Client Compatibility

ManiLuaHub manifests and scripts are structured for native interoperability with leading Steam utility frameworks:

- **Watt Toolkit (Steam++ / Bimorphism)**
- **SteamTools**
- **GreenLuma** (via standard depot mapping)
- **SmokeAPI & Koaloader**
- **SteamOS / Steam Deck**
- **macOS Whisky & CrossOver**

---

## 🔌 Quick API Usage

Integrate ManiLuaHub data into your own CLI, Discord/Telegram bots, or utility scripts:

### 1. Search Game Catalog
```bash
curl -s "https://maniluahub.com/api/search?q=cyberpunk" | jq
```

### 2. Fetch Lua Blueprint
```bash
curl -s "https://maniluahub.com/api/files/1091500/lua" -o 1091500_public.lua
```

### 3. Download Full Manifest ZIP Bundle
```bash
curl -s -O -J "https://maniluahub.com/api/files/1091500/zip"
```

For full OpenAPI 3.0 Swagger specifications and interactive documentation, visit **[maniluahub.com/docs](https://maniluahub.com/docs)**.

---

## 🤝 Contributing & Community

We warmly welcome developers, curators, and gaming enthusiasts to collaborate with us:

- **Submit / Update a Manifest**: Check out the [Contribution Guide](https://github.com/manilua-hub/ManifestHub3/blob/main/CONTRIBUTING.md) to submit a PR with updated AppID branches.
- **Report Outdated Keys**: Open an issue on [ManifestHub3 Issues](https://github.com/manilua-hub/ManifestHub3/issues) with the affected AppID and depot details.
- **Feature Requests & Suggestions**: Feel free to initiate discussions or contribute to the web frontend and API layers.

---

## 📜 Legal & Disclaimer

- **Open-Source License**: All documentation, code, and script registries are distributed under the [MIT License](LICENSE).
- **Trademark Notice**: *Steam*, *SteamOS*, and the *Steam logo* are registered trademarks of **Valve Corporation**. ManiLuaHub is an independent open-source project and is neither affiliated with, endorsed by, nor sponsored by Valve Corporation.

---

<div align="center">

Made with ❤️ by the **ManiLuaHub Community** • [maniluahub.com](https://maniluahub.com)

</div>
