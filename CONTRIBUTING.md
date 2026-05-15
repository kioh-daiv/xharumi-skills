# Contributing to xharumi-skills

Thank you for considering contributing to **xharumi-skills**! This monorepo welcomes contributions of all kinds.

---

## 🤝 Ways to Contribute

1. **Improve existing skills** — Refine prompts, add edge cases, enhance the chained workflow
2. **Add framework-specific patterns** — e.g., `xharumi-sec` threat models for Next.js, FastAPI, Rails
3. **Add mentor archetypes** — Help `xharumi-distiller` extract more thinkers' models
4. **Update default rules** — `xharumi-token-detox` ignore patterns for new frameworks
5. **Translate** — Add languages beyond EN / JA / ZH
6. **Write a new skill** — Propose via Issue first

---

## 📝 Pull Request Process

1. **Fork** this repo and create a feature branch from `main`:
   ```bash
   git checkout -b feat/<short-description>
   # or
   git checkout -b fix/<short-description>
   ```

2. **Make your changes** with clear commit messages following [Conventional Commits](https://www.conventionalcommits.org/):
   ```
   feat(xharumi-sec): add Next.js middleware threat model
   fix(xharumi-token-detox): handle .gitignore with comments
   docs(README): update install instructions for v2
   ```

3. **Test your changes locally** by symlinking the skill and running it in Claude Code:
   ```bash
   ln -s $(pwd)/xharumi-<name> ~/.claude/skills/xharumi-<name>
   # Restart Claude Code, then run the skill
   ```

4. **Open a Pull Request** with:
   - Clear description of what changed and why
   - Before/After examples if it changes prompt behavior
   - Updated README sections if user-facing

---

## 📐 Skill Structure Convention

Each skill must follow this structure:

```
xharumi-<name>/
├── SKILL.md              # Required: Claude Code skill definition
├── README.md             # Optional: Standalone skill documentation
└── README.ja.md / .zh.md # Optional: Multilingual docs
```

### `SKILL.md` Frontmatter

```yaml
---
name: xharumi-<name>
description: <One-line description that Claude will use to decide when to invoke this skill. Include trigger keywords.>
---
```

### Naming Rule

- All skills in this monorepo MUST use the `xharumi-` prefix
- For non-public skills (personal, business, work), use other prefixes (`pkm-`, `lab-`, `scna-`) and host them in a separate location

---

## 🎨 Style Guide

- **Prompts in SKILL.md**: Write in second person ("You are an expert..."), use clear numbered workflows
- **Code blocks**: Use language tags (` ```bash`, ` ```python`)
- **Headings**: Use emoji prefix sparingly for major sections
- **Examples**: Show realistic usage, not toy examples

---

## 🔒 License Agreement

By contributing to xharumi-skills, you agree that your contributions will be licensed under the [MIT License](./LICENSE).

---

## 🐛 Reporting Bugs

Open an [Issue](https://github.com/kioh-daiv/xharumi-skills/issues) with:
- Skill name and version (commit hash if possible)
- Claude Code version (`claude --version`)
- Reproduction steps
- Expected vs actual behavior

---

## 💬 Questions?

Open a [Discussion](https://github.com/kioh-daiv/xharumi-skills/discussions) or reach out to [@kioh-daiv](https://github.com/kioh-daiv).

Thanks for making xharumi-skills better! 🙏
