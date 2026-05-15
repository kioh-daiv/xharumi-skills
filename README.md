# 🌟 xharumi-skills

[![Languages](https://img.shields.io/badge/Languages-EN%20|%20JA%20|%20ZH-blue.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Skills](https://img.shields.io/badge/Skills-8-brightgreen.svg)](#skills)

**English** | [日本語](./README.ja.md) | [中文](./README.zh.md)

**xharumi-skills** is a monorepo of **8 custom skills for Claude Code**, designed by **X Harumi** to streamline software development from ideation to merge — and beyond.

It acts as a complete **DevSecOps relay baton**: brainstorm an idea → write a PRD → create a GitHub Issue + branch + Draft PR → architect the Tech Spec → code with TDD → run a security audit before merging. Plus extra skills for debugging, cognitive cloning, and token cost optimization.

Even if you are a beginner, simply run the **5 core skills in order** and Claude Code will guide you through building professional, secure software.

---

## 📦 Skills (8)

### 🚀 DevSecOps Workflow (5 core skills)

| # | Skill | Role | What it does |
|---|-------|------|--------------|
| 1 | [`xharumi-idea`](./xharumi-idea/) | 🟢 Product Manager | Turns your vague idea into a professional **PRD** through structured questioning |
| 2 | [`xharumi-kickoff`](./xharumi-kickoff/) | 🟡 Scrum Master | Creates a **GitHub Issue**, checks out a **branch**, opens a **Draft PR** via `gh` CLI |
| 3 | [`xharumi-design`](./xharumi-design/) | 🟠 Tech Lead | Brainstorms architecture, schema, and threat modeling — outputs a **Tech Spec** |
| 4 | [`xharumi-dev`](./xharumi-dev/) | 🔵 Senior Engineer | Writes tests + implementation (TDD), creates conventional commits, marks PR Ready |
| 5 | [`xharumi-sec`](./xharumi-sec/) | 🛡️ Security Engineer | Final audit: scans for OWASP Top 10, Supabase RLS bypasses, hardcoded secrets |

### 🚑 Extra Skills

| # | Skill | Role | What it does |
|---|-------|------|--------------|
| 6 | [`xharumi-investigate`](./xharumi-investigate/) | SRE / Senior Engineer | Deep-dives bugs and unexpected behavior, identifies root cause, proposes (or implements) the fix |
| 7 | [`xharumi-distiller`](./xharumi-distiller/) | 🧠 Cognitive Architect | Provide a name → Claude extracts mental models / heuristics / blind spots → generates a custom **mentor-skill** |

### 🧹 Utility Skills

| # | Skill | Role | What it does |
|---|-------|------|--------------|
| 8 | [`xharumi-token-detox`](./xharumi-token-detox/) | Token Optimizer | Diagnoses token bloat, fixes ignore configs, estimates cost of large files. See its [own README](./xharumi-token-detox/README.md) for details |

---

## 🚀 The 5-Step Workflow

When you want to build a new feature, run these in order:

```
xharumi-idea  →  xharumi-kickoff  →  xharumi-design  →  xharumi-dev  →  xharumi-sec
   (PRD)         (Issue + PR)         (Tech Spec)        (Code + TDD)    (Audit + Merge)
```

Each skill has clear handoff conditions to the next, so you never have to think "what's next?"

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

This way you get all 8 skills with a single `git pull` for future updates.

### Option B: Install individual skills

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

# When PRD is ready
> run xharumi-kickoff

# When Tech Spec is decided
> run xharumi-design

# When ready to code
> run xharumi-dev

# Before merging
> run xharumi-sec

# Anytime: debug a mysterious bug
> run xharumi-investigate
> The login flow throws "Invalid token" but the JWT looks fine

# Anytime: clone a thinker's mind
> run xharumi-distiller
> Distill Steve Jobs

# Anytime: cut your token bill
> run xharumi-token-detox
```

---

## 🤝 Contributing

Contributions are welcome! Open a Pull Request to:
- Improve prompts or add framework-specific threat models (`xharumi-sec`)
- Add new mentor archetypes for `xharumi-distiller` to extract
- Update default ignore rules for `xharumi-token-detox`
- Translate skills into more languages

See [CONTRIBUTING.md](./CONTRIBUTING.md) for details.

---

## 📄 License

[MIT License](./LICENSE) — Copyright (c) 2026 **X Harumi**

---

## 🔗 Author

Built by **X Harumi** ([@kioh-daiv](https://github.com/kioh-daiv)) — bridging AI agent design with real-world software workflows.
