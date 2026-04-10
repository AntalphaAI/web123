# web123 — Web3 Skill Navigator / Web3 技能导航站

> **"Web3 不会用，就上 web123"**
> **"New to Web3? Start with web123."**

一句话描述需求，AI 自动推荐最合适的 Web3 工具并给出安装命令。
Describe your need in plain language — get the right Web3 skill recommendation instantly.

---

## 🚀 Quick Start / 快速开始

```bash
# Install / 安装
openclaw skill install https://github.com/AntalphaAI/web123

# Then just talk to your AI agent / 然后直接跟 AI 说：
"我想交易代币"        → 推荐 web3-trader
"查我的钱包余额"      → 推荐 wallet-balance
"Web3 新手，怎么开始" → 推荐新手入门套装
"有哪些 Web3 技能"   → 展示全部 13 个 skill
```

---

## 📦 What's Inside / 收录内容

共收录 **13 个** AntalphaAI 官方 Skill，覆盖 5 大分类：
**13 official AntalphaAI Skills** across 5 categories:

| 分类 / Category | Skill | 一句话描述 / Description |
|----------------|-------|------------------------|
| 🔄 交易 Trading | `web3-trader` | DEX 聚合交易 + Hyperliquid 合约 / DEX swap + perpetuals |
| 🔄 交易 Trading | `poly-master` | Polymarket 预测市场 / Prediction market |
| 💰 投资 Invest | `antalpha-rwa` | RWA 链上理财 / RWA on-chain yield |
| 💰 投资 Invest | `web3-investor` | DeFi/NFT 投资组合管理 / DeFi portfolio |
| 📊 数据 Data | `wallet-balance` | 多链钱包余额 / Multi-chain balance |
| 📊 数据 Data | `transaction-receipt` | 链上交易解析 / On-chain tx decoder |
| 📊 数据 Data | `smart-money` | 聪明钱鲸鱼追踪 / Whale tracking |
| 📊 数据 Data | `defillama-data-aggregator` | DeFi TVL 数据 / DeFi TVL & yields |
| 🛡️ 安全 Safety | `wallet-guard` | 钱包高风险授权扫描 / Wallet approval scan |
| 🛡️ 安全 Safety | `meme-token-analyzer` | Meme 币财富基因检测 / Meme token analysis |
| 🛡️ 安全 Safety | `airdrop-hunter` | 空投情报日报 / Daily airdrop intel |
| 💳 支付 Payment | `eth-payment` | EIP-681 收款链接 / Payment link generator |
| 💳 支付 Payment | `walletconnect-requester` | WalletConnect 钱包连接 / Wallet connection |

---

## 🎒 Starter Packs / 新手套装

### 新手入门 / Web3 Beginner
```bash
openclaw skill install https://github.com/AntalphaAI/wallet-balance https://github.com/AntalphaAI/web3-trader https://github.com/AntalphaAI/transaction-receipt
```
查余额 + 交易代币 + 查交易记录 / Check balance + trade + verify tx

### 安全套装 / Safety Pack
```bash
openclaw skill install https://github.com/AntalphaAI/wallet-guard https://github.com/AntalphaAI/airdrop-hunter https://github.com/AntalphaAI/Meme-Token-Analyzer
```
钱包防护 + 空投猎手 + Meme 币分析 / Wallet guard + airdrop + meme analysis

### 交易套装 / Trading Pack
```bash
openclaw skill install https://github.com/AntalphaAI/web3-trader https://github.com/AntalphaAI/wallet-balance https://github.com/AntalphaAI/transaction-receipt
```

---

## 💡 How It Works / 工作原理

```
用户自然语言输入
User natural language input
        ↓
意图识别（新手/分类浏览/需求匹配/全览）
Intent detection
        ↓
标签权重匹配算法 (tags×3 + scenarios×2 + description×1)
Tag-weighted matching
        ↓
返回 Top 3 推荐 + 安装命令
Return Top 3 recommendations + install commands
```

---

## 📁 File Structure / 文件结构

```
web123/
├── README.md              ← 你在这里 / You are here
├── SKILL.md               ← AI Agent 执行规范 / Agent instruction file
└── references/
    └── skills.json        ← 13 个 skill 元数据 / Skill metadata
```

---

## 🔗 AntalphaAI GitHub

所有收录 skill 均来自：All skills sourced from:
👉 [github.com/AntalphaAI](https://github.com/AntalphaAI)

---

*Powered by Antalpha AI · web123 v1.2.0*
