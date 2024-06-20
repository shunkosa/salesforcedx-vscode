---
title: デスクトップとの違い
lang: en
---

## Code Builder では何が違うか

Code Builder は、VS Code 向け Salesforce 拡張機能の機能を最大限に活用し、デスクトップ バージョンと同じ豊富な機能を提供します。デスクトップで VS Code を使用しているか、ブラウザから Code Builder を使用しているかに関係なく、アクセスする Salesforce 拡張機能は同じです。拡張機能は通常、アクセス方法に関係なく同じように機能しますが、注意すべき点がいくつかあります。

- Because your Code Builder instance runs in the cloud, authorizing an org from it follows a different (device) flow than the desktop version. See [Connect to Different Org](https://developer.salesforce.com/tools/vscode/en/codebuilder/cb-start#connect-to-a-different-org) for steps.
- Code Builder is installed as a managed package, and it comes with everything you need: VS Code, Salesforce extensions, and Salesforce CLI. No installation required on your local machine.
- Unlike VS Code for desktop, you cannot access the Microsoft Marketplace from Code Builder. Instead, you can add extensions available in [Open VSX](https://open-vsx.org/) marketplace to your Code Builder environment. This means that you might see differences in the extensions that are available.
- The third-party authorization sequence is different in Code Builder.
- We keep the Salesforce extensions up to date for you in Code Builder. You don’t need to take any action.

## 既知のギャップと不具合

既に検知されている不具合の一覧については、[既知のギャップと不具合 (英語)](https://github.com/forcedotcom/try-code-builder-feedback/wiki/Known-Gaps-and-Issues)を参照してください。

リストにない不具合を発見した場合、または最初の印象や機能リクエストなど、その他のフィードバックを提供したい場合は、GitHub リポジトリに [Issue を作成](https://github.com/forcedotcom/try-code-builder-feedback/issues)してください。どのような機能や改善があなたにとって重要なのかを理解したいと考えています。
