---
title: カスタムコードテンプレート
lang: ja
---

## 概要

VS Code で Apex クラスなどのメタデータオブジェクトを作成する際に、カスタムテンプレートを使用して独自のコードテンプレートをソースファイルにすばやく追加します。テンプレートは、カスタムコードを含むファイルです。カスタムテンプレートを使用して、次の操作を実行できます。

- プロジェクト内の新しいファイルにデフォルトの著作権情報を追加する。
- Aura または LWC にデフォルトのコードを追加して、新しい Apex クラスを有効にする、など。

**注**:
この [Git リポジトリのサブディレクトリ](https://github.com/forcedotcom/salesforcedx-templates/tree/main/src/templates)には、メタデータコンポーネントの Salesforce 公式のテンプレート集があります。このディレクトリにリストされているファイルに加えられた更新のみが、VS Code のソースファイルに表示されます。このサブディレクトリをコピーするか、ローカルに複製することができます。このとき、同じフォルダ構造を維持してください。コードに関連するテンプレートファイルを更新し、上書きしたくないファイルを削除するだけです。

## デフォルトのテンプレートの場所を設定する

テンプレートのファイルはローカルのディレクトリか GitHub のプロジェクト内に保存することができます。`org-custom-metadata-templates` 設定変数を使用して、カスタムテンプレートの場所を設定します。

1. VS Code 内のターミナルから、`sf config set org-custom-metadata-templates <GitHub repo or local template directory>` コマンドを実行します。
2. `sf config list` コマンドを実行して、設定が更新されていることを確認します。

**注:** `<project-folder>/.sfdx` フォルダにある `sfdx-config.json` は、 `"customOrgMetadataTemplates": "<GitHub repo or local template directory>"` の形式で新しい行が追加されます。

設定変数に関する詳細は、Salesforce CLI 設定ガイドの[『設定変数』](https://developer.salesforce.com/docs/atlas.ja-jp.sfdx_setup.meta/sfdx_setup/sfdx_dev_cli_config_values.htm)を参照してください。

## テンプレートの場所の設定例

- `sf config set org-custom-metadata-templates https://github.com/vscodeuser/salesforcedx-templates/tree/main/src/templates/` は `org-custom-metadata-templates` 設定変数をユーザー `vscodeuser` の GitHub リポジトリのディレクトリに設定します。
- `sf config set org-custom-metadata-templates /Users/vscodeuser/CustomTemplateProject/MyCustomTemplates` は、`org-custom-metadata-templates` 設定変数を、ローカルマシンの `MyCustomTemplates` ディレクトリに設定します。

## GitHub 上のカスタムテンプレートを使用する

1. この [Git リポジトリのサブディレクトリ](https://github.com/forcedotcom/salesforcedx-templates/tree/main/src/templates)をクローンします。
2. クローンしたリポジトリで、使用したいテンプレートを含むフォルダ以外のすべてのフォルダを削除します。
3. リポジトリ内のカスタムテンプレートを更新します。
4. `org-custom-metadata-templates` がこのリポジトリを指していることを確認します。

## ローカルのカスタムテンプレートを使用する

Salesforce 拡張機能では、テンプレートがこのリポジトリとまったく同じフォルダ構造と命名体系に従う必要があります。CLI を使用してメタデータオブジェクトのテンプレートを指定する場合、このような制限はありません。

1. VS Code のプロジェクトディレクトリに、カスタムテンプレートを保存するためのフォルダーを作成します。フォルダーに、たとえば "MyCustomTemplates " などのわかりやすい名前を付けます。
2. この [git リポジトリ内](https://github.com/forcedotcom/salesforcedx-templates/tree/main/src/templates)のフォルダとファイル名を注意深く確認し、カスタマイズするファイルを含む同じ名前のサブフォルダを作成します。例えば、デフォルトの Lightning コントローラ JavaScript ファイルをカスタマイズするには、`lightningapp` という名前のサブフォルダを作成し、`DefaultLightningController.js` という名前のファイルを追加します。また、Apex クラスにカスタムコードを追加するには、`apexclass` という名前のサブフォルダを作成し、`DefaultApexClass.cls` という名前のファイルを追加します。
3. カスタムテンプレートファイルを更新します。
4. `org-custom-metadata-templates` がカスタムテンプレートディレクトリを指していることを確認します。

## GitHub 上のリモートテンプレートを更新する

VS Code は、テンプレートのリポジトリに初めてアクセスされた際にテンプレートファイルをローカル (`~/.sfdx/custom-templates` on macOS/Linux or `%USERPROFILE%\.sfdx\custom-templates` on Windows) にダウンロードします。更新されたテンプレートを使用するには、ローカルにキャッシュされたファイルをクリアしてテンプレートファイルを再度ダウンロードしてください。

## ローカルテンプレートを更新する

テンプレートの場所がマシン上にある場合、テンプレートに加えた変更は保存後すぐに使用できるようになります。変更がすぐに表示されない場合は、VS Code ウィンドウを更新して VS Code のキャッシュをクリアし、変更が反映されていることを確認してください。
