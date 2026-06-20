# Decap CMS — コンテンツ管理画面のセットアップ

このサイトには **Decap CMS**（無料・GitHubベース）を追加済みです。
ニュース／研究テーマ／各ページを**Webフォームで編集**でき、保存すると `main` に commit され自動デプロイされます。

- 管理画面ローダー: `static/admin/index.html`
- 設定: `static/admin/config.yml`
- アクセス先: `https://cvim-tsukuba.github.io/admin/`（本番）／ `http://localhost:1313/admin/`（ローカル）

---

## 方法A：ローカルで使う（OAuth不要・すぐ使える）

GitHub のOAuth設定なしで、自分のPCですぐ編集できます（`config.yml` に `local_backend: true` を設定済み）。

```powershell
# ターミナル1: Decap のローカルプロキシ
npx decap-server

# ターミナル2: Hugo（このリポジトリのフォルダで）
hugo server
```
ブラウザで **http://localhost:1313/admin/** を開く → ログイン不要でフォーム編集。
保存するとローカルの Markdown が書き換わるので、`git push` で公開してください。

> これが一番手軽です。1人で管理するならこれで十分です。

---

## 方法B：本番（どこからでもブラウザで編集）

`https://cvim-tsukuba.github.io/admin/` でGitHubログインして編集できるようにするには、
**GitHub OAuth プロバイダ**が必要です（GitHub Pages はNetlifyのような認証機能を持たないため）。

手順の概略:
1. **GitHub OAuth App を作成**
   GitHub → Settings → Developer settings → OAuth Apps → New OAuth App
   - Homepage URL: `https://cvim-tsukuba.github.io`
   - Authorization callback URL: 下記プロバイダのコールバックURL
   取得した **Client ID / Client Secret** を控える。
2. **OAuth プロキシをデプロイ**（無料）
   代表的には **Cloudflare Workers** に OAuth プロキシを置く方法（"decap cms oauth cloudflare worker" で検索）。
   Vercel / Render の関数でも可。Client ID/Secret を環境変数に設定。
3. **`static/admin/config.yml` を編集**
   `backend:` に次を追加（プロキシのURLに置換）:
   ```yaml
   backend:
     name: github
     repo: CVIM-Tsukuba/cvim-tsukuba.github.io
     branch: main
     base_url: https://<プロキシのホスト>
     # auth_endpoint: auth   # プロキシの仕様に合わせて
   ```
   commit & push。
4. `https://cvim-tsukuba.github.io/admin/` →「Login with GitHub」で編集可能に。

参考: Decap 公式ドキュメント「Backends → GitHub」 https://decapcms.org/docs/github-backend/

---

## 編集できる項目（config.yml）

- **ニュース（日本語 / English）**: 新規作成・編集（タイトル・日付・本文）
- **研究テーマ（日本語 / English）**: タイトル・並び順・概要・本文
- **ページ（日本語 / English）**: 受賞・リンク・入室希望・映像集・OB/OG・メンバー・アクセス

### 注意
- **メンバー / アクセス** の本文には HTML（写真カード・地図iframe）が含まれます。編集時はエディタ右上の **`</>`（Markdown/コード表示）** に切り替えてから触ると崩れにくいです。
- Decap は **config.yml に定義していないフロントマター項目を保存時に削除**します。項目を増やしたいときは config.yml の `fields` に追加してください。
- 画像アップロード先は `static/uploads/`（ニュースは記事フォルダ内）。
