# rakuraku-check.com 公開用リポジトリ

らくらく臨店チェックを独自ドメイン https://rakuraku-check.com/ で公開するためのリポジトリ。

- アプリ本体のソースは [azumatori49-max/tori](https://github.com/azumatori49-max/tori) の
  `claude/store-checklist-app-ld80bz` ブランチ（`rakuraku-check/`）。**このリポジトリにアプリのコピーは置かない**
- デプロイは `.github/workflows/deploy.yml` が tori から最新を取得して行う
  （tori 更新後に手動起動＋毎日1回の定期実行）
- 会社別サイトは `/c/<会社ID>/`（tori 側 `rakuraku-check/companies/` から生成）

## 初回セットアップ（一度だけ）

1. Settings → Pages → Custom domain に `rakuraku-check.com` を入力して Save、
   証明書発行後に Enforce HTTPS を ON
2. Cloudflare DNS に CNAME を2件（@ と www → `azumatori49-max.github.io`、プロキシOFF）
3. Google Cloud の APIキー「HTTPリファラー制限」に `https://rakuraku-check.com/*` を追加
