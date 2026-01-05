# Nani-clone デベロッパーガイド

Gemini API を利用した、シンプルでセキュアなリアルタイム翻訳ツールです。

## 1. 概要

このプロジェクトは、Google の Gemini API (1.5 Flash) を利用して、入力されたテキストをリアルタイムで翻訳する Web アプリケーションです。
ユーザー自身が発行した API キーを使用する **BYOK (Bring Your Own Key)** 構成を採用しており、プライバシー保護と低コスト運用を両立しています。

## 2. 開発者向けセットアップ

1. 依存関係のインストール:
   ```bash
   npm install
   ```
2. 開発サーバーの起動:
   ```bash
   npm run dev
   ```
3. 環境設定: Gemini API キーをフロントエンドの設定画面から入力して使用します（安全のため `httpOnly Cookie` で保持されます）。

## 3. プロジェクト構造

- `src/app/`: Next.js App Router ページとレイアウト
- `src/components/`: 再利用可能な UI コンポーネント
- `docs/`: 要件定義、デザイン仕様などの設計書
- `.agent/rules/`: AI エージェント（Antigravity）向けの動作ルール

## 4. 開発プロセス

- **Issue ベースの開発**: 実装はすべて GitHub Issues に基づいて行われます。
- **ドキュメント優先**: 実装前に必ず `docs/REQUIREMENTS.md` および `docs/DESIGN.md` との不整合がないか確認してください。
- **コミットメッセージ規約**:
  - `feat:`, `fix:`, `docs:`, `style:`, `refactor:`, `test:`, `chore:` をプレフィックスとして使用してください。

## 5. ドキュメント

- [要件定義書](docs/REQUIREMENTS.md)
- [デザイン設計書](docs/DESIGN.md)

---

MIT License
