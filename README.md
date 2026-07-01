# TW Price Compare — 台灣購物網站比價

[![Hermes Agent](https://img.shields.io/badge/Hermes-Agent-6366f1)](https://hermes-agent.nousresearch.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![npx skills](https://img.shields.io/badge/npx%20skills-add-blue)](https://github.com/vercel-labs/skills)

Anthropic SKILL.md 標準格式的台灣購物比價技能，支援 **Hermes Agent**、**Claude Code**、**Codex CLI** 等相容平台。

## 功能

- 🔍 一次搜尋 **Feebee（飛比）** + **FindPrice（找找）** 兩個比價聚合站
- 🏪 覆蓋 momo、PChome、蝦皮、Yahoo購物中心、樂天、酷澎等數百家電商
- 📊 產出結構化價格比較表（Markdown / JSON）
- ⚡ 支援價格過濾、商店過濾、單站查詢

## 安裝

### Hermes Agent

**方法一：Tap（推薦）— 加一次永久可用**
```bash
hermes skills tap add derekhsu/tw-price-compare
hermes skills search tw-price-compare
hermes skills install tw-price-compare
```

**方法二：直接安裝**
```bash
hermes skills install https://github.com/derekhsu/tw-price-compare
```

### Claude Code / Codex CLI / 其他 SKILL.md 相容平台

```bash
# Vercel Skills CLI（最通用）
npx skills add https://github.com/derekhsu/tw-price-compare

# Anthropic Claude Code 外掛市場
/plugin marketplace add https://github.com/derekhsu/tw-price-compare
```

或手動下載 `SKILL.md` 放入平台對應的 skills 目錄。

## 使用

### Agent 模式

直接對 AI 助理說：

```
比價 iPhone 16 Pro
PS5 主機 哪邊買最便宜？
RTX 5090 價格比較
比價 Dyson V15
```

### 獨立腳本

```bash
python3 scripts/tw-price-compare.py "RTX 5090"
python3 scripts/tw-price-compare.py --max-price 30000 "PS5 主機"
python3 scripts/tw-price-compare.py --store 蝦皮 "Dyson V15"
python3 scripts/tw-price-compare.py --json --no-findprice "MacBook Air"
```

## 檔案結構

```
tw-price-compare/
├── SKILL.md                          # 技能主檔案（SKILL.md 標準格式）
├── README.md                         # 本文件
├── package.json                      # npm 套件資訊（npx skills 用）
└── scripts/
    └── tw-price-compare.py           # 獨立比價腳本
```

## 資料來源

| 站點 | 網址 | 覆蓋通路 |
|------|------|---------|
| **Feebee（飛比）** | https://feebee.com.tw | 400+ 台灣電商 |
| **FindPrice（找找）** | https://www.findprice.com.tw | 主流購物網站 + 拍賣 |

## 授權

MIT License
