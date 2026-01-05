# Nani-clone

Gemini API を利用した、シンプルでセキュアなリアルタイム翻訳ツールです。

## 概要

このプロジェクトは、Google の Gemini API (1.5 Flash) を利用して、入力されたテキストをリアルタイムで翻訳する Web アプリケーションです。
ユーザー自身が発行した API キーを使用する **BYOK (Bring Your Own Key)** 構成を採用しており、高いプライバシーと利便性を両立しています。

## 特徴

- **リアルタイム翻訳**: 入力停止から 500ms 後に自動的に翻訳を開始します。
- **セキュアな設計**:
  - API キーはブラウザの `httpOnly Cookie` に保存され、JavaScript からアクセスできません。
  - サーバー側のデータベースには一切データを保存しないため、プライバシーが守られます。
- **モダンな UI**: Vanilla CSS による、装飾を極限まで削ぎ落とした「スマートでミニマル」なデザイン。
- **レスポンシブ対応**: PC、タブレット、スマートフォンで快適に動作します。

## 技術スタック

- **フロントエンド**: Next.js (App Router), React, TypeScript
- **スタイリング**: Vanilla CSS
- **バックエンド**: Next.js API Routes (API Proxy)
- **AI モデル**: Google Gemini 1.5 Flash
- **インフラ**: Vercel

## セットアップ

1. 依存関係のインストール:
   ```bash
   npm install
   ```
2. 開発サーバーの起動:
   ```bash
   npm run dev
   ```
3. [Gemini API キー](https://aistudio.google.com/app/apikey)を取得し、アプリの設定画面から入力して使用してください。

## ドキュメント

- [要件定義書](docs/REQUIREMENTS.md)
- [デザイン設計書](docs/DESIGN.md)

## ライセンス

MIT License
