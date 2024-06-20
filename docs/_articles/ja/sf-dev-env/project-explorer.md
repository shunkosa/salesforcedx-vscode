---
title: プロジェクトエクスプローラー
lang: ja
---

Salesforce 開発の中心となるのは Salesforce DX プロジェクトです。プロジェクト構造には、デフォルトのパッケージ ディレクトリ **force-app** が含まれています。

```text
your-app
├── README.md
├── sfdx-project.json
├── .sfdx
├── .vscode
│   ├── extensions.json
│   └── settings.json
├── force-app
|   └── main
|       └── default
|           ├── aura
|           ├── classes
|           └── objects
└── manifest
    └── package.xml
```

プロジェクト内のフォルダについて知るには、[『Salesforce DX プロジェクトの構造とソース形式』](https://developer.salesforce.com/docs/atlas.ja-jp.sfdx_dev.meta/sfdx_dev/sfdx_dev_source_file_format.htm)を参照してください。

プロジェクト内で事前に入力されている標準ファイルには、次のようなものがあります。

- **.gitignore**: バージョン管理に Git を使い始めるのが簡単になります。
- **.prettierrc** and **.prettierignore**: Prettier を使用して Aura コンポーネントのフォーマットを簡単に開始できます。
- **.vscode/extensions.json** and **.vscode/launch.json**: Replay デバッガを構成して、より見つけやすく、使いやすくします。
- **.vscode/settings.json**: デフォルトでは、このファイルには保存時にプッシュまたはデプロイするための 1 つの設定があり、false に設定されています。この値を変更したり、他の設定を追加したりできます。
