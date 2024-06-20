---
title: LWC 開発クイックスタート
lang: en
---

## 概要

アプリケーションに取引先責任者の名前と電話番号を表示する `contactList` と呼ばれる LWC コンポーネントを作成します。`ContactController` と呼ばれる Apex クラスから表示する取引先責任者の情報を取得します。

開始する前に, [デスクトップ向け Salesforce 拡張機能](./ja/vscode-desktop/install)をインストールするか、[コードビルダーを設定](./ja/codebuilder/cb-setup)してください。

### 取引先責任者をクエリする Apex クラスの追加

1. Salesforce DX プロジェクトがない場合は、VS Code で、コマンドパレットから **SFDX: Create Project (SFDX: プロジェクトの作成)** を実行して作成します。
2. LWC を追加したい組織にログインします。
3. コマンドパレットから、**SFDX: Refresh SObject Definitions (SFDX: SObject 定義の更新)** コマンドを実行して、SObject 関連コードの補完候補を取得します。
4. コマンドパレットから、**SFDX: Create Apex Class (SFDX: Apex クラスの作成)** を実行して、`ContactController` の名前で Apex クラスを作成します。

次にこのクラスに `getContacts` というメソッドを追加しましょう。このメソッドを public かつ static にします。これは静的メソッドなので、メソッドにアクセスするためにクラスのインスタンスを作成する必要はありません。クラス名の後にドット (`.`) とメソッド名を付けるだけです。このメソッドは、取引先責任者オブジェクトの項目群をクエリします。次のコードを `ContactController.cls` に貼り付けます。

```
public with sharing class ContactController {
    @AuraEnabled(cacheable=true)
    public static List<Contact> getContacts() {
        return [
SELECT
Id,
Name,
Email,
Phone
FROM Contact
WITH SECURITY_ENFORCED
LIMIT 10
];
    }
}

```

次に、クエリした項目を表示する LWC コンポーネントを追加します。

### 取引先責任者の情報を表示する LWC コンポーネントの作成

1. コマンドパレットから, run **SFDX: Create Lightning Web Component** and create a component called `contactList` in the default location.
2. `contactList.html` ファイルの内容を以下のコードに置き換え、ファイルを保存します。

```
<template>
    <lightning-card title="Contact List">
        <template if:true={contacts.data}>
            <template for:each={contacts.data} for:item="contact">
                <div class="slds-var-p-horizontal_medium" key={contact.Id}>
                    <p>{contact.Name}, {contact.Phone}</p>
                </div>
            </template>
        </template>
        <template if:true={contacts.error}>
            <p>{contacts.error}</p>
        </template>
    </lightning-card>
</template>

```

3. `contactList.js` ファイルの内容を以下のコードに置き換えて保存します。

```
import { LightningElement, wire } from 'lwc';
import getContacts from '@salesforce/apex/ContactController.getContacts';

export default class ContactList extends LightningElement {
    @wire(getContacts) contacts;
}
```

4. `contactList.js-meta.xml` ファイルの内容を以下のコードに置き換えて保存します。

```
<?xml version="1.0" encoding="UTF-8"?>
<LightningComponentBundle xmlns="http://soap.sforce.com/2006/04/metadata">
 	<apiVersion>57.0</apiVersion>
 	<isExposed>true</isExposed>
 	<targets>

   		<target>lightning__HomePage</target>
 	</targets>
</LightningComponentBundle>

```

5. `force-app/main` 下の default フォルダを右クリックして、and run **SFDX: 組織へソースをデプロイ** を選択し、コードを組織にデプロイします。

### Lightning Experience のアプリケーションに新しいコンポーネントを追加する

1. Visual Studio Code で、コマンドパレットを開き **SFDX: Open Default Org (SFDX: デフォルトの組織を開く)** を実行します。
   別のブラウザタブで組織が開かれます。
2. **アプリケーションランチャー**から**セールス**を検索し選択します。
3. 任意のレコードを開いた後、**設定**のギアアイコンをクリックし、**編集ページ**を選択します。編集メニューが表示されない場合は、**設定** > **ホーム**から**高度な営業ホーム**を無効化します。
4. 左サイドバーの、Lightning コンポーネントリストがあるカスタム領域から `contactList` Lightning Web コンポーネントをページキャンバスの上部にドラッグします。
5. **保存**をクリックします。
6. **有効化**をクリックします。
7. **組織のデフォルトとして割り当て**をクリックします。
8. **保存**をクリックします。
9. 再度**保存**をクリックし、**戻る**の矢印をクリックして元のページに戻ります。
10. ページを更新して新しいコンポーネントを確認します。

![LWC component を表示する PNG](./images/contact_lwc.png)
