---
name: commit-push-pr
description: コミット、プッシュ、PR作成を一度に実行します。ユーザーが「コミット、プッシュ、PRを作成して」や「変更をPRにして」と依頼した場合に使用します。
allowed-tools: Bash(git:*), Bash(gh:*)
---

# Commit, Push, PR スキル

このスキルは、Git の変更をコミット、プッシュし、Pull Request を作成する一連の流れを自動化します。

## 実行手順

### 1. 現在の状態を確認

```bash
git status
git branch --show-current
```

### 2. 変更内容を確認

```bash
git diff
git diff --staged
```

最近のコミットメッセージも確認して、スタイルを合わせる：

```bash
git log -3 --format='%s'
```

### 3. 変更をコミット

- すべての変更をステージング：`git add -A`
- コミットメッセージは日本語で作成
- 以下の形式を使用（HEREDOCで複数行対応）：

```bash
git add -A && git commit -m "$(cat <<'EOF'
<type>: <subject>

<body>

🤖 Generated with [Claude Code](https://claude.com/claude-code)

Co-Authored-By: Claude Sonnet 4.5 <noreply@anthropic.com>
EOF
)"
```

**コミットメッセージの型：**
- `feat`: 新機能
- `fix`: バグ修正
- `docs`: ドキュメント更新
- `style`: スタイル変更
- `refactor`: リファクタリング
- `test`: テスト追加
- `chore`: 雑務

### 4. リモートにプッシュ

現在のブランチが main の場合：
- 新しいブランチを作成してからプッシュ
- ブランチ名は `feat/`, `fix/`, `docs/` などで始める

それ以外の場合：
- 既存ブランチにプッシュ、または `-u` フラグで新規作成

```bash
git push -u origin <ブランチ名>
```

### 5. PR を作成

`.github/PULL_REQUEST_TEMPLATE.md` の形式に**必ず従う**こと：

```bash
gh pr create --title "PRのタイトル" --body "$(cat <<'EOF'
## 概要

PRの目的や概要を簡潔に説明

## 関連 Issue

Closes #番号 または「なし」

## 行った変更

- [x] 変更内容1
- [x] 変更内容2

## 動作確認

- [x] 確認項目1
- [x] 確認項目2

## 備考

その他注意点があれば記載
EOF
)"
```

**重要：**
- 「行った変更」と「動作確認」は必ずチェックボックス形式 `- [x]` で記載
- すべての変更を完了している場合は `[x]` でチェック済みにする

## エラーハンドリング

- コミットに失敗した場合、pre-commit フックのエラーを確認
- プッシュに失敗した場合、リモートの状態を確認
- PR作成に失敗した場合、既存のPRがないか確認

## 実行例

ユーザー: 「変更をコミット、プッシュ、PRして」

1. `git status` で変更を確認
2. `git diff` で差分を確認
3. `git log -3` で最近のコミットスタイルを確認
4. 適切なコミットメッセージを生成してコミット
5. 現在のブランチまたは新規ブランチにプッシュ
6. テンプレートに従ってPRを作成
7. PR URLを返す
