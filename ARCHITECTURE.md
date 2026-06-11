# Agions Profile Architecture

> **版本**: v1.0 · **项目**: [Agions/Agions](https://github.com/Agions/Agions) · **类型**: GitHub Profile README

---

## 1. 概述

本项目是 **GitHub Profile 展示型仓库**，通过 README.md + 自定义 SVG 资产 + CI 自动化管线，构建自维护的开发者个人主页。

**核心目标：**
- **零手动维护** — CI 自动验证、自动修复、自动更新
- **高故障透明度** — 任何异常在 CI 中可见，不进生产
- **可组合可扩展** — 以 section marker 驱动的模块化内容编排

---

## 2. 分层架构

```
┌─────────────────────────────────────────────────────┐
│                   DevX Layer                         │
│        devcontainer · prettier · docs                │
└──────────────────────┬──────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────┐
│                 Content Layer (README.md)             │
│  ┌──────┬──────┬──────────┬──────┬─────┬──────┬────┐ │
│  │Banner│About │ Projects │ Tech│Game │Activ.│Foot│ │
│  └──────┴──────┴──────────┴──────┴─────┴──────┴────┘ │
│  Section markers: <!-- section:{name} -->             │
└──────────────────────┬──────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────┐
│                  Asset Layer (assets/)                │
│  banner.svg · profile-card.svg · runner-game.svg     │
│  wechat-qrcode.png · output/snake.svg (generated)    │
└──────────────────────┬──────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────┐
│             Pipeline Layer (GitHub Actions)           │
│  ┌────────┬────────┬──────┬──────┬──────┬─────────┐ │
│  │generate│ verify │check │check │check │  format │ │
│  │ -snake │ -readme│-badge│ -svg │-links│ -check  │ │
│  └────────┴────────┴──────┴──────┴──────┴─────────┘ │
│  Schedule: 0 */12 * * *  ·  workflow_dispatch        │
└─────────────────────────────────────────────────────┘
```

### 2.1 Content Layer — 内容层

基于 HTML 注释标记的模块化 README 编排：

| Section | 标记 | 内容 |
|---------|------|------|
| Banner | `<!-- section:banner -->` | Hero SVG + GitHub/Email 按钮 + Profile Views |
| About | `<!-- section:about -->` | 自我介绍 + Profile Card SVG |
| Projects | `<!-- section:projects -->` | 4 个项目卡片（scene-fab, story-fab, frame-fab, CaptionFab） |
| Tech Stack | `<!-- section:tech-stack -->` | 技术栈分类表 + shields.io badges |
| Game | `<!-- section:game -->` | 开发者跑酷 SVG 动画 |
| Activity | `<!-- section:activity -->` | 贡献图 + snake 动画 + 统计 badges |
| Contact | `<!-- section:contact -->` | 微信二维码 |
| Footer | `<!-- section:footer -->` | 署名信息 |

**设计原则：** 每个 section 使用 `<!-- section:{name} -->` / `<!-- end:{name} -->` 包裹，CI 可逐个独立验证，未来可拆分为独立模板文件。

### 2.2 Asset Layer — 资产层

| 资产 | 类型 | 尺寸 | 生成方式 | 用途 |
|------|------|------|----------|------|
| `banner.svg` | 矢量 | 900×200 | 手写 | Profile 首屏 Hero |
| `profile-card.svg` | 矢量 | ~300px | 手写 | About 区头像卡片 |
| `runner-game.svg` | 矢量 | 全宽 | 手写 | Game 区互动动画 |
| `wechat-qrcode.png` | 位图 | 120px | 外部生成 | 联系方式 |
| `output/snake.svg` | 矢量 | 动态 | CI 自动生成 (Platane/snk) | 贡献蛇动画 |

### 2.3 Pipeline Layer — 流水线层

单一 workflow (`update-profile.yml`)，6 个并行 job：

```
           ┌─────────────────┐
           │  Schedule/Dispatch │
           └────────┬────────┘
                    │
           ┌────────▼────────┐
           │ generate-snake   │ ← Platane/snk 生成贡献蛇
           └────────┬────────┘
                    │
    ┌───────────────┼───────────────┐
    │               │               │
┌───▼──────┐  ┌────▼────┐  ┌──────▼─────┐
│verify-   │  │check-   │  │check-      │
│readme    │  │badges   │  │svg         │
└───┬──────┘  └────┬────┘  └──────┬─────┘
    │               │               │
┌───▼──────┐  ┌────▼────┐         │
│check-    │  │format-  │         │
│links     │  │check    │         │
└───┬──────┘  └────┬────┘         │
    │               │               │
    └───────────────┼───────────────┘
                    │
           ┌────────▼────────┐
           │ All Must Pass ✓ │
           └─────────────────┘
```

#### Job 职责矩阵

| Job | 验证内容 | 失败影响 | 修复策略 |
|-----|---------|---------|---------|
| `generate-snake` | 生成贡献蛇 SVG | snake 不更新、无 visual 影响 | 自动提交 |
| `verify-readme` | 8 个 section marker + 4 个项目名 + snake 引用 | ❌ 阻断 | snake 自动修复 |
| `check-badges` | 27 个 shields.io 链接可达性 | ❌ 阻断 | 3 次重试 + 2s backoff |
| `check-svg` | SVG header + closing tag + 文件大小 | ❌ 阻断 | 手动修复 |
| `check-links` | 5 个项目 URL (200/301) + README 大小 | ❌ 阻断 | 手动修复 |
| `format-check` | prettier 格式化一致性 | ⚠️ 非阻断 | 手动修复 |

### 2.4 DevX Layer — 开发体验层

| 工具 | 路径 | 目的 |
|------|------|------|
| DevContainer | `.devcontainer/devcontainer.json` | 开箱即用的开发环境 |
| Prettier | `.prettierrc` | 统一的代码格式化 |
| Architecture Doc | `docs/architecture-overview.html` | 可视化架构建档 |
| This file | `ARCHITECTURE.md` | 文字架构建档 |

---

## 3. 数据流

```
GitHub API
    │
    ▼
Platane/snk ──► output/snake.svg ──► README.md (Activity section)
    │
    ▼
shields.io ──► 27 badges ──► README.md (all sections)
    │
    ▼
GitHub Profile ──► renders README.md ──► Visitor's browser
```

**关键数据流：**
1. **贡献数据** → GitHub API → Platane/snk → snake.svg → README
2. **项目元数据** → shields.io 动态生成 badges（stars, forks, license）
3. **活动数据** → github-readme-activity-graph → 贡献图表
4. **Profile PV** → komarev.com → PV counter badge

---

## 4. 安全与可靠性

### 4.1 验证策略
- **入口验证** — 所有 badge 链接在 CI 中通过 curl 验证可达性
- **结构性验证** — SVG 文件必须包含有效的 `<svg>` 头 + `</svg>` 闭合
- **引用完整性** — README 中引用的每个项目名必须实际存在于文档中
- **URL 可达性** — 所有项目 GitHub 链接返回 200/301

### 4.2 故障恢复
- **网络抖动** — badge 检查 3 次重试 + 2s backoff
- **内容漂移** — snake 引用丢失时 CI 自动修复并提交
- **运行时保护** — workflow timeout: 3-10 min/job，避免资源泄漏

---

## 5. 演进路线图

### P0 — 当前状态（已完成）
- ✅ 基础 README 内容编排
- ✅ 自定义 SVG 资产
- ✅ 6 重 CI 验证管线
- ✅ Retry 机制的 badge 验证

### P1 — 短期改善
- [ ] README section 模板化 — 将每个 section 拆为独立 `.md` 文件，构建时合并
- [ ] SVG 生成流水线 — 用 CI 动态生成带有实时 star 数据的 banner/profile-card
- [ ] 项目数据外部化 — 从 JSON/TOML 文件读取项目元数据，CI 渲染到 README

### P2 — 中期蓝图
- [ ] 数据源层 — 引入 GitHub API token 获取实时 star/forks 数据
- [ ] 多 profile 模板 — 支持暗/亮模式变体
- [ ] 贡献图快照 — 本地缓存 activity-graph，减少外部依赖

### P3 — 远期愿景
- [ ] 可插拔 section registry — section 可独立启用/禁用/排序
- [ ] 本地 CLI 工具 — `agions-profile build/test/deploy`
- [ ] 分布式的 profile 渲染管线（webhook 触发，CDN 缓存）

---

## 6. 技术决策记录（ADR）

### ADR-001: 单文件 README vs 模板引擎
- **决策**：单文件 README.md + HTML section markers
- **理由**：避免构建工具链依赖，GitHub 原生渲染无额外开销
- **代价**：不支持 conditonal rendering，内容冗余

### ADR-002: Schedule-based vs Event-triggered CI
- **决策**：定时（12h）+ 手动触发
- **理由**：profile 内容是低频变化，事件触发收益低
- **代价**：新数据最多延迟 12h 展示

### ADR-003: shields.io badges vs 本地计算
- **决策**：使用 shields.io 动态 badges
- **理由**：零维护、实时数据、无自建服务
- **代价**：网络依赖，偶尔超时（已用重试缓解）

---

## 7. 模块接口

```
Agions/Agions
├── README.md              ← 内容入口，section 边界标记
├── assets/
│   ├── banner.svg         ← Hero 区域
│   ├── profile-card.svg   ← 个人卡片
│   └── runner-game.svg    ← 跑酷动画
├── output/
│   └── snake.svg          ← CI 生成
├── docs/
│   └── architecture-overview.html  ← 架构可视化
├── .github/workflows/
│   └── update-profile.yml ← 自动化管线
├── .devcontainer/
│   └── devcontainer.json  ← 开发环境
├── .prettierrc            ← 格式化配置
├── ARCHITECTURE.md        ← 本文档
└── ...
```

---

*此文档由架构师（和一杯咖啡 ☕）于 2026-06-11 共同起草。*
