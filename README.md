# 🌟 xharumi-skills

[![Languages](https://img.shields.io/badge/Languages-EN%20|%20JA%20|%20ZH-blue.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Skills](https://img.shields.io/badge/Skills-2-brightgreen.svg)](#-skills-2)

**English** | [日本語](./README.ja.md) | [中文](./README.zh.md)

**xharumi-skills** is a monorepo of **custom skills for Claude Code**, designed by **X Harumi** to take software from a vague idea to a merged pull request.

The workflow is a simple two-step relay: turn your idea into a **PRD**, then implement it with tests, commit, open the PR, and merge.

---

## 📦 Skills (2)

| # | Skill | Role | What it does |
|---|-------|------|--------------|
| 1 | [`xharumi-idea`](./xharumi-idea/) | 🟢 Product Manager | Turns your vague idea into a professional **PRD** through structured questioning |
| 2 | [`xharumi-dev`](./xharumi-dev/) | 🔵 Senior Engineer | Writes tests + implementation (TDD), runs a security self-check, creates conventional commits, opens/updates the PR and merges |

---

## 🚀 The 2-Step Workflow

```
xharumi-idea  →  xharumi-dev
   (PRD)          (Code + TDD + PR + Merge)
```

---

## 📦 Installation

### Option A: Clone the whole repo (Recommended)

```bash
# Clone the monorepo to a stable location
git clone https://github.com/kioh-daiv/xharumi-skills.git ~/xharumi-skills

# Symlink each skill into Claude Code's skills directory
for s in ~/xharumi-skills/xharumi-*; do
  ln -s "$s" ~/.claude/skills/$(basename $s)
done
```

This way you get every skill with a single `git pull` for future updates.

### Option B: Install individual skills

```bash
/skill add https://github.com/kioh-daiv/xharumi-skills/tree/main/xharumi-idea
/skill add https://github.com/kioh-daiv/xharumi-skills/tree/main/xharumi-dev
```

### Verify installation

```bash
ls -la ~/.claude/skills/ | grep xharumi-
```

---

## 💡 Usage Examples

```
# Start a new feature
> run xharumi-idea
> I want to build a Todo app with email reminders

# When the PRD is ready
> run xharumi-dev
```

---

## 🗂️ Retired skills

`xharumi-kickoff`, `xharumi-design`, `xharumi-sec`, `xharumi-investigate`, `xharumi-distiller` and `xharumi-token-detox` were retired in 2026-07. The workflow was consolidated into `idea → dev`; issue/PR creation and the security check now live inside `xharumi-dev`. They remain available in the git history.

---

## 🤝 Contributing

Contributions are welcome! See [CONTRIBUTING.md](./CONTRIBUTING.md) for details.

---

## 📄 License

[MIT License](./LICENSE) — Copyright (c) 2026 **X Harumi**

---

## 🔗 Author

Built by **X Harumi** ([@kioh-daiv](https://github.com/kioh-daiv)) — bridging AI agent design with real-world software workflows.
