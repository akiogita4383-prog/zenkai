# 前回いつ

薬やコンタクトなど「前回いつやったか」をカレンダーにすぐ記録できるPWAです。
ビルド不要の静的ファイルだけで動きます。

## 公開手順（GitHub Pages）

1. GitHubで新しいリポジトリを作る（例：`zenkai-itsu`）
2. このフォルダの中身をすべてリポジトリ直下に置いて push
3. リポジトリの **Settings → Pages** で
   Source を `Deploy from a branch`、Branch を `main` / `/ (root)` にして保存
4. 数分後に `https://<ユーザー名>.github.io/zenkai-itsu/` で開けます

## ホーム画面に追加

- iPhone：Safariで開く → 共有 → 「ホーム画面に追加」
- Android：Chromeで開く → メニュー → 「アプリをインストール」

一度開けばオフラインでも使えます。

## ファイル構成

```
index.html             アプリ本体（HTML / CSS / JS を1ファイルに）
manifest.webmanifest   アプリ名・アイコン・表示モード
sw.js                  オフライン対応の Service Worker
icons/                 アプリアイコン
.nojekyll              GitHub Pages の Jekyll 処理を止める
```

## 更新するとき

`index.html` を直したら、`sw.js` の `VERSION` を `v2`、`v3`… と上げてから push してください。
古いキャッシュが消えて、新しい版に切り替わります。

## データについて

記録は端末のブラウザ（localStorage）に保存されます。
端末間の同期はなく、ブラウザのデータを消すと記録も消えます。
