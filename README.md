# 職務経歴書

個人の職務経歴書を管理・公開するリポジトリです。  
Markdown 形式で記述し、[GitHub Pages](https://ejiosa.github.io/resume/) で公開しています。

## 📁 ディレクトリ構成

```
├── index.md # トップページ（自己紹介・全体リンク）
├── experience.md # 職務経歴（プロジェクト・業務内容）
├── background.md # 異業種からの転職背景（元・看護師）
├── skills.md # 使用技術・スキル一覧
└── assets # 画像やアイコンなどの静的ファイル
```

## 📦 使用技術・ツール

- **Markdown** : 職務経歴書の記述
- **GitHub Pages** : 公開用
- **textlint** : 日本語の表記ゆれや読みやすさのチェック
- **Prettier** : Markdown / JSON の整形
- **markdownlint** : Markdown 構文の Lint

## 🛠 スクリプト一覧

| コマンド        | 説明                                         |
| --------------- | -------------------------------------------- |
| `yarn format`   | Markdown / JSON ファイルのフォーマット       |
| `yarn lint`     | textlint と markdownlint による構文チェック  |
| `yarn lint:fix` | textlint による自動修正（markdownlint 含む） |
| `yarn fix`      | format + lint:fix をまとめて実行             |

## 🧪 Lint 設定について

- 日本語技術文書向けのルール（`textlint-rule-preset-ja-technical-writing`）を中心に構成
- 冗長な表現や助詞の連続、漢字の使いすぎなどを検出
- Markdown 構文の細かな揺れも `markdownlint` で補完

## 💻 VS Code 推奨設定（`.vscode/settings.json`）

```json
{
  "editor.codeActionsOnSave": {
    "source.fixAll": "explicit"
  },
  "editor.formatOnSave": false,
  "textlint.run": "onSave",
  "files.associations": {
    "*.md": "markdown"
  },
  "[json]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnSave": true
  },
  "emeraldwalk.runonsave": {
    "commands": [
      {
        "match": ".*\\.(md|txt|json)$",
        "cmd": "yarn fix"
      }
    ]
  }
}
```
