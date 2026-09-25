# 🌟 xharumi-skills

[![Languages](https://img.shields.io/badge/Languages-EN%20|%20JA%20|%20ZH-blue.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Skills](https://img.shields.io/badge/Skills-2-brightgreen.svg)](#-スキル一覧2-個)

[English](./README.md) | **日本語** | [中文](./README.zh.md)

**xharumi-skills** は、Claude Code 用の **カスタムスキル** をまとめたモノリポです。**X Harumi** が、ソフトウェア開発を **ぼんやりしたアイデアからマージ済みの PR まで** 支援するために設計しました。

流れはシンプルな 2 段リレーです：アイデアを **PRD** にまとめ、テストと実装を書いてコミットし、PR を出してマージします。

---

## 📦 スキル一覧（2 個）

| # | スキル | 役割 | 何をするか |
|---|-------|------|-----------|
| 1 | [`xharumi-idea`](./xharumi-idea/) | 🟢 プロダクトマネージャー | 対話形式の質問で、ぼんやりしたアイデアを **PRD** に仕上げる |
| 2 | [`xharumi-dev`](./xharumi-dev/) | 🔵 シニアエンジニア | テスト + 実装（TDD）、セキュリティのセルフチェック、Conventional Commits、PR の作成・更新とマージ |

---

## 🚀 2 ステップのワークフロー

```
xharumi-idea  →  xharumi-dev
   (PRD)          (コード + TDD + PR + マージ)
```

---

## 📦 インストール

### 方法 A：リポジトリごとクローン（推奨）

```bash
# モノリポを安定した場所にクローン
git clone https://github.com/kioh-daiv/xharumi-skills.git ~/xharumi-skills

# 各スキルを Claude Code のスキルディレクトリにシンボリックリンク
for s in ~/xharumi-skills/xharumi-*; do
  ln -s "$s" ~/.claude/skills/$(basename $s)
done
```

以後は `git pull` 1 回で全スキルが更新されます。

### 方法 B：スキルを個別にインストール

```bash
/skill add https://github.com/kioh-daiv/xharumi-skills/tree/main/xharumi-idea
/skill add https://github.com/kioh-daiv/xharumi-skills/tree/main/xharumi-dev
```

### インストール確認

```bash
ls -la ~/.claude/skills/ | grep xharumi-
```

---

## 💡 使用例

```
# 新機能を始める
> run xharumi-idea
> メールでリマインドしてくれる Todo アプリを作りたい

# PRD ができたら
> run xharumi-dev
```

---

## 🗂️ 廃止したスキル

`xharumi-kickoff` `xharumi-design` `xharumi-sec` `xharumi-investigate` `xharumi-distiller` `xharumi-token-detox` は 2026-07 に廃止しました。ワークフローは `idea → dev` の 2 段に集約し、Issue / PR 作成とセキュリティチェックは `xharumi-dev` に含めています。旧スキルは git の履歴から参照できます。

---

## 🤝 コントリビューション

歓迎します。詳しくは [CONTRIBUTING.md](./CONTRIBUTING.md) を参照してください。

---

## 📄 ライセンス

[MIT License](./LICENSE) — Copyright (c) 2026 **X Harumi**

---

## 🔗 作者

**X Harumi**（[@kioh-daiv](https://github.com/kioh-daiv)）— AI エージェント設計と実際のソフトウェア開発の橋渡しをしています。
