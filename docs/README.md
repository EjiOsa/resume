# ローカルプレビュー方法（Jekyll）

このリポジトリでは、`docs/` ディレクトリを Jekyll サイトのルートとして使用し、Markdown 形式の職務経歴書をローカルで確認できます。

---

## ✅ 前提条件

- Ruby（推奨：3.0 以上）
- Bundler（Jekyll 実行に必要）

バージョン確認：

```bash
ruby -v
bundler -v
```

## 　初回セットアップ

```bash
bundle install
```

## サーバー起動

```bash
bundle exec jekyll serve
```

起動後に `http://localhost:4000` へアクセス
