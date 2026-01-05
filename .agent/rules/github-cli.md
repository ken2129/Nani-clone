---
trigger: model_decision
description: GitHub CLI (gh) の利用ルール
---

# GitHub CLI (gh) 運用

- **基本**: PR作成やステータス確認には `gh` コマンドを使用。
- **PR作成 (`gh pr create`)**:
  - **非対話実行**: `--title`, `--body`, `--base`, `--head` を明示。
  - **テンプレート適用**: `.github/PULL_REQUEST_TEMPLATE.md` を読み込んで `--body` に反映。
- **確認**: 必要に応じ `gh pr list`, `gh issue list` で重複確認。
