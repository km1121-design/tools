# 社内ツール（GitHub Pages 公開用）

ブラウザから使う社内ツールを GitHub Pages で公開するためのリポジトリ。
`main` への push で `.github/workflows/deploy-pages.yml` が動き、自動デプロイされる。

| ディレクトリ | 内容 | 公開パス |
|---|---|---|
| `pages-root/` | トップページ（ツール一覧） | `/` |
| `dashboard/` | Gooner運送事業部 経営分析ダッシュボード（Vite + React。ビルドして配置） | `/dashboard/` |
| `invoice-tool/` | 請求書作成ツール（静的HTML/JS） | `/invoice-tool/` |

## 経緯

もとは `km1121-design/test` に同居していたが、同リポジトリにBAR事業の
スタッフ名・売上目標・時給が含まれるため private 化することになり、
**公開が必要なツールだけをこちらへ分離**した。

BAR 日報・経営分析アプリは `km1121-design/bar-app`（private）へ移行済み。

## ローカルでの確認

```bash
# dashboard（Vite）
cd dashboard && npm install && npm run dev

# invoice-tool / pages-root は静的なのでファイルを直接開くだけ
```

リンクはすべて相対パス（`./dashboard/` や Vite の `base: './'`）にしてあるため、
リポジトリ名が変わっても公開パスの修正は不要。
