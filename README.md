はじめての Salesforce DX ハンズオン資料
=======================================

この資料は [はじめての Salesforce DX ハンズオン - connpass](https://teamspirit.connpass.com/event/71116/) のために用意したものです。  
Trailhead の [App Development with Salesforce DX](https://trailhead.salesforce.com/ja/modules/sfdx_app_dev) の内容をおおむねなぞる形で構成されていますが、完全な和訳ではありません。

※[Convert and Deploy an Existing App](https://trailhead.salesforce.com/ja/modules/sfdx_app_dev/units/sfdx_app_dev_deploy) の単元がまだ含まれていません（2017/11/27 時点）

## ドキュメント URL

ドキュメントは https://zaki-yama.github.io/sfdx-getting-started/index.html で公開しています。


## ドキュメントをローカルで開発する場合

```zsh
# gitbook のインストール
$ yarn

# http://localhost:4000 でドキュメントを起動
$ yarn run gitbook serve

# docs/ にエクスポート
$ yarn run gitbook build ./ docs/
```
