---
title: SOQL の例
lang: ja
---

このページは、コードビルダーまたは Salesforce 拡張機能を使用した VS Code で完了できるサンプルの SOQL タスクを含みます。このリストは今後も追加していきますので、このトピックをよく確認してください。

## ニューヨーク州に住所のある取引先のクエリを作成する

1. コマンドパレットから、**SFDX: Create Query in SOQL Builder** を実行し、SOQL クエリビルダーを開きます。
2. **ファイル > 保存** からファイルを保存します。拡張子の .soql を保持するようにしてください。
3. SOQL ビルダーとテキストエディタを切り替えるアイコンをクリックし(<img src="./images/go-to-file.svg">) SOQL ビルダーを再オープンします。
4. `From` 項目で、オブジェクトを検索し、`Account` オブジェクトを選択します。
5. `Fields` で、`Name`、`BillingState`、`BillingCountry` を選択します。
6. `Filter` 項目で、`AND` を選択し、以下の通り設定します。
   `BillingCountry = USA`
   `AND`
   `BillingState = NY`
7. **Run Query** をクリックします。

クエリ結果のタブが開きます。結果を `csv` または `json` 形式で保存することができます。

## リソース

ガイド:

- [SOQL SELECT の例](https://developer.salesforce.com/docs/atlas.ja-jp.soql_sosl.meta/soql_sosl/sforce_api_calls_soql_select_examples.htm)
- [Salesforce Object Query Language (SOQL)](https://developer.salesforce.com/docs/atlas.ja-jp.soql_sosl.meta/soql_sosl/sforce_api_calls_soql.htm)

Trailhead:

– [SOQL クエリを作成する](https://trailhead.salesforce.com/content/learn/modules/apex_database/apex_database_soql)
