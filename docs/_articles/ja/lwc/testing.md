---
title: Lightning Web コンポーネントのテスト
lang: ja
---

[`sfdx-lwc-jest`](https://developer.salesforce.com/docs/component-library/documentation/lwc/lwc.unit_testing_using_jest_installation) をインストールして、Lightning Web Components 用の Jest テストランナーを準備します。

## LWC のテストを探索する

LWC テストサイドバーは、書いたコードのテストを実行するための中心的な場所を提供します。1 つのテストケース、1 つのファイル内のテストケース、またはすべてのテストを実行することができます。また、最後に実行したテストの結果を表示したり、テストから直接対応するコード行に移動することもできます。テストサイドバーにアクセスするには、ビューバーのビーカーアイコン (ホバーテキスト: テスト) をクリックします。このアイコンが表示されない場合、VS Code で開いているプロジェクトがルートディレクトリに sfdx-project.json ファイルを含んでいることを確認してください。

選択したテストを実行するには、LWC テストビューから再生アイコンを表示するためにテストケースもしくはファイルの名前の上にカーソルを置きます。再生アイコン (ホバーテキスト: SFDX: Lightning Web コンポーネントテストケースの実行) をクリックすると、テストケースまたはファイル内のすべてのテストケースが実行されます。ビュー内のすべてのテストを実行するには、LWC テストビューの上部にある大きな再生アイコン (ホバーテキスト: SFDX: Lightning Web Component テストをすべて実行) をクリックします。

テスト結果は緑が合格、赤が不合格、オレンジがスキップされたテストです。

テストファイルやテストケースにジャンプするには、サイドバーのテスト名をクリックします。

テスト結果をクリアするには、サイドバー上部の更新アイコンをクリックします。 (ホバーテキスト: SFDX: Lightning Web Component テストエクスプローラを更新)

## Jest テストのデバッグ構成を追加する

Jest テストのデバッグ構成を追加して、`launch.json` を自動的に更新します。前提条件として、[node.js](https://nodejs.org/) と [npm](https://www.npmjs.com/get-npm) がインストールされている必要があります。

> **_注_** 空のプロジェクトから開始する場合、まず [sfdx-lwc-jest](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.unit_testing_using_jest_installation) をインストールし、説明されている手順に従ってテスト設定を追加します。

以下の手順で Jest テスト構成を追加します。

1. アクティビティバーから、**実行とデバッグ**に移動します。
2. ドロップダウンリストから、**構成の追加...**を選択します。
3. **Debug: LWC Jest Tests** を選択します。
4. 更新された `launch.json` を 保存します。
5. 構成のドロップダウンから、**Debug: LWC Jest Tests** を選択し、デバッグを開始します。

## ファイル内から Jest テストを実行、デバッグ、監視する

ファイル内のコンテキストアクション、またはエディタウィンドウの右上隅にあるメニューバーからボタンをクリックすることで、Jest ユニットテストを実行またはデバッグすることができます。ターミナルパネルでテスト結果を表示します。

#### Jest テストの実行

個々の Jest テストケースを実行するには、`.test.js` ファイルに移動し、Jest テストケースの定義の上に表示される **Run Test (テストを実行)** をクリックします。

![テストを実行 コードレンズを使用した LWC テストの実行](./images/lwc_test_run.gif)

Jest テストファイル内のすべてのテストケースを実行するには、エディタウィンドウの右上隅にある、メニューバーの再生アイコンをクリックします。

#### Jest テストのデバッグ

個々の Jest テストケースをデバッグするには、`.test.js` ファイルに移動し、Jest テストケースの定義の上にある **Debug Test (テストをデバッグ)** をクリックします。

![テストをデバッグ コードレンズを使用した LWC テストのデバッグ](./images/lwc_test_debug.gif)

Jest テストファイル内のすべてのテストケースをデバッグするには、エディタウィンドウの右上隅にあるメニューバーのデバッグアイコンをクリックします。

VS Code の組み込みデバッガが起動し、VS Code でテストをデバッグすることができます。[ブレークポイント](https://code.visualstudio.com/docs/editor/debugging#_breakpoints)を設定したり、[デバッグアクション](https://code.visualstudio.com/docs/editor/debugging#_debug-actions)でデバッグセッションを制御したり、[デバッグコンソール](https://code.visualstudio.com/docs/editor/debugging#_debug-console-repl)を使用して式を評価したりすることができます。

#### Jest テストの監視

Jest のテストファイルを監視するには、エディタウィンドウの右上隅にあるメニューバーの目のアイコンをクリックします。アイコンを切り替えると、監視を停止します。Jest テストファイルをウォッチしているときに、Jest テストファイルまたは Jest テストファイルがテスト対象としている LWC の JavaScript ファイルを編集すると、テストファイルが再実行されます。

![メニューバーボタンを使用した LWC テストの監視](./images/lwc_test_watch.gif)
