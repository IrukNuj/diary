# 自動動画生成ツールの開発とAPI検証

> 2026-09-14

## Summary
Gemini APIキーの仕様変更検証と、長文テキストをスクロールする動画自動量産スクリプトの作成。

## Added
- `mass_produce.ts`
  - 対象サイトのリンク自動抽出と、動画の連続レンダリング。
- `Root.tsx` の動的フレーム調整
  - 外部プロパティ渡しによる尺の自動計算。
- `Video.tsx` のスクロールアニメーション
  - 長文テキストの視認性確保。

## Changed
- `make-video.ts` (旧 `generate.ts`)
  - AI要約を廃止。CLIからの直接テキスト入力化。API依存の排除。

## Fixed (Investigated)
- Gemini APIキー（`AQ.`形式）の認証エラー
  - Google Cloudにおける仕様変更の特定。AI関連APIキーのサービスアカウント紐付けの必須化。

## Retrospective
- **振り返り（全体）**: 自動化において、無料APIのレート制限とレンダリング待機時間がボトルネックになることを確認。
- **改善案（More Better）**: 動画系はROIが低いため、単価の高いデジタル商材販売へピボット。
- **エージェント改善**: ユーザーのWSL環境におけるGUIブラウザ自動化（`chrome_devtools`）の制約を学習。手動操作への誘導、またはPolar.sh等API経由の自動化提案を徹底する。
