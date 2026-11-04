# ひとつのろうそく（onecandle-chem.com）

日本語で学ぶ・教えるDP化学のサイトです。HTMLとCSSだけでできた静的サイトで、GitHub Pages でそのまま公開できます。

## フォルダ構成

```
index.html               トップページ
404.html                 ページが見つからないときの表示
CNAME                    独自ドメイン（onecandle-chem.com）
.nojekyll                GitHub Pages の変換処理を止めるための空ファイル
assets/site.css          各ページ共通の見た目
assets/bar.css           共通のヘッダー・フッター（ツールのページでも使用）
teaching/                授業と実験
tools/                   学習ツール
  command-terms/         指示用語の日英対訳と答え方
  uncertainty/           IA 不確かさ計算ツール
ia-guide/                IAガイド
practice/                実践記録
about/                   このサイトについて（利用条件・IBとの関係）
```

ページを追加するときは、同じフォルダ構成で `フォルダ名/index.html` を作ります。ヘッダーのメニューは、各ページの `<nav class="oc-nav">` の中にあります。

## 公開の手順

### 1. GitHub のアカウントを用意する
- アカウント名は本名を含まないものにする（例：`onecandle-chem`）
- Settings → Emails で「Keep my email addresses private」をオンにする

### 2. リポジトリを作ってファイルを上げる
1. 新しいリポジトリを作る（名前の例：`onecandle-chem`、公開設定は Public）
2. このフォルダの中身をすべてアップロードする（`.nojekyll` と `CNAME` も含める）

### 3. GitHub Pages を有効にする
1. リポジトリの Settings → Pages を開く
2. Source を「Deploy from a branch」、Branch を `main`、フォルダを `/ (root)` にして保存する
3. 「Custom domain」に `onecandle-chem.com` を入れて保存する

**独自ドメインは、DNSを設定する前にここで登録しておきます。** 先にDNSだけを設定すると、他人にサイトを乗っ取られるおそれがあります。

### 4. Xserverドメインで DNS レコードを設定する
「DNSレコード設定」で、次のレコードを追加します。

| 種別 | ホスト名 | 内容 |
|---|---|---|
| A | （空欄） | 185.199.108.153 |
| A | （空欄） | 185.199.109.153 |
| A | （空欄） | 185.199.110.153 |
| A | （空欄） | 185.199.111.153 |
| AAAA | （空欄） | 2606:50c0:8000::153 |
| AAAA | （空欄） | 2606:50c0:8001::153 |
| AAAA | （空欄） | 2606:50c0:8002::153 |
| AAAA | （空欄） | 2606:50c0:8003::153 |
| CNAME | www | `GitHubのアカウント名.github.io` |

- 「空欄」は、ドメインそのもの（onecandle-chem.com）を指す意味です。
- 最初から入っている同じ種別のレコード（Xserver のサーバーを指す A レコードなど）があれば削除します。
- 反映には最大24時間ほどかかります。

### 5. HTTPS をオンにする
DNS が反映されたら、Settings → Pages で「Enforce HTTPS」にチェックを入れます。

## 公開前の確認
- 勤務校の規定と、IA採点官の契約の確認が済んでいるか
- 利用条件（about ページの「利用条件」）を決めて書いたか
- お問い合わせ先（匿名で使えるメールアドレスやフォーム）を決めたか
