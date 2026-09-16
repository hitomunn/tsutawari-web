# tsutawari-web

発表の「伝わり方」を可視化するツール [Tsutawari](https://github.com/hitomunn/Tsutawari) の、
**聴衆側のページだけ**を置いた配信用リポジトリ。

GitHub Pages で配信するために公開している。中身は `index.html` 1枚と、そのアイコン2つだけ。

## 使い方

聴衆は発表者が出す QR を読むだけ。URL は `?s=<6桁コード>` の形。

## 鍵について

`index.html` に Supabase の **publishable key** が書いてある。これは**クライアントに露出する前提の鍵**で、
守っているのは鍵ではなく Row Level Security ポリシー。

- 開始前 / 終了後の押下はサーバーで弾かれる
- そのセッションに定義されたボタン以外の値は受け付けない
- 他人のセッションは読めない

`sb_secret_...` と旧 `service_role` は含まれていない。

## 更新の仕方

本体は [Tsutawari](https://github.com/hitomunn/Tsutawari) の `web/` にある。**あちらが正。**
直したらこちらにコピーして push する。
