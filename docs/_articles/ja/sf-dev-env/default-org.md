---
title: デフォルトの組織の変更または起動
lang: ja
---

VS Code 向け Salesforce 拡張機能は、開発用のデフォルトの組織として設定した組織に対してコマンドを実行します。[パッケージ開発モデル](./ja/user-guide/development-models/#package-development-model)では通常、デフォルトの組織はスクラッチ組織です。[組織開発モデル](./ja/user-guide/development-models/#org-development-model)では通常、Sandbox、Developer Edition \(DE\) 組織、Trailhead Playground のいずれかです。

開発に使用する組織を設定または変更するには、VS Code のフッターに表示されている組織名かコンセントアイコン \({% octicon plug %}\) をクリックします。次に、別の組織を選択するか、**[SFDX: Set a Default Org \(デフォルトの組織を設定\)]** を選択して、新しい組織を承認します。または、コマンドパレットを開き、**[SFDX: Authorize an Org \(SFDX: 組織を認証\)]** または **[SFDX: Create a Default Scratch Org \(SFDX: デフォルトのスクラッチ組織を作成\)]** を実行します。

デフォルトの組織を開いて、変更内容をテストしたり、宣言型ツールを使用できるようにするには、フッターのブラウザアイコン \({% octicon browser %}\) をクリックします。または、コマンドパレットを開き、**[SFDX: Open Default Org \(SFDX: デフォルトの組織を開く\)]** を実行します。

デフォルトの組織からログアウトするには、**[SDFX: Log Out from Default Org \(SFDX: デフォルトの組織からログアウト\)]** を実行します。
