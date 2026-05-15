# Contributing to Token Detox

First off, thank you for considering contributing to Token Detox! It's people like you that make Claude Code skills more powerful and accessible for everyone.

## How Can I Contribute?

### 1. Expanding Ignore Rules
Different languages and frameworks have their own heavy directories or files that should be ignored by default to save tokens. 
If you know a common directory (e.g., `.venv/` for Python, `vendor/` for Go) that is not currently checked by `SKILL.md`, please open a Pull Request to add it!

**How to update `SKILL.md`:**
1. Open `SKILL.md`.
2. Locate the "Diagnose Context & Ignore Configs" section.
3. Add your framework's directories to the appropriate category.

### 2. Improving Prompts
If you find a way to make the token diagnosis faster, more accurate, or better formatted, feel free to submit improvements to the prompt inside `SKILL.md`.

### 3. Translation
We aim to support English, Japanese, and Chinese comprehensively. If you notice any awkward phrasing in the README files or want to translate the README into another language, Pull Requests are highly appreciated.

## Pull Request Process
1. Fork the repo and create your branch from `main`.
2. Make your changes.
3. If you've updated `SKILL.md`, please test it locally in Claude Code (`/skill add .`) to ensure it behaves correctly.
4. Issue that pull request!

Thank you!
