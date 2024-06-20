---
title: マニフェストビルダーの使用
lang: ja
---

## マニフェストを使用したプロジェクトの作成

1. VS Code エディタを開き、コマンドパレットから、**SFDX: Create Project with Manifest (SFDX: マニフェストを使用してプロジェクトを作成)** を実行します。

![プロジェクトを作成](./images/create-project-with-manifest.png)

2. コードエディターのステータスバーで、組織ピッカーをクリックしてコマンドパレットを開きます。認証済みの組織のリストから選択することも、新しい組織を認証することもできます。

VS Code で初めてプロジェクトを作成し、認証済みの組織がない場合は、組織ピッカーにはデフォルトの組織が未設定と表示されます。

3. **SFDX: Authorize an Org (SFDX: 組織を認証)** を実行し、ログイン URL (例えば Sandbox) を選択します。

![組織を認証](./images/authorize-org-command.png)

組織の別名を入力すると、ブラウザウィンドウが開きます。組織にログインし、アクセスを許可し、VS Code ウィンドウに戻ります。組織ピッカーには組織を認証する際に入力した別名が表示されます。

![組織ピッカー](./images/org-picker.png)

### マニフェスト (`package.xml`) ファイル

Sandbox、DE 組織、または Trailhead Playground に接続したら、package.xml ファイルを使用して組織からメタデータを取得します。SFDX: Create Project with Manifest (SFDX: マニフェストファイルを使用してプロジェクトを作成) コマンドを実行すると、package.xml ファイルが作成されます。取得したい様々なメタデータ型をこのファイルに追加します`package.xml` ファイル内の様々なメタデータのサブセットの操作方法については、『メタデータ API 開発者ガイド』の [package.xml マニフェストファイルのサンプル](https://developer.salesforce.com/docs/atlas.ja-jp.api_meta.meta/api_meta/manifest_samples.htm) を参照してください。

### マニフェストビルダー

package.xml ファイルを手動で編集する代わりに、指定されたメタデータコンポーネントセットのマニフェストファイルを自動的に生成します。

1.  エクスプローラビューで、マニフェストの生成に使用するコンポーネントを右クリックして選択します。
2.  **SFDX: Generate Manifest File (SFDX: マニフェストファイルを生成)** を実行します。
3.  マニフェストファイルの一意の名前 (XML の拡張子を含めない) を入力します。

新しいファイルが作成されマニフェストフォルダに追加されます。

新しいマニフェストファイルを使用して、**SFDX: Deploy Source in Manifest to Org (SFDX: マニフェストファイルのソースを組織にデプロイ)** または **SFDX: Retrieve Source in Manifest from Org (SFDX: マニフェストファイルのソースを組織から取得)** コマンドを使用して、組織からソースをデプロイおよび取得します。
