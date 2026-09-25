# 🌟 xharumi-skills

[![Languages](https://img.shields.io/badge/Languages-EN%20|%20JA%20|%20ZH-blue.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Skills](https://img.shields.io/badge/Skills-2-brightgreen.svg)](#-技能列表2-个)

[English](./README.md) | [日本語](./README.ja.md) | **中文**

**xharumi-skills** 是一个 **Claude Code 自定义技能** 的 monorepo，由 **X Harumi** 设计，帮助你把一个模糊的想法一路推进到合并完成的 PR。

流程是简单的两步接力：先把想法整理成 **PRD**，再编写测试和实现、提交、创建 PR 并合并。

---

## 📦 技能列表(2 个)

| # | 技能 | 角色 | 功能 |
|---|------|------|------|
| 1 | [`xharumi-idea`](./xharumi-idea/) | 🟢 产品经理 | 通过结构化提问，把模糊的想法整理成专业的 **PRD** |
| 2 | [`xharumi-dev`](./xharumi-dev/) | 🔵 高级工程师 | 编写测试 + 实现(TDD)、安全自检、Conventional Commits、创建/更新 PR 并合并 |

---

## 🚀 2 步工作流

```
xharumi-idea  →  xharumi-dev
   (PRD)          (代码 + TDD + PR + 合并)
```

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

之后只需一次 `git pull` 即可更新全部技能。

### 选项 B:单独安装

```bash
/skill add https://github.com/kioh-daiv/xharumi-skills/tree/main/xharumi-idea
/skill add https://github.com/kioh-daiv/xharumi-skills/tree/main/xharumi-dev
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
> run xharumi-dev
```

---

## 🗂️ 已停用的技能

`xharumi-kickoff`、`xharumi-design`、`xharumi-sec`、`xharumi-investigate`、`xharumi-distiller`、`xharumi-token-detox` 已于 2026-07 停用。工作流已整合为 `idea → dev` 两步，Issue / PR 创建和安全检查已并入 `xharumi-dev`。旧技能可在 git 历史中查看。

---

## 🤝 贡献

欢迎贡献!详情请参阅 [CONTRIBUTING.md](./CONTRIBUTING.md)。

---

## 📄 许可证

[MIT License](./LICENSE) — Copyright (c) 2026 **X Harumi**

---

## 🔗 作者

由 **X Harumi**([@kioh-daiv](https://github.com/kioh-daiv))打造 —— 连接 AI 智能体设计与真实的软件开发流程。
