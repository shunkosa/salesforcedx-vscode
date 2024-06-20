---
title: デスクトップとの違い
lang: en
---

## Code Builder では何が違うか

Code Builder は、VS Code 向け Salesforce 拡張機能の機能を最大限に活用し、デスクトップ バージョンと同じ豊富な機能を提供します。デスクトップで VS Code を使用しているか、ブラウザから Code Builder を使用しているかに関係なく、アクセスする Salesforce 拡張機能は同じです。拡張機能は通常、アクセス方法に関係なく同じように機能しますが、注意すべき点がいくつかあります。

- Code Builder インスタンスはクラウドで実行されるため、そこからの組織の承認はデスクトップ バージョンとは異なる (デバイス) フローに従います。手順については、[別の組織に接続する](https://developer.salesforce.com/tools/vscode/ja/codebuilder/cb-start/#connect-to-a-different-org) を参照してください。
- Code Builder は管理パッケージとしてインストールされ、VS Code、Salesforce 拡張機能、Salesforce CLI など、必要なものがすべて付属しています。ローカルマシンにインストールする必要はありません。
- デスクトップ用の VS Code とは異なり、Code Builder から Microsoft Marketplace にアクセスすることはできません。代わりに、[Open VSX](https://open-vsx.org/) マーケットプレイスで入手可能な拡張機能を Code Builder 環境に追加できます。これは、使用可能な拡張機能に違いが生じる可能性があることを意味します。
- Code Builder では、サードパーティの認証シーケンスが異なります。
- Code Builder では、Salesforce 拡張機能が最新の状態に保たれます。ユーザー側で何もアクションを起こす必要はありません。

## 既知のギャップと不具合

既に検知されている不具合の一覧については、[既知のギャップと不具合 (英語)](https://github.com/forcedotcom/try-code-builder-feedback/wiki/Known-Gaps-and-Issues)を参照してください。

リストにない不具合を発見した場合、または最初の印象や機能リクエストなど、その他のフィードバックを提供したい場合は、GitHub リポジトリに [Issue を作成](https://github.com/forcedotcom/try-code-builder-feedback/issues)してください。どのような機能や改善があなたにとって重要なのかを理解したいと考えています。
