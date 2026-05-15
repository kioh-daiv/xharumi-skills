# 🌟 xharumi-skills

[![Languages](https://img.shields.io/badge/Languages-EN%20|%20JA%20|%20ZH-blue.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Skills](https://img.shields.io/badge/Skills-8-brightgreen.svg)](#-スキル一覧8-個)

[English](./README.md) | **日本語** | [中文](./README.zh.md)

**xharumi-skills** は、Claude Code 用の **8 個のカスタムスキル** をまとめたモノリポです。**X Harumi** が、ソフトウェア開発を **アイデアからマージまで（とそれ以降も）** 一気通貫で支援するために設計しました。

完全な **DevSecOps リレー** として機能します：アイデア出し → PRD → GitHub Issue + ブランチ + Draft PR → Tech Spec → TDD コーディング → マージ前のセキュリティ監査。さらにデバッグ・思考モデル抽出・トークンコスト最適化までカバー。

初心者でも、**5 つのコアスキルを順に実行するだけ** で、Claude Code が「プロ品質 + セキュア」なソフトウェア開発を導いてくれます。

---

## 📦 スキル一覧（8 個）

### 🚀 DevSecOps ワークフロー（5 個のコアスキル）

| # | スキル | 役割 | 内容 |
|---|--------|------|------|
| 1 | [`xharumi-idea`](./xharumi-idea/) | 🟢 PM | 曖昧なアイデアを **PRD** に整理（質問駆動）|
| 2 | [`xharumi-kickoff`](./xharumi-kickoff/) | 🟡 スクラムマスター | **GitHub Issue** 作成、**ブランチ**切り、**Draft PR** 起票（`gh` CLI）|
| 3 | [`xharumi-design`](./xharumi-design/) | 🟠 テックリード | アーキ設計 + DB スキーマ + 脅威モデリング → **Tech Spec** 出力 |
| 4 | [`xharumi-dev`](./xharumi-dev/) | 🔵 シニアエンジニア | TDD でテスト + 実装、Conventional Commits、PR を Ready に |
| 5 | [`xharumi-sec`](./xharumi-sec/) | 🛡️ セキュリティエンジニア | 最終監査：OWASP Top 10、Supabase RLS 漏れ、ハードコード認証情報をスキャン |

### 🚑 エクストラスキル

| # | スキル | 役割 | 内容 |
|---|--------|------|------|
| 6 | [`xharumi-investigate`](./xharumi-investigate/) | SRE / シニアエンジニア | バグや予期せぬ挙動を深掘り、根本原因特定、修正方針提示（または直接修正）|
| 7 | [`xharumi-distiller`](./xharumi-distiller/) | 🧠 認知アーキテクト | 人物名を渡す → 思考モデル / 経験則 / 盲点を抽出 → 専用 **mentor-skill** を自動生成 |

### 🧹 ユーティリティスキル

| # | スキル | 役割 | 内容 |
|---|--------|------|------|
| 8 | [`xharumi-token-detox`](./xharumi-token-detox/) | トークン最適化 | トークン肥大化を診断、ignore 設定を自動修正、大ファイルのコスト推定。詳細は [専用 README](./xharumi-token-detox/README.ja.md) 参照 |

---

## 🚀 5 ステップワークフロー

新機能を作るとき、この順で実行：

```
xharumi-idea  →  xharumi-kickoff  →  xharumi-design  →  xharumi-dev  →  xharumi-sec
   (PRD)         (Issue + PR)         (Tech Spec)        (Code + TDD)    (監査 + マージ)
```

各スキルが次への引き継ぎ条件を明示するので、「次に何をやればいいか」を考える必要はありません。

---

## 📦 インストール

### オプション A：リポ全体をクローン（推奨）

```bash
# モノリポを安定した場所にクローン
git clone https://github.com/kioh-daiv/xharumi-skills.git ~/xharumi-skills

# 各スキルを Claude Code のスキルディレクトリへ symlink
for s in ~/xharumi-skills/xharumi-*; do
  ln -s "$s" ~/.claude/skills/$(basename $s)
done
```

これで 8 個全部入り、`git pull` 一発で全スキル更新。

### オプション B：個別インストール

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

### インストール確認

```bash
ls -la ~/.claude/skills/ | grep xharumi-
```

---

## 💡 使い方の例

```
# 新機能を始める
> run xharumi-idea
> メールリマインダー付きの Todo アプリを作りたい

# PRD ができたら
> run xharumi-kickoff

# Tech Spec が決まったら
> run xharumi-design

# コーディング開始
> run xharumi-dev

# マージ前
> run xharumi-sec

# いつでも：謎のバグを調査
> run xharumi-investigate
> ログインフローで "Invalid token" になるが JWT は正しい

# いつでも：思考モデルを抽出
> run xharumi-distiller
> スティーブ・ジョブズを抽出して

# いつでも：トークン代を削減
> run xharumi-token-detox
```

---

## 🤝 貢献

PR 大歓迎です。例：
- プロンプト改善、フレームワーク特化の脅威モデル追加（`xharumi-sec`）
- 新しいメンター原型を `xharumi-distiller` に追加
- `xharumi-token-detox` のデフォルト ignore ルール更新
- 多言語対応の追加

詳細は [CONTRIBUTING.md](./CONTRIBUTING.md) を参照。

---

## 📄 ライセンス

[MIT License](./LICENSE) — Copyright (c) 2026 **X Harumi**

---

## 🔗 著者

**X Harumi**（[@kioh-daiv](https://github.com/kioh-daiv)）作 — AI エージェント設計と現実のソフトウェアワークフローの橋渡し。
