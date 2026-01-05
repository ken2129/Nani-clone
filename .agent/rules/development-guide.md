---
trigger: always_on
description: 開発・運用ルール
---

## 2. 開発・運用ルール

- **使用言語**: 報告、計画、コミットメッセージ等はすべて**日本語**。
- **GitHub 運用**:
  - **Issue 不要な例**: タイポ、軽微な UI 調整。
  - **ブランチ名**: `feat/issue-1-xxx` (Issueあり) または `fix/minor-update` (Issueなし)。
  - **PR 義務**: 作業完了後は `gh` コマンド（非対話・テンプレート遵守）で Pull Request を提出し、マージまで責任を持つ。
- **透明性**: 重要な技術選定・設計変更時は必ず `notify_user` で承認を得る。
