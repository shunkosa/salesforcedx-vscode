---
title: Salesforce 拡張機能のインストール
lang: ja
---

## 概要

始める前に、必要なソフトウェアをコンピュータにインストールしてください。

## Visual Studio Code

macOS、Windows、Linux のいずれかを実行しているコンピュータに Visual Studio Code をインストールします。VS Code には[システム要件](https://code.visualstudio.com/docs/supporting/requirements)がさほどないため、大半のコンピュータで適切に機能します。

Visual Studio Code をインストールするには、<https://code.visualstudio.com> にアクセスし、緑の大きな **[Download \(ダウンロード\)]** ボタンをクリックします。ダウンロードが済んだら、インストーラを開き、手順に従ってインストールを完了します。Salesforce 拡張機能パックを必要な Visual Studio Code の最小バージョンは 1.82 です。

注: VS Code のバージョンを更新できない場合は、59.15.0 より前のバージョンの Salesforce 拡張機能パックを使用することをお勧めします。なお、これらの以前のバージョンの修正はサポートされないことに注意してください。

## Salesforce 拡張機能パック

ローカルで開発を行いたいですか？既に VS Code を使用していますか？Salesforce 拡張機能と Salesforce CLI をインストールすることで、Salesforce プラットフォームでの開発をより迅速かつ生産的に行うことができます。

<span>以下のリンクから VS Code と Salesforce 拡張機能パックをインストールしてください。 <span><br/><a class="slds-button slds-button_neutral landing__header-cta slds-m-vertical--x-large" href="https://code.visualstudio.com">Visual Studio Code のダウンロード</a><a class="slds-button slds-button_brand landing__header-cta slds-m-vertical--x-large" href="https://marketplace.visualstudio.com/items?itemName=salesforce.salesforcedx-vscode">Salesforce 拡張機能のインストール</a>

## Salesforce CLI

Salesforce CLI は、Salesforce 組織に対してコマンドを実行したり、ローカルマシン上のソースファイルを操作したりするために使用します。VS Code 向け Salesforce 拡張機能では Salesforce CLI をバックグラウンドで使用するため、CLI を直接使用する予定がなくても、マシンにインストールする必要があります。

Salesforce CLI のインストールについての詳細は、[『Salesforce DX 設定ガイド』](https://developer.salesforce.com/docs/atlas.en-us.sfdx_setup.meta/sfdx_setup/sfdx_setup_install_cli.htm)を参照してください。

## Java Platform, Standard Edition Development Kit

VS Code 向け Salesforce 拡張機能の一部の機能は、Java Platform, Standard Edition Development Kit \(JDK\) に依存しています。JDK のバージョン 11 またはバージョン 17 以降をインストールしている必要があります。詳細については、[Java の設定](./ja/getting-started/java-setup)を参照してください。
