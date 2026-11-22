# payment-architect · 支付系统架构专家 Skill

> 一套体系化的国内支付系统架构方法论，以 Agent Skill（SKILL.md 开放标准）形式交付。
> 覆盖域划分、资金安全、账户记账、编码体系、合规密评、加密机、银联网联与外卡渠道。
> A systematic architecture playbook for Chinese payment systems, packaged as an Agent Skill (open SKILL.md standard).

[![Skill Standard](https://img.shields.io/badge/format-SKILL.md-blue)]()
[![Modules](https://img.shields.io/badge/modules-11-green)]()
[![Language](https://img.shields.io/badge/lang-中文-red)]()

---

## 这是什么 / What is this

一个加载后即可让 AI 编程助手（Claude Code、Cursor、WorkBuddy 及任何兼容 SKILL.md 标准的 Agent）具备**资深支付架构师判断力**的技能包：不是代码片段集合，而是从域划分到资金安全、从密评合规到渠道协议的完整工程方法论，全部沉淀为可执行的红线、状态机、检查清单。

Load it into any SKILL.md-compatible agent and it reviews, designs, and generates payment-system code like a senior payment architect: domain boundaries, fund-safety invariants, idempotency systems, accounting models, compliance matrices, and channel protocol contracts — as enforceable checklists, not vague advice.

## 内容清单 / Contents

**免费版（本仓库，3 个文件）/ Free edition:**

| 模块 / Module | 内容 / Covers |
|---|---|
| `SKILL.md` | 角色立场、任务路由、资金安全十条铁律速览 / Persona, routing, 10 fund-safety rules |
| `references/domain-map.md` | 13 个标准域职责边界、标准资金链路、6 个架构反模式 / 13-domain map, fund flow, anti-patterns |
| `references/fund-safety.md` | 金额规范、三层幂等、状态机+version CAS、事务三段式、UNKNOWN 查证、Outbox、锁序、fail-closed / Amount, idempotency, state machine, transaction boundaries |

**完整版（付费，共 11 个模块）/ Full edition (paid)**，在免费版基础上另含：

| 模块 / Module | 内容 / Covers |
|---|---|
| `domain-details.md` | 各域落地级约束：核心单、状态机、表约束、域内红线 |
| `accounting.md` | 账户-账簿-桶模型、语义记账、复式凭证、对账四步、日切日结、结算、备付金 |
| `id-codes.md` | 码三分类、全链路灯（单号串联）、交易码/产品码/费率种 |
| `business-scenarios.md` | 受限卡转账（充值+转账两阶段）、一业务单多交易单、分账与空中分账 |
| `compliance.md` | 等保 2.0、密评四性矩阵（GB/T 39786）、数据分级（JR/T 0171）、反洗钱 |
| `crypto-hsm.md` | 统一加密服务、密钥归属两判据、SM2/SM3/SM4、HSM 接入 P0 红线 |
| `channel-unionpay-netsunion.md` | 银联全渠道产品族、交易原语、签名加密、网联备付金额度模型 |
| `channel-foreign-cards.md` | 万事网联格局、Auth/Capture 双报文、3DS2、拒付全生命周期、PCI DSS |
| `engineering.md` | DDD 分层、单表 SQL 红线、公共中间件基线、错误码/异常/消息头、测试门禁 |

完整版获取 / Get the full edition：见本仓库 Releases 页或上架市场链接（更新中）。

## 安装 / Installation

```bash
# Claude Code / 兼容 Agent
npx skills add coilior/payment-architect-skill

# 或手动：把 payment-architect/ 复制到
#   用户级  ~/.workbuddy/skills/  (或 ~/.claude/skills/)
#   项目级  <repo>/.workbuddy/skills/
```

## 使用示例 / Usage

加载后直接提需求，Skill 按任务路由自动选取对应模块：

- “帮我评审这个收单域的退款链路设计” → fund-safety + accounting + business-scenarios
- “设计一个支持分账的支付中台域划分” → domain-map + business-scenarios
- “新接银联代收通道，给我接入评审清单” → channel-unionpay-netsunion
- “外卡收单的拒付工单系统怎么设计” → channel-foreign-cards + fund-safety
- “我们的口令存储方案能过密评吗” → compliance + crypto-hsm

## 设计原则 / Design principles

- **资金安全优先**：正确性 > 可用性 > 性能；UNKNOWN 只查证不重试；fail-closed
- **一切结论可执行**：落到表约束、状态机、幂等键、错误码，不停留在概念
- **通用脱敏**：不含任何特定公司内部命名，全部为国内支付行业通用口径
- Fund safety first; every conclusion lands on enforceable contracts; fully vendor-neutral

## 版本说明 / Editions

- **免费版（本仓库）**：SKILL.md + domain-map + fund-safety，覆盖架构设计与资金安全主线
- **完整版（付费）**：全部 11 个模块 + 持续更新，获取方式见上方「内容清单」

## License

本仓库内容采用 **CC BY-NC-ND 4.0**（署名-非商业-禁止演绎）。商业使用与完整版授权请联系作者。

© 2026 payment-architect contributors. All rights reserved.
