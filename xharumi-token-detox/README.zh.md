# 🧹 Token Detox Skill for Claude Code

> 📦 Part of [`xharumi-skills`](../README.md) monorepo

[![Languages](https://img.shields.io/badge/Languages-EN%20|%20JA%20|%20ZH-blue.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

[English](./README.md) | [日本語](./README.ja.md) | **中文**

**Token Detox** 是为 Claude Code 设计的自定义技能，旨在帮助您监控、优化和减少令牌（Token）消耗，从而节省 API 成本。

在大型项目或包含大量构建文件及日志的环境中运行 Claude Code 时，不必要的文件可能会被意外读入上下文中，导致令牌消耗剧增（成本飙升）。此技能可以找出导致这一问题的根本原因，并提供一键自动修复流程。

## ✨ 主要功能

- 🔍 **忽略规则诊断:** 检查您的 `.claudesignore` 或 `.gitignore`，确认是否遗漏了常见的容易浪费令牌的目录（如 `node_modules/`, `dist/`, 媒体文件等）。
- 📊 **大文件成本估算:** 搜索项目中的大型文件，并估算意外读取它们可能消耗的令牌（成本）数量，提醒您潜在的浪费。
- 🧹 **上下文清理:** 如果聊天记录过于冗长，提示您执行 `/compact` 或 `/clear` 命令。
- 🤖 **一键自动修复:** 根据诊断结果，自动将缺失的忽略规则追加到 `.claudesignore` 文件中。
- 🌐 **多语言支持:** 根据您提问时使用的语言（英语、日语或中文），以相应的语言返回诊断结果和建议。

## 🚀 安装方法

您可以全局安装 Token Detox 技能，也可以仅在特定项目中安装。

### 选项 A: 全局安装（推荐）
将技能添加到全局的 Claude Code 环境中，以便在任何目录中使用。

1. 克隆或下载此仓库：
   ```bash
   # Part of xharumi-skills monorepo:
   git clone https://github.com/kioh-daiv/xharumi-skills.git ~/xharumi-skills
   ln -s ~/xharumi-skills/xharumi-token-detox ~/.claude/skills/xharumi-token-detox
   ```
2. 打开 Claude Code，并添加技能：
   ```bash
   claude
   > /skill add ~/.claude-skills/xharumi-token-detox
   ```

### 选项 B: 项目级安装
如果您只想在特定项目中使用：

1. 将技能文件放置在项目内的一个目录中。
2. 在项目的根目录下运行：
   ```bash
   claude
   > /skill add ./path/to/xharumi-token-detox
   ```

## 💡 使用方法

在 Claude Code 中，只需输入以下提示即可触发该技能：

* `"run xharumi-token-detox"`
* `"最近 token 消耗很快，请帮我检查原因"`
* `"优化我的 token 消耗，并更新忽略文件"`

**示例:**
![Demo](https://via.placeholder.com/800x400?text=Demo+GIF+Placeholder)  
*(这里建议放置技能运行时的截图或 GIF 演示)*

## 🤝 参与贡献

非常欢迎大家的贡献！
如果您了解特定框架（如 Python, Go, Ruby 等）中应该默认忽略的目录，请提交 Pull Request 更新 `SKILL.md` 中的规则。

更多详情请参阅 [CONTRIBUTING.md](./CONTRIBUTING.md)。

## 📄 许可证

本项目基于 MIT 许可证开源 - 详情请参阅 [LICENSE](./LICENSE) 文件。
