# 🌟 xharumi-skills

[![Languages](https://img.shields.io/badge/Languages-EN%20|%20JA%20|%20ZH-blue.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Skills](https://img.shields.io/badge/Skills-8-brightgreen.svg)](#-技能列表8-个)

[English](./README.md) | [日本語](./README.ja.md) | **中文**

**xharumi-skills** 是为 Claude Code 设计的 **8 个自定义技能** 集成仓库,由 **X Harumi** 打造,旨在简化从创意到合并的整个软件开发流程,并涵盖之后的运维场景。

它充当完整的 **DevSecOps 接力棒**:头脑风暴 → 编写 PRD → 创建 GitHub Issue + 分支 + Draft PR → 设计 Tech Spec → TDD 编码 → 合并前安全审计。还包括调试、思维模型提炼、Token 成本优化等扩展技能。

即使是初学者,只需 **按顺序运行 5 个核心技能**,Claude Code 就会引导你构建专业、安全的软件。

---

## 📦 技能列表(8 个)

### 🚀 DevSecOps 工作流(5 个核心技能)

| # | 技能 | 角色 | 功能 |
|---|------|------|------|
| 1 | [`xharumi-idea`](./xharumi-idea/) | 🟢 产品经理 | 通过结构化提问,把模糊创意转化为专业 **PRD** |
| 2 | [`xharumi-kickoff`](./xharumi-kickoff/) | 🟡 Scrum Master | 创建 **GitHub Issue**、检出 **分支**、打开 **Draft PR**(via `gh` CLI)|
| 3 | [`xharumi-design`](./xharumi-design/) | 🟠 技术负责人 | 设计架构 + DB schema + 威胁建模 → 输出 **Tech Spec** |
| 4 | [`xharumi-dev`](./xharumi-dev/) | 🔵 高级工程师 | TDD 编写测试 + 实现,创建 Conventional Commits,PR 标记为 Ready |
| 5 | [`xharumi-sec`](./xharumi-sec/) | 🛡️ 安全工程师 | 最终审计:扫描 OWASP Top 10、Supabase RLS 漏洞、硬编码凭证 |

### 🚑 扩展技能

| # | 技能 | 角色 | 功能 |
|---|------|------|------|
| 6 | [`xharumi-investigate`](./xharumi-investigate/) | SRE / 高级工程师 | 深入排查 bug 和异常行为,定位根本原因,提出(或实施)修复方案 |
| 7 | [`xharumi-distiller`](./xharumi-distiller/) | 🧠 认知架构师 | 输入人名 → Claude 提取其思维模型 / 启发式 / 盲点 → 自动生成专属 **mentor-skill** |

### 🧹 实用工具技能

| # | 技能 | 角色 | 功能 |
|---|------|------|------|
| 8 | [`xharumi-token-detox`](./xharumi-token-detox/) | Token 优化 | 诊断 token 膨胀,自动修复 ignore 配置,估算大文件成本。详见 [专属 README](./xharumi-token-detox/README.zh.md) |

---

## 🚀 5 步工作流

构建新功能时,按此顺序运行:

```
xharumi-idea  →  xharumi-kickoff  →  xharumi-design  →  xharumi-dev  →  xharumi-sec
   (PRD)         (Issue + PR)         (Tech Spec)        (Code + TDD)    (审计 + 合并)
```

每个技能都明示对下一个技能的交接条件,所以你不用思考"接下来该做什么"。

---

## 📦 安装

### 选项 A:克隆整个仓库(推荐)

```bash
# 把 monorepo 克隆到稳定位置
git clone https://github.com/kioh-daiv/xharumi-skills.git ~/xharumi-skills

# 把每个技能软链接到 Claude Code 的技能目录
for s in ~/xharumi-skills/xharumi-*; do
  ln -s "$s" ~/.claude/skills/$(basename $s)
done
```

这样可一次安装 8 个技能,以后用 `git pull` 一键更新所有技能。

### 选项 B:单独安装

```bash
/skill add https://github.com/kioh-daiv/xharumi-skills/tree/main/xharumi-idea
/skill add https://github.com/kioh-daiv/xharumi-skills/tree/main/xharumi-kickoff
/skill add https://github.com/kioh-daiv/xharumi-skills/tree/main/xharumi-design
/skill add https://github.com/kioh-daiv/xharumi-skills/tree/main/xharumi-dev
/skill add https://github.com/kioh-daiv/xharumi-skills/tree/main/xharumi-sec
/skill add https://github.com/kioh-daiv/xharumi-skills/tree/main/xharumi-investigate
/skill add https://github.com/kioh-daiv/xharumi-skills/tree/main/xharumi-distiller
/skill add https://github.com/kioh-daiv/xharumi-skills/tree/main/xharumi-token-detox
```

### 验证安装

```bash
ls -la ~/.claude/skills/ | grep xharumi-
```

---

## 💡 使用示例

```
# 启动新功能
> run xharumi-idea
> 我想做一个带邮件提醒的 Todo 应用

# PRD 准备好之后
> run xharumi-kickoff

# Tech Spec 确定之后
> run xharumi-design

# 开始编码
> run xharumi-dev

# 合并前
> run xharumi-sec

# 任何时候:调查神秘 bug
> run xharumi-investigate
> 登录流程报 "Invalid token",但 JWT 看起来没问题

# 任何时候:克隆思维模型
> run xharumi-distiller
> 提炼史蒂夫·乔布斯

# 任何时候:削减 token 账单
> run xharumi-token-detox
```

---

## 🤝 贡献

欢迎 PR!例如:
- 改进 prompt 或为 `xharumi-sec` 添加框架特定的威胁模型
- 为 `xharumi-distiller` 添加新的 mentor 原型
- 更新 `xharumi-token-detox` 的默认 ignore 规则
- 添加更多语言支持

详见 [CONTRIBUTING.md](./CONTRIBUTING.md)。

---

## 📄 许可证

[MIT License](./LICENSE) — Copyright (c) 2026 **X Harumi**

---

## 🔗 作者

由 **X Harumi**([@kioh-daiv](https://github.com/kioh-daiv))创建 — 连接 AI 代理设计与真实世界软件工作流。
