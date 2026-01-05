# Claude Code 運用ルール

## 1. 核心的動作原理 (Single Source of Truth)

- **SSoT の遵守**: 実装・設計の判断は、常に `docs/REQUIREMENTS.md` と `docs/DESIGN.md` を絶対的真実とすること。
- **優先順位**: 1. ユーザーの最新の指示, 2. このルールファイル (`CLAUDE.md`), 3. `docs/` 配下のドキュメント。
- **構造**: ディレクトリ構成等は `README.md` を参照。

## 2. 開発・運用ルール

- **使用言語**: 報告、計画、コミットメッセージ等はすべて**日本語**。
- **GitHub 運用**:
  - **Issue 不要な例**: タイポ、軽微な UI 調整。
  - **ブランチ名**: `feat/issue-1-xxx` (Issueあり) または `fix/minor-update` (Issueなし)。
  - **PR 義務**: 作業完了後は `gh` コマンド（非対話）で Pull Request を提出し、マージまで責任を持つ。
  - **PR テンプレート遵守**: `.github/PULL_REQUEST_TEMPLATE.md` の形式に必ず従うこと。特に「行った変更」「動作確認」はチェックボックス形式で記載する。
- **透明性**: 重要な技術選定・設計変更時は必ず承認を得る。
