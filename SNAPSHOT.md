# Snapshot — v3-candidate (HugoBlox Academic CV)

研究室サイトの **HugoBlox Academic CV 版**（候補 v3）。新世代 HugoBlox（Tailwind v4 / `kit/modules/blox`）。
日英二言語。改善後の情報構成（v2 と同じIA）。論文は占位（空）。

## 構成 / Notes
- テーマ: Hugo Modules（`go.mod`）。`_vendor/` に vendor 済み（実行時 Go 不要）。
- ビルドに必要: **Hugo extended**, **Node.js**（`npm install` で Tailwind v4 / preact / pagefind）, または PATH 上の standalone `tailwindcss`。
- 改善IA: ホーム / 研究(研究テーマ・映像集) / 論文 / メンバー(メンバー・OB・OG) / ニュース / 入室希望 / アクセス、フッター: 受賞・リンク。
- 論文: 占位（TROIS 等のリンクのみ。本体約800件は別リポジトリ `cvim-tsukuba.github.io/_content/raw/` に抽出済み）。
- 退避: 2014年の旧紹介動画リンクは未収録（v2 の `_archive/` 参照）。

## ローカル実行 / Run
```bash
npm install                 # Tailwind v4, preact, pagefind
hugo mod vendor             # （初回のみ。Go 必須）
hugo server --port 1314     # → http://localhost:1314/
```

## 既知の制限
- 自動スクリーンショットツール（ヘッドレス）はこのテーマの外部リソース待ちでハングするため未取得。実ブラウザでは正常表示。
