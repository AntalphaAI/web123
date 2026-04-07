---
name: web123
version: 1.1.0
description: Web3 技能导航站。"Web3 不会用，就上 web123"。通过自然语言描述需求，自动推荐匹配的 AntalphaAI Skill，并提供安装命令。触发词：web123、推荐技能、我想交易代币、查余额、Web3 新手、投资理财、聪明钱追踪、空投、meme币分析、收款链接、Web3 技能有哪些
author: Antalpha AI
---

# web123 — Web3 技能导航站

> **"Web3 不会用，就上 web123"**
> AntalphaAI 官方产品矩阵导航，帮你找到最适合的工具

---

## 数据来源

所有 skill 元数据存储在 `references/skills.json`，仅收录 AntalphaAI GitHub org 真实发布的 13 个仓库。

**收录清单：**
- `web3-trader` — DEX 交易 + Hyperliquid 合约
- `poly-master` — Polymarket 预测市场
- `defillama-data-aggregator` — DeFi TVL 数据
- `wallet-balance` — 多链钱包余额
- `meme-token-analyzer` — Meme 币财富基因分析
- `airdrop-hunter` — 空投情报
- `wallet-guard` — 钱包安全防护
- `web3-investor` — DeFi/NFT 投资基础设施
- `antalpha-rwa-skill` — RWA 链上理财
- `eth-payment` — 收款链接生成
- `smart-money` — 聪明钱鲸鱼追踪
- `walletconnect-requester` — WalletConnect 钱包连接
- `transaction-receipt` — 链上交易解析

---

## 触发条件

以下任意情况触发本 skill：

- 用户提到 `web123`
- 用户用自然语言描述 Web3 需求（如"我想交易代币"、"查钱包余额"）
- 用户说"Web3 新手"、"新手入门"、"推荐技能"
- 用户询问"有什么 Web3 工具"、"AntalphaAI 有哪些 skill"
- 用户按分类浏览（如"安全类的 skill"、"交易类工具"）

---

## 推荐算法（MVP）

### 权重计算

```
tags 匹配      → 权重 +3（每个匹配词）
scenarios 匹配 → 权重 +2（每个匹配词）
description 匹配 → 权重 +1（每个匹配词）
新手包关键词   → 额外 +5（检测到"新手"、"入门"、"starter"）
```

### 匹配步骤

1. 将用户输入分词（去停用词）
2. 遍历 skills.json 中所有 skill，计算匹配权重
3. 按权重 + priority 排序，返回 Top 3
4. 如有新手包关键词，返回对应套装而非单个 skill

### 边界处理

- **无匹配**（权重均为 0）→ 返回 `hot_skills` 热门推荐 Top 3
- **匹配 >3 个**→ 按权重 × priority 乘积排序，取 Top 3
- **"新手入门"类请求**→ 优先返回新手入门套装
- **分类浏览请求**→ 列出该分类下所有 skill

---

## 执行流程

### Step 1：加载数据

读取 `references/skills.json`（相对于 SKILL.md 目录）

### Step 2：意图识别

| 意图 | 示例 | 处理方式 |
|------|------|----------|
| 需求匹配 | "我想交易代币" | 关键词匹配算法 → Top 3 |
| 新手入门 | "Web3 新手"、"新手入门" | 直接返回新手入门套装 |
| 分类浏览 | "安全类的 skill" | 列出该分类所有 skill |
| 精确查找 | "web3-trader 怎么安装" | 直接返回该 skill 详情 |
| 全览 | "有哪些 skill"、"产品矩阵" | 列出所有分类和 skill 概览 |

### Step 3：生成推荐结果

按下方模板格式输出。

---

## 输出模板

### 单个 Skill 推荐卡片

```
🎯 推荐技能：{name}
📝 功能：{description}
💡 使用场景：
- {example_1}
- {example_2}
📦 安装：{install}
🔗 GitHub：{github}
```

### Top 3 推荐列表

```
🔍 根据你的需求，为你推荐以下技能：

━━━━━━━━━━━━━━━━━━━
🥇 {name_1} — {description_1}
   💡 {scenario_1}
   📦 {install_1}

🥈 {name_2} — {description_2}
   💡 {scenario_2}
   📦 {install_2}

🥉 {name_3} — {description_3}
   💡 {scenario_3}
   📦 {install_3}
━━━━━━━━━━━━━━━━━━━
💡 批量安装：clawhub install {name_1} {name_2} {name_3}
```

### 新手套装推荐

```
🎒 {pack_label}
{pack_description}

包含 {count} 个必备技能：
- {skill_name_1} — {description_1}
- {skill_name_2} — {description_2}
- {skill_name_3} — {description_3}

一键安装：
{install_command}
```

### 全景产品矩阵

```
🌐 AntalphaAI Skill 全家桶（共 13 个）

🔄 交易
  • web3-trader — DEX 聚合交易 + Hyperliquid 合约
  • poly-master — Polymarket 预测市场投注与跟单

💰 投资
  • antalpha-rwa — RWA 链上理财，BTC 超额抵押
  • web3-investor — DeFi/NFT 投资机会发现与执行

📊 数据
  • wallet-balance — 多链钱包余额查询
  • transaction-receipt — 链上交易解析
  • smart-money — 聪明钱鲸鱼追踪与信号
  • defillama-data-aggregator — DeFi TVL 与协议数据

🛡️ 安全
  • wallet-guard — 钱包高风险授权扫描
  • meme-token-analyzer — Meme 币财富基因检测
  • airdrop-hunter — 空投情报 S/A/B 评级日报

💳 支付
  • eth-payment — EIP-681 收款链接 + 二维码
  • walletconnect-requester — WalletConnect v2 钱包连接

💬 告诉我你想做什么，我来帮你推荐！
```

---

## 验收标准速查

| 用户说 | 返回结果 |
|--------|----------|
| "我想交易代币" | 推荐 web3-trader |
| "查钱包余额" | 推荐 wallet-balance |
| "投资 RWA 产品" | 推荐 antalpha-rwa |
| "聪明钱在买什么" | 推荐 smart-money |
| "检测 rug pull" | 推荐 wallet-guard + meme-token-analyzer |
| "空投任务" | 推荐 airdrop-hunter |
| "帮我生成收款链接" | 推荐 eth-payment |
| "Web3 新手入门" | 返回新手入门套装 |
| "有哪些安全工具" | 列出安全分类所有 skill |
| "有哪些 skill" | 返回全景产品矩阵 |
| 无法匹配 | 返回热门 Top 3 |

---

## 安装命令说明

```bash
# 安装单个 skill
clawhub install web3-trader

# 批量安装（新手包）
clawhub install wallet-balance web3-trader transaction-receipt
```

---

*Powered by Antalpha AI | web123 v1.1.0 | 数据源：github.com/AntalphaAI*
