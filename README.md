# resume

個人の職務経歴書を管理・公開するリポジトリです。  
Markdown形式で記述し、GitHub Pagesでの公開をしています。

## 📁 ディレクトリ構成

```
├── assets # 画像やアイコンなどの静的ファイル
├── experience.md # 職務経歴（プロジェクト・業務内容）
├── index.md # トップページ（自己紹介・全体リンク）
├── skills.md # 使用技術・スキル一覧
└── background.md # 異業種からの転職背景（元・看護師）
```

## 📦 使用技術・ツール

- **Markdown** : 職務経歴書の記述
- **GitHub Pages** : 公開用
- **Prettier** : Markdown / JSON の整形
- **textlint** : 日本語の表記ゆれや読みやすさのチェック
- **markdownlint** : Markdown構文のLint

## 🛠 スクリプト一覧

| コマンド        | 説明                                        |
| --------------- | ------------------------------------------- |
| `yarn format`   | Markdown / JSONファイルのフォーマット       |
| `yarn lint`     | textlint と markdownlint による構文チェック |
| `yarn lint:fix` | textlint による自動修正（markdownlint含む） |
| `yarn fix`      | format + lint:fix をまとめて実行            |

## 🧪 Lint 設定について

- 日本語技術文書向けのルール（`textlint-rule-preset-ja-technical-writing`）を中心に構成
- 冗長な表現や助詞の連続、漢字の使いすぎなどを検出
- Markdown構文の細かな揺れも `markdownlint` で補完

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
