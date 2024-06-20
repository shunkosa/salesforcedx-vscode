---
title: コードビルダーの使用開始
lang: ja
---

## 概要

このクイックスタートを完了して、コードビルダーのインターフェイスに慣れ、コードビルダー環境でいくつかの簡単なタスクを実行します。開始する前に、[コードビルダーの概要](./ja/codebuilder/about)で詳細情報と重要な考慮事項を確認してください。

### 作業を保存することを忘れないようにする

クラウド上で作業することには利点があります。しかし、ローカルマシンにファイルを保存するデスクトップ上での作業と異なり、作業を永続的に保存するには、変更を組織にデプロイするか、ソース管理にコミットする必要があります。コードビルダー環境に保存された作業は戻ったときにそこにありますが、コードビルダーは永続的な長期保存には適していません。コードビルダーのブラウザタブを閉じる前に作業を保存することをお勧めします。

**注**: コードビルダー環境が 60 日間以上非アクティブになっている場合、その環境は削除されることがあります。

## コードビルダー環境を作成する

1. アプリケーションランチャーから、**コードビルダーダッシュボード** を開きます。

**注:** コードビルダーダッシュボードが表示されない場合、システム管理者に連絡して、適切なライセンスと権限セットが割り当てられているか確認してください。

2. **Launch (起動)** をクリックすると、コードビルダー環境が起動します。初めて起動するときには、新しい環境が作成されます。作業を開始できるように空の Salesforce DX プロジェクトも作成されます。新しい環境が作成されて読み込まれるまでには数分かかることに注意してください。“Welcome to Salesforce Code Builder (Salesforce コードビルダーへようこそ)” と表示されたら、すべての準備が整った状態です。

![コードビルダーダッシュボード](./images/cb_dashboard.png)

**ヒント**: コードビルダー環境を一度作成したら、いつでもダッシュボードから起動したり、ブックマークしてすばやくアクセスしたりできます。

**注**: `.bashrc`、`.profile`、および `.bash_logout` ファイルはコードビルダー環境を起動する度に上書きされます。これらのファイルの変更は失われるため、編集しないことをお勧めします。代わりに、新しく `.bashrc.local`、`.profile.local`、および `.bash_logout.local` ファイルを使用して、Dotfile の設定を行なってください。

## Salesforce 組織に接続する

次に、コードビルダー環境を組織に接続します。開発の途中で、異なるフェーズ毎に異なる種類の組織に接続することがあります。例えば、開発フェーズでは Developer Sandbox や Developer エディション組織に接続し、インテグレーション、テスト、ステージングのために他の Sandbox 種別に移動し、最後に、本番環境に変更をデプロイすることは一般的なユースケースです。コードビルダーではこれらのどの組織にも接続して、メタデータをデプロイまたは取得できます。

コードビルダーを初めて起動するときに組織に接続する手順は次の通りです。

1. コードビルダー環境で **Connect an Org (組織に接続)** をクリックして、作業したい Salesforce 組織に接続します。
2. ログイン URL を入力するか、ログインしたい組織を選択します。
3. 組織の別名を入力します。例えば、 dev_pro_sandbox や my_playground です。
4. テキストボックスにコードが表示されます。**Connect (接続)** をクリックします。
5. ユーザ名とパスワードを入力しログインします。**許可**をクリックします。
6. **続ける**をクリックします。これで組織に接続しました。コードビルダーのタブの下部にあるステータスバーに名前が表示されます。

現在の組織の名前をクリックし、コマンドパレットを呼び出し **SFDX: Authorize an Org (SFDX: 組織に接続)** を実行することで、接続する組織を変更することができます。

**注**: 組織を認証すると、その後の認証はコードビルダー側で処理されるため、継続的にログインし直す必要はありません。組織の名前をクリックし、リストから組織を選択するだけです。

## クイックツアーを開始する

これで、コードビルダーの開発環境に入りました。コードビルダーには豊富な IDE があり、拡張された Salesforce 拡張機能パックを通じて、Salesforce 固有の優れた開発ツールにアクセスできます。クイックツアーを行って、状況を把握しましょう。画面は次のようになります。

![code_builder_ui](./images/code_builder_ga_ui_dark.jpg)

コードビルダーのユーザーインターフェースは 5 つのエリアに分けられます。

**Activity Bar (アクティビティバー)**: 左側に位置し、さまざまなビューを切り替えるためのアイコンボタンがあります。この例では、エクスプローラービューがアクティブになっています。

**Side Bar (サイドバー)**: プロジェクトでの作業を支援するさまざまなビューが含まれています。たとえば、この例ではエクスプローラービューが表示されています。プロジェクト内の DX プロジェクト構造内のファイルが一覧表示されます。

**Editor (エディター)**: ファイルを編集するメインのエリアです。縦や横に並べて、好きなだけエディターを開くことができます。

**Panel (パネル)**: 出力やデバッグの情報、エラーと警告、統合されたターミナルを表示します。表示する出力を選択できます。

**Status Bar (ステータスバー)**: 開いているプロジェクトや編集しているファイルに関する情報を表示しいます。ステータスバーには接続している組織が表示されます。

## 組織について知る - 組織ブラウザを使用する

アクティビティバーをよく見ると、雲の形のアイコンがあります。このアイコンは組織ブラウザを表しています。これは Salesforce 拡張機能パックの一部です。組織ブラウザを使用すると、マニフェストファイルを使用せずに組織からメタデータを参照および取得できます。組織ブラウザを使用して、メタデータのソースをローカルのプロジェクトに取得します。

**詳細**: [組織ブラウザ](https://developer.salesforce.com/tools/vscode/en/user-guide/org-browser)についての詳細は Salesforce 拡張機能パックのドキュメントを参照してください。

![org_browser_small](./images/org_browser_small.jpg)

組織ブラウザをクリックして **Custom Objects** までスクロールします。最初に見えるオブジェクトは Account (取引先) です。**Account (取引先)** オブジェクトのメタデータを表示することができます。and do a few more cool things, but we’ll get to those in a bit.

## SOQL ビルダーを使用して最初のクエリを構築し実行する

Code Builder comes preloaded with everything you need to build and run a SOQL query.
Let’s build and run a simple SOQL query on the Account object:

コードビルダーには、SOQL クエリを構築して実行するために必要なものがすべてあらかじめロードされています。取引先オブジェクトで簡単な SOQL クエリを構築して実行してみましょう。

1. Ctrl+Shift+P (⇧⌘P) キーを押して、コマンドパレットを表示します。
2. 検索ボックスに “SOQL” と入力し、**SFDX: Create Query in SOQL Builder (SFDX: SOQL ビルダーでクエリを作成)** を選択します。
3. 次の通り選択します。

   a. **From** で**Account** オブジェクト

   b. **Fields** で **BillingState (請求先住所)** と **NumberofEmployees (従業員数)**

   c. **Run Query** を実行し、組織でシンプルな SOQL を実行します。

無題のファイルを閉じると、変更を保存するように求められます。

5. 変更を、“.soql” の拡張子のファイルで保存します。
6. 保存したクエリを再実行しましょう。ファイルを右クリックし、**ファイルを開くアプリケーションの選択…**を選択し、SOQL ビルダーを選択します。
   ファイルが SOQL ビルダーで開き、必要に応じてクエリを再実行または編集できます。

より複雑なクエリを構築するには、VS Code 向け Salesforce 拡張機能のドキュメントの [SOQL Builder](https://developer.salesforce.com/tools/vscode/ja/soql/soql-builder) を参照してください。

## カスタム項目を作成、取得、デプロイする

組織内のオブジェクトにカスタム項目を作成して、コードビルダーのプロジェクトにそのメタデータをプルしましょう。

最初にカスタム項目を作成しましょう。

1. **設定**から、**オブジェクトマネージャー**に移動し、**取引先**を選択します。
2. **項目とリレーション**を選択します。
3. **新規**をクリックします。
4. データ型で**日付**を選択し、**次へ**をクリックします。
5. 以下の通り埋めます。
   - 項目の表示ラベル: Created On
   - 一意の名前: createdon
   - 説明: Date of Account Creation
6. 項目が保存されるまで**次へ**をクリックします。

新しい項目のメタデータを取得しましょう。

1. コードビルダーに戻り組織ブラウザを開きます。
2. **Custom Objects** までスクロールし、**Account** を特定します。
3. Account コンポーネントの隣の取得アイコンをクリックすると、**SFDX: Retrieve Source from Org** が実行されます。
4. アクティビティバーから、エクスプローラーをクリックし `force-app/main/default/object/Account` を開きます。

`fields` フォルダの、`createdon_c.field-meta.xml` という名前のファイルに、新しいカスタム項目のメタデータが含まれていることが分かります！

参考までに取得されるメタデータは次の通りです。

```
<?xml version="1.0" encoding="UTF-8"?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
   <fullName>createdon__c</fullName>
   <description>Date of Account Creation</description>
   <externalId>false</externalId>
   <label>Created On</label>
   <required>false</required>
   <trackFeedHistory>false</trackFeedHistory>
   <type>Date</type>
</CustomField>
```

ここで、この項目に簡単な編集を加え、1 回のクリックで変更を組織にデプロイします。

1. `createdon_c.field-meta.xml` を編集し、この項目を必須項目にするため、`<required>` タグの値を `true` に変更します。
2. `objects/Account` フォルダを右クリックし、**SFDX: Deploy Source to Org (ソースを組織にデプロイ)** をクリックします。
3. コマンドが正常に実行されたら、組織に戻り、**Created On** カスタム項目の詳細を確認し、項目が必須項目になっていることを確認します。

## 新しい Lightning Web コンポーネントを作成しデプロイする

デプロイのもう 1 つのエクササイズとして、コードビルダーのプロジェクトでシンプルな Lightning Web コンポーネントをすばやく作成する方法を学びましょう。次に、1 つのコマンドを使用してこのコンポーネントを組織にデプロイします。では、始めましょう。

新しい Lightning Web コンポーネントを作成する手順は次の通りです。

1. Ctrl+Shift+P (⇧⌘P) を押し、**SFDX: Create Lightning Web Component** から新しい Lightning Web コンポーネントを作成します。
2. ここでは、コンポーネント名に `newCBComponent` と入力します。
3. **Enter** キーを押し、デフォルトのファイル位置を受け入れます。 (`force-app/main/default/lwc`).
4. **Enter** キーを押します。

`force-app/main/default/lwc/newCBComponent` フォルダに 3 つの新しいファイルが作成されます。

ファイルを次の通り更新します。

`newCBComponent.html` の内容を、次のコードをコピーアンドペーストして置き換えます。

```
<template>
    <p>Hello, {greeting}!</p>
    <lightning-input label="Name" value={greeting} onchange={handleChange}></lightning-input>
</template>
```

`newCBComponent.js` の内容を、次のコードをコピーアンドペーストして置き換えます。

```
import { LightningElement } from 'lwc';

export default class NewCBComponent extends LightningElement {
   greeting = 'Great going learning Code Builder!';
   changeHandler(event) {
       this.greeting = event.target.value;
   }
}

```

`newCBComponent.js-meta.xml` の内容を、次のコードをコピーアンドペーストして置き換えます。

<!-- prettier-ignore -->
```html

<?xml version="1.0" encoding="UTF-8"?>
<LightningComponentBundle xmlns="http://soap.sforce.com/2006/04/metadata">
   <apiVersion>54.0</apiVersion>
   <isExposed>true</isExposed>
   <targets>
   <target>lightning__AppPage</target>
   <target>lightning__RecordPage</target>
   <target>lightning__HomePage</target>
 </targets>
</LightningComponentBundle>

```

すべてのファイルを保存します。

このコンポーネントを組織にデプロイしましょう。

`force-app/main/default/lwc/newCBComponent` フォルダを右クリックして、**SFDX: Deploy Source to Org (SFDX: 組織にソースをデプロイ)** をクリックします。

出力ウィンドウに次のメッセージが表示されます。

```

=== Deployed Source
STATE    FULL NAME       TYPE                      PROJECT PATH
───────  ──────────────  ────────────────────────  ────────────────────────────────────────────────────────────────────
Created  newCBComponent  LightningComponentBundle  force-app/main/default/lwc/newCBComponent/newCBComponent.html
Created  newCBComponent  LightningComponentBundle  force-app/main/default/lwc/newCBComponent/newCBComponent.js
Created  newCBComponent  LightningComponentBundle  force-app/main/default/lwc/newCBComponent/newCBComponent.js-meta.xml

10:22:27.340 ended SFDX: Deploy Source to Org

```

2. **SFDX: Open Default Org (SFDX: デフォルトの組織を開く)** コマンドで組織にログインします。
3. **設定の Lightning コンポーネント** に移動して、`newCBComponent` 名前の新しい Lightning Web コンポーネントが利用可能であることを確認します。

おめでとうございます。新しい Lightning Web コンポーネントを作成してデプロイすることができました。

## リソース

コードビルダーで何ができるかについて詳しく知るには、以下のリソースを活用してください。

- [Visual Studio Code User Interface](https://code.visualstudio.com/docs/getstarted/userinterface) to get to know the Visual Studio code user interface.
- [Salesforce Extensions](https://developer.salesforce.com/tools/vscode) to learn about all the powerful features of the Salesforce Extension for VS Code.
