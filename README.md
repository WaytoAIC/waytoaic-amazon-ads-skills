# waytoaic-amazon-ads-skills

## Way to AIC | 通往AI电商之路

Fixed README prefix for Way to AIC repositories.

- 官网 / Website: [waytoaic.com](https://waytoaic.com) | [www.waytoaic.com](https://www.waytoaic.com)
- 社群招募 / Community: `Way to AIC社群招募 | WaytoAIC.com`
- 公众号 / WeChat Official Account: `维正 WaytoAIC`
- 知识星球 / Xiaozhixing: `AI电商之路 WaytoAIC`
- AIC = `AI Commerce`

在 AI 重塑商业的时代，我们希望和每一个拥抱 AI 的卖家，找到场景，定义问题，积累能力，设计系统，共同通往 AI 电商之路。

Way to AIC 不是教学，不是工具，而是一条所有电商人共同走的进化之路。

后续 Way to AIC 相关 GitHub 项目，默认都应在 README 顶部保留这一前缀区块。

### WaytoAIC 理念 | Principles

| 中文 | English |
|---|---|
| 场景先于方法 | Context before method |
| AI 的价值来自真实业务场景，而不是技术本身。 | AI creates value through real business contexts, not through technology alone. |
| 问题先于答案 | Problem before answer |
| 定义问题，比拥有工具更重要。 | Defining the problem matters more than collecting tools. |
| 系统胜过技巧 | System over tricks |
| 技巧是术，系统才是道，决定卖家的上限。 | Tricks are tactical; systems define long-term leverage and ceiling. |
| 共创优于独行 | Co-creation over solo progress |
| 我们相信，真正的进化发生在共同探索的过程中。 | Real evolution happens through shared exploration. |

---

中文 | [English](#english)

## Quick Install

```bash
# Codex
curl -fsSL https://raw.githubusercontent.com/WaytoAIC/waytoaic-amazon-ads-skills/v1.0.1/install.sh | bash -s -- --target codex --ref v1.0.1
```

```bash
# OpenClaw
curl -fsSL https://raw.githubusercontent.com/WaytoAIC/waytoaic-amazon-ads-skills/v1.0.1/install.sh | bash -s -- --target openclaw --ref v1.0.1
```

```bash
# Custom skills root
curl -fsSL https://raw.githubusercontent.com/WaytoAIC/waytoaic-amazon-ads-skills/v1.0.1/install.sh | bash -s -- --dest "$(pwd)/skills" --ref v1.0.1
```

安装脚本会把 `shared/` 和全部 `waytoaic-ads-*` skill 目录直接安装到目标 `skills` 根目录，而不是再额外套一层仓库目录。

---

一套把亚马逊广告分析方法拆成可复用技能包的 skill suite，覆盖路由、关键词地图、起盘测试、报表诊断、广告位控制、放缩量、变体策略、利润/TACOS 和季节节奏。

这套 skill 的边界很明确：

- 能做：拉取 MCP 数据、解析广告报表、计算指标、形成动作建议
- 不能做：直接改 Amazon Ads 后台
- 所有调价、调预算、否词、暂停、建活动类动作都只会输出建议，并标记 `approval_required=true`

## 中文

### 包含的 skill

| Skill | 作用 |
|---|---|
| `waytoaic-ads-ad-router` | 入口 skill，按问题类型路由到 1-3 个专用 skill |
| `waytoaic-ads-keyword-map` | 准流量词表、全流量词表、否词池、词根分层、词角色分类 |
| `waytoaic-ads-launch-test-planner` | 新品或放量前的基准竞价测试结构 |
| `waytoaic-ads-ad-report-diagnosis` | Search Term / Targeting / Placement / Advertised Product 等报表诊断 |
| `waytoaic-ads-bid-placement-control` | TOS / ROS / PP 广告位与竞价控制建议 |
| `waytoaic-ads-scale-shrink-planner` | 放量、稳盘、缩量动作规划 |
| `waytoaic-ads-variant-strategy` | 父子体角色分工与测款/主推逻辑 |
| `waytoaic-ads-profit-tacos-planner` | CPA / ACOS / TACOS / 广告单占比 / 利润倒推 |
| `waytoaic-ads-seasonality-planner` | A-B-C-D-E 季节节奏与旺季/淡季动作规划 |
| `shared/waytoaic-ads-operating-boundaries.md` | 全套 skill 共享边界、数据归属、输出格式约束 |

### 数据边界

| 数据类型 | 主来源 |
|---|---|
| 关键词需求、历史、竞争、ASIN 关键词信号、广告结构、流量诊断 | `SIF MCP` |
| SPR、ASIN 基础信息、变体、价格、coupon、评分、Google Trend | `SellerSprite MCP` |
| 花费、点击、订单、销售额、广告位分布、Search Term 实绩 | `Amazon Ads 原始报表` |
| 市场/产品补充验证 | `Sorftime MCP` 可选 |

如果 SIF 或其他 MCP 能力在当前会话里未暴露，这套 skill 会明确写 `capability not available` 或 `证据不足`，不会静默换源。

### 适合的使用方式

直接在 Codex 里说：

- `按照 WaytoAIC-Ads Ad Router 分析这个 ASIN`
- `给我做一套新品基准竞价测试结构`
- `用 Placement Report 看一下 TOS / ROS / PP 怎么调`
- `结合 SIF 和 SellerSprite 做关键词地图`
- `做父子体广告角色分工`

### 仓库结构

```text
shared/
waytoaic-ads-ad-router/
waytoaic-ads-keyword-map/
waytoaic-ads-launch-test-planner/
waytoaic-ads-ad-report-diagnosis/
waytoaic-ads-bid-placement-control/
waytoaic-ads-scale-shrink-planner/
waytoaic-ads-variant-strategy/
waytoaic-ads-profit-tacos-planner/
waytoaic-ads-seasonality-planner/
```

### 许可说明

- 当前仓库公开可见，可学习、可安装、可二次研究
- 默认不允许商用
- 如果你基于这套 skill 做了再分发的功能或产品，需要公开对应源码并保留原始署名

---

## English

This repository packages an Amazon Ads skill suite for operator-facing analysis and planning.

It covers:

- routing ad requests to the right specialist skill
- keyword map creation
- launch and baseline bid testing
- ad report diagnosis
- bid and placement control
- scale / stabilize / shrink planning
- variation strategy
- profit and TACOS planning
- seasonality planning

### Key operating boundary

These skills can gather MCP data, parse reports, calculate metrics, and draft action plans, but they do not modify Amazon Ads backend state. Any bid, budget, negative, pause, or campaign-creation action is recommendation-only and should be marked with `approval_required=true`.

### Install behavior

`install.sh` installs `shared/` and every `waytoaic-ads-*` directory directly into the target skills root so the existing relative references keep working.

### Primary use cases

- analyze an ASIN with the router skill
- build a launch-test structure before scale
- diagnose Search Term / Targeting / Placement exports
- produce scale or shrink plans
- assign traffic roles across parent-child variations

### Notes

- SIF is the primary source for keyword demand, competition, ASIN keyword signals, ad structure, and traffic diagnosis.
- SellerSprite supplements ASIN fundamentals, variation data, and external trend signals.
- Amazon Ads exports remain the source of truth for spend, clicks, orders, sales, and placement distribution.
