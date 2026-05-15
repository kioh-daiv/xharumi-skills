# 🧹 Token Detox Skill for Claude Code

> 📦 Part of [`xharumi-skills`](../README.md) monorepo

[![Languages](https://img.shields.io/badge/Languages-EN%20|%20JA%20|%20ZH-blue.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

[English](./README.md) | **日本語** | [中文](./README.zh.md)

**Token Detox** は、Claude Code を使用する際のトークン消費を監視・最適化し、APIコストを削減するためのカスタムスキルです。

Claude Code を大規模なプロジェクトや、ビルドファイル・ログが多い環境で実行すると、不要なファイルがコンテキストに読み込まれ、トークン消費が激しくなる（＝コストが高騰する）ことがあります。このスキルは、その原因を特定し、自動で修正を提案・実行します。

## ✨ 主な機能

- 🔍 **除外設定の診断:** `.claudesignore` や `.gitignore` をチェックし、一般的にトークンを浪費しやすいディレクトリ（`node_modules/`, `dist/`, メディアファイルなど）が適切に無視されているか確認します。
- 📊 **重いファイルのコスト見積もり:** プロジェクト内の大きなファイルを検索し、それを読み込んだ場合にどれくらいのトークン（コスト）が消費されるかを概算して警告します。
- 🧹 **コンテキストのクリーンアップ:** チャット履歴が長くなりすぎている場合、`/compact` や `/clear` の実行を促します。
- 🤖 **ワンクリック自動修正:** 診断結果をもとに、見落としていた無視ルールを `.claudesignore` に自動追記し、最適な状態へ修復します。
- 🌐 **多言語対応:** あなたが話しかけた言語（日本語、英語、中国語）で診断結果と提案を返します。

## 🚀 インストール方法

Token Detox スキルをあなたのプロジェクト、またはグローバルの Claude Code 環境にインストールするには、以下の手順を実行します。

### オプション A: グローバルにインストールする (推奨)
すべてのプロジェクトで使えるようにするには、グローバルの `claude.json` にスキルを登録します。

1. このリポジトリを適当な場所にクローン（またはダウンロード）します。
   ```bash
   # Part of xharumi-skills monorepo:
   git clone https://github.com/kioh-daiv/xharumi-skills.git ~/xharumi-skills
   ln -s ~/xharumi-skills/xharumi-token-detox ~/.claude/skills/xharumi-token-detox
   ```
2. Claude Code を開き、スキルを登録します。
   ```bash
   claude
   > /skill add ~/.claude-skills/xharumi-token-detox
   ```

### オプション B: プロジェクトごとにインストールする
特定のプロジェクトディレクトリ内でのみ使いたい場合の手順です。

1. プロジェクト内にスキル用のディレクトリを作成し、ファイルを配置します。
2. そのディレクトリのルートで、以下を実行してスキルを追加します。
   ```bash
   claude
   > /skill add ./path/to/xharumi-token-detox
   ```

## 💡 使い方

Claude Code 内で、以下のようなプロンプトを入力するだけで発動します。

* `"run xharumi-token-detox"`
* `"最近トークン消費が激しいから原因を調べて"`
* `"プロジェクトの不要なファイルを ignore に追加してデトックスして"`

**実行例:**
![Demo](https://via.placeholder.com/800x400?text=Demo+GIF+Placeholder)  
*(※ ここに実行中のスクリーンショットやGIF動画を配置すると効果的です)*

## 🤝 コントリビュート

コントリビューションは大歓迎です！
特定の言語（Python, Go, Rubyなど）やフレームワークで「これも無視リストに入れるべき！」という知見があれば、ぜひ `SKILL.md` に追記してプルリクエストを送ってください。

詳細は [CONTRIBUTING.md](./CONTRIBUTING.md) をご覧ください。

## 📄 ライセンス

このプロジェクトは MIT ライセンスのもとで公開されています。詳細は [LICENSE](./LICENSE) ファイルをご覧ください。
