3. Build the Geolocation App Using Salesforce CLI
=================================================

この章では、CLI を使って Apex や Lightning Component を作成します。  
が、コードをすべて追っていると時間もかかりますし、DX の使い方からは逸れてしまうので今回は豪快にショートカットします。

このモジュールで作成するアプリケーションは別のモジュール  
[取引先の地理位置情報アプリケーションを作成する | Salesforce Trailhead](https://trailhead.salesforce.com/ja/projects/account-geolocation-app)  
のものらしいので、興味があればそちらに挑戦しましょう。

https://github.com/zaki-yama/sfdx-trailhead

を clone または zip でダウンロードし、`geolocation/force-app/main/default` 以下の

* aura
* classes
* staticresources
* tabs

の 4 つのディレクトリを、開発中のプロジェクトの `force-app/main/default` 以下にコピーします。

コピーしたら、 `force:source:push` で push してみましょう。

```
$ sfdx force:source:push
=== Pushed Source
STATE  FULL NAME                                     TYPE                  PROJECT PATH
─────  ────────────────────────────────────────────  ────────────────────  ────────────────────────────────────────────────────────────────────────
Add    AccountController                             ApexClass             force-app/main/default/classes/AccountController.cls
Add    AccountController                             ApexClass             force-app/main/default/classes/AccountController.cls-meta.xml
Add    leaflet                                       StaticResource        force-app/main/default/staticresources/leaflet.resource
Add    leaflet                                       StaticResource        force-app/main/default/staticresources/leaflet.resource-meta.xml
Add    Account_Locator                               CustomTab             force-app/main/default/tabs/Account_Locator.tab-meta.xml
Add    AccountList/AccountList.cmp                   AuraDefinitionBundle  force-app/main/default/aura/AccountList/AccountList.cmp
Add    AccountList/AccountList.cmp                   AuraDefinitionBundle  force-app/main/default/aura/AccountList/AccountList.cmp-meta.xml
Add    AccountList/AccountList.css                   AuraDefinitionBundle  force-app/main/default/aura/AccountList/AccountList.css
Add    AccountList/AccountListController.js          AuraDefinitionBundle  force-app/main/default/aura/AccountList/AccountListController.js
Add    AccountList/AccountListHelper.js              AuraDefinitionBundle  force-app/main/default/aura/AccountList/AccountListHelper.js
Add    AccountList/AccountListRenderer.js            AuraDefinitionBundle  force-app/main/default/aura/AccountList/AccountListRenderer.js
Add    AccountListItem/AccountListItem.cmp           AuraDefinitionBundle  force-app/main/default/aura/AccountListItem/AccountListItem.cmp
Add    AccountListItem/AccountListItem.cmp           AuraDefinitionBundle  force-app/main/default/aura/AccountListItem/AccountListItem.cmp-meta.xml
Add    AccountListItem/AccountListItem.css           AuraDefinitionBundle  force-app/main/default/aura/AccountListItem/AccountListItem.css
Add    AccountListItem/AccountListItemController.js  AuraDefinitionBundle  force-app/main/default/aura/AccountListItem/AccountListItemController.js
Add    AccountListItem/AccountListItemHelper.js      AuraDefinitionBundle  force-app/main/default/aura/AccountListItem/AccountListItemHelper.js
Add    AccountListItem/AccountListItemRenderer.js    AuraDefinitionBundle  force-app/main/default/aura/AccountListItem/AccountListItemRenderer.js
Add    AccountLocator/AccountLocator.cmp             AuraDefinitionBundle  force-app/main/default/aura/AccountLocator/AccountLocator.cmp
Add    AccountLocator/AccountLocator.cmp             AuraDefinitionBundle  force-app/main/default/aura/AccountLocator/AccountLocator.cmp-meta.xml
Add    AccountLocator/AccountLocator.css             AuraDefinitionBundle  force-app/main/default/aura/AccountLocator/AccountLocator.css
Add    AccountLocator/AccountLocatorController.js    AuraDefinitionBundle  force-app/main/default/aura/AccountLocator/AccountLocatorController.js
Add    AccountLocator/AccountLocatorHelper.js        AuraDefinitionBundle  force-app/main/default/aura/AccountLocator/AccountLocatorHelper.js
Add    AccountLocator/AccountLocatorRenderer.js      AuraDefinitionBundle  force-app/main/default/aura/AccountLocator/AccountLocatorRenderer.js
Add    AccountMap/AccountMap.cmp                     AuraDefinitionBundle  force-app/main/default/aura/AccountMap/AccountMap.cmp
Add    AccountMap/AccountMap.cmp                     AuraDefinitionBundle  force-app/main/default/aura/AccountMap/AccountMap.cmp-meta.xml
Add    AccountMap/AccountMap.css                     AuraDefinitionBundle  force-app/main/default/aura/AccountMap/AccountMap.css
Add    AccountMap/AccountMapController.js            AuraDefinitionBundle  force-app/main/default/aura/AccountMap/AccountMapController.js
Add    AccountMap/AccountMapHelper.js                AuraDefinitionBundle  force-app/main/default/aura/AccountMap/AccountMapHelper.js
Add    AccountMap/AccountMapRenderer.js              AuraDefinitionBundle  force-app/main/default/aura/AccountMap/AccountMapRenderer.js
Add    AccountsLoaded/AccountsLoaded.evt             AuraDefinitionBundle  force-app/main/default/aura/AccountsLoaded/AccountsLoaded.evt
Add    AccountsLoaded/AccountsLoaded.evt             AuraDefinitionBundle  force-app/main/default/aura/AccountsLoaded/AccountsLoaded.evt-meta.xml
```

と大量に表示されれば OK です。

## 参考：Apex や Lightning Component などを作成するコマンド

Apex や Lightning Component, Visualforce を新規作成するコマンドは以下です。

```zsh
# Apex
$ sfdx force:apex:class:create -n AccountController -d force-app/main/default/classes

# Lightning Component
$ sfdx force:lightning:component:create -n AccountListItem -d force-app/main/default/aura

# Visualforce
$ sfdx force:visualforce:page:create -n AccountListPage -d force-app/main/default/pages
```

いずれも `-n` で名前を、 `-d` で保存場所を指定します。

> 空のファイルが作成されるだけなので正直使う必要ないんじゃないかと...


## おつかれさまでした！

ほとんど何もやってない感ありますが、この章はこれで終了です。  
Challenge だけ解答しときましょう。
