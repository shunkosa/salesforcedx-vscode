---
title: パッケージ開発モデル
lang: ja
---

## パッケージ開発モデル

スクラッチ組織のようなソース追跡機能を持つ組織に対して開発を行う場合には、パッケージ開発モデルを使用します。このモデルは、ローカルのワークステーションとデフォルトの開発組織での変更を追跡します。パッケージ化されたメタデータのセットを使用して、組織間で変更を移行します。[Package Development Model](https://trailhead.salesforce.com/en/content/learn/modules/sfdx_dev_model) の Trailhead モジュールを参照してください。

## プロジェクトの作成

このモデルで開発を開始するには、以下の手順に従います。

1. VS Code のエディタを開き、コマンドパレットから、**SFDX: Create Project (SFDX: プロジェクトを作成)** を実行します。
   - 既存のプロジェクトで作業したい場合は、**File (ファイル)** > **Open (開く)** (macOS) / **File (ファイル)** > **Open Folder (フォルダを開く)** (Windows、Linux) を選択し、プロジェクトのディレクトリに移動します。VS Code で既存のプロジェクトを開く前に、プロジェクトに `sfdx-project.json` ファイルがあり、メタデータがソース形式であることを確認してください。
   - プロジェクトの構造についての情報は、『Salesforce DX 開発者ガイド』 の[「プロジェクトの設定」](https://developer.salesforce.com/docs/atlas.ja-jp.224.0.sfdx_dev.meta/sfdx_dev/sfdx_dev_workspace_setup.htm)を参照してください。
   - ソース追跡された組織で作業できるのは、メタデータがソース形式の場合のみです。[ソース形式](../user-guide/source-format)を参照してください。
2. コードエディターのサイドバーで、組織ピッカーをクリックすると、コマンドパレットが開きます。
3. **SFDX: Authorize an Org (組織を認証)** を実行します。Dev Hub がない場合は、『Salesforce DX 開発者ガイド』 の[「組織での Dev Hub の有効化」](https://developer.salesforce.com/docs/atlas.ja-jp.sfdx_setup.meta/sfdx_setup/sfdx_setup_enable_devhub.htm)を参照してください。
4. 組織ピッカーをクリックし、**SFDX: Create a Default Scratch Org (SFDX: デフォルトのスクラッチ組織を作成)** を実行し、開発用のデフォルトのスクラッチ組織を作成し設定します。
5. スクラッチ組織のシェイプを選択し、別名を入力し、スクラッチ組織の期限が切れるまでの日数を入力します。組織ピッカーにはスクラッチ組織に対して入力した別名が表示されます。サイドバーのブラウザアイコン ({% octicon browser %}) をクリックすると、作業しているデフォルトの組織を開くことができます。
   開発中のデフォルトの組織を変更するには、組織ピッカーをクリックして別の組織を選択してください。または、コマンドパレットを開いて、**SFDX: Authorize an Org (SFDX: 組織を認証)** または **SFDX: Create a Default Scratch Org (SFDX: デフォルトのスクラッチ組織を作成)** を実行してください。

### ソースのプッシュとプル

パッケージ開発モデルを使用すると、ローカルのプロジェクトとデフォルトの開発組織を同期させるのが簡単になります。パッケージ化されたメタデータのセットを使用して他の組織に変更をデプロイするので、手動で変更を追跡する必要はありません。
VS Code は、スクラッチ組織で作業していることをコンテキストとして認識しており、ソースを取得してデプロイするためのコマンドではなく、プッシュとプルのコマンドのみを提供します。

#### ソースのプッシュ

ソースを新しいスクラッチ組織にプッシュしたり変更を加えたりするには、**SFDX: Push Source to Default Scratch Org (SFDX: デフォルトのスクラッチ組織へソースをプッシュ)** を実行します。

プロジェクトの変更をスクラッチ組織の変更に上書きする場合は、**SFDX: Push Source to Default Scratch Org and Override Conflicts (SFDX: デフォルトのスクラッチ組織へソースをプッシュして競合を上書き)** を実行します。

#### ソースのプル

ブラウザで変更を行った後、**SFDX: Pull Source from Default Scratch Org (SFDX: デフォルトのスクラッチ組織からソースをプル)** を実行してプロジェクトを更新します。

スクラッチ組織の変更をプロジェクトの変更に上書きする場合は、**SFDX: Pull Source from Default Scratch Org and Override Conflicts (SFDX: デフォルトのスクラッチ組織からソースをプルして競合を上書き)** を実行します。

#### 変更の確認

ローカルの変更をスクラッチ組織にプッシュしたり、リモートの変更をローカルのプロジェクトにプルしたりする前に、出力パネルで変更内容を確認することができます。そのためには、コマンドパレットから **SFDX: View Changes in Default Scratch Org** を実行してください。
