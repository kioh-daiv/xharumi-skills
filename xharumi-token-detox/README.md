# 🧹 Token Detox Skill for Claude Code

> 📦 Part of [`xharumi-skills`](../README.md) monorepo

[![Languages](https://img.shields.io/badge/Languages-EN%20|%20JA%20|%20ZH-blue.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**English** | [日本語](./README.ja.md) | [中文](./README.zh.md)

**Token Detox** is a custom skill for Claude Code that helps you monitor, optimize, and reduce token consumption to save on API costs.

Running Claude Code in large repositories or environments with many build files and logs can accidentally pull unnecessary files into context. This drastically increases token consumption and costs. This skill identifies the root causes of token bloat and provides a one-click auto-remediation workflow to fix them.

## ✨ Features

- 🔍 **Ignore Rules Diagnosis:** Checks your `.claudesignore` or `.gitignore` for missing common culprits that waste tokens (e.g., `node_modules/`, `dist/`, media files).
- 📊 **Heavy Files Cost Estimation:** Finds the largest files in your project and estimates the token cost of accidentally reading them, giving you a clear picture of potential waste.
- 🧹 **Context Cleanup:** Reminds you to run `/compact` or `/clear` if your conversation history is too bloated.
- 🤖 **One-Click Auto-Remediation:** Automatically appends missing rules to your `.claudesignore` based on the diagnosis.
- 🌐 **Multilingual Support:** Responds with diagnosis and suggestions in the language you used to trigger it (English, Japanese, or Chinese).

## 🚀 Installation

You can install the Token Detox skill globally or per-project.

### Option A: Global Installation (Recommended)
Add the skill to your global Claude Code environment so it's available in any directory.

1. Clone or download this repository:
   ```bash
   # Part of xharumi-skills monorepo:
   git clone https://github.com/kioh-daiv/xharumi-skills.git ~/xharumi-skills
   ln -s ~/xharumi-skills/xharumi-token-detox ~/.claude/skills/xharumi-token-detox
   ```
2. Open Claude Code and add the skill:
   ```bash
   claude
   > /skill add ~/.claude-skills/xharumi-token-detox
   ```

### Option B: Project-Level Installation
If you only want to use it in a specific project:

1. Place the skill files in a directory within your project.
2. In the root of your project, run:
   ```bash
   claude
   > /skill add ./path/to/xharumi-token-detox
   ```

## 💡 Usage

Simply prompt Claude Code to trigger the skill.

* `"run xharumi-token-detox"`
* `"My token usage is high, please check why"`
* `"Optimize my tokens and update my ignore files"`

**Example:**
![Demo](https://via.placeholder.com/800x400?text=Demo+GIF+Placeholder)  
*(Add a screenshot or GIF of the skill in action here)*

## 🤝 Contributing

Contributions are very welcome! 
If you know of specific framework directories (Python, Go, Ruby, etc.) that should be ignored by default but aren't, please submit a Pull Request to update the `SKILL.md` rules.

See [CONTRIBUTING.md](./CONTRIBUTING.md) for more details.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.
