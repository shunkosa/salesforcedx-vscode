---
title: コードビルダーの設定
lang: ja
---

コードビルダーを有効にすると、サポートされている Salesforce エディションにコードビルダー管理パッケージをインストールするために必要な権限を利用できるようになります。

### サポートされているエディション

**次で使用可能**: Enterprise、Performance、Professional、および Unlimited エディションの Lightning Experience

Code Builder isn't available in sandboxes. However, during the development lifecycle, you can deploy code from Code Builder in a supported edition to a sandbox.

**次で使用不可能**: 欧州連合 (EU) オペレーティングゾーン。EU オペレーティングゾーンは強化されたレベルのデータレジデンシーコミットメントを提供する特別な有料サービスです。コードビルダーは、標準の製品利用規約に従って、EU オペレーティングゾーンに含まれない EU 内の組織でサポートされます。

## コードビルダーを有効化しインストールする

Professional Edition の組織にコードビルダーをインストールするには、組織に API アクセス権が必要です。API アクセスなしでコードビルダーを Professional Edition 組織にインストールしようとすると、インストールエラーが発生します。API アドオンをリクエストするには、アカウントエグゼクティブに連絡してください。

**注**: Government Cloud Plus 組織でコードビルダーを有効化すると、組織はセキュリティ認可境界の外にデータを送信できるようになります。詳細は担当のアカウントエグゼクティブに連絡してください。

1. [設定] から [クイック検索] に「`コードビルダー`」と入力し、**[コードビルダー]** を選択します。

2. コードビルダーを有効化し、製品条件を確認して同意すると、パッケージのインストールが可能になります。コードビルダーがすでにインストールされている場合、設定を無効にすると、コードビルダーアプリケーションにアクセスできなくなります。

3. **パッケージのインストール** をクリックします。
   インストーラの起動後、最新バージョンのコードビルダー管理パッケージをインストールするためのインストールプロセスが表示されます。パッケージの再インストールやアップグレードは、この設定ページに戻って行うことができます。

4. **すべてのユーザーのインストール** を選択し、**インストール** をクリックします。

5. サードパーティアクセスを承認し、**次へ** をクリックします。

コードビルダーダッシュボードがアプリケーションランチャーから利用可能になります。チームメンバーに適切なコードビルダーの権限セットを割り当ててください。

## コードビルダーがインストールされたことを確認する

インストールが完了すると、確認のメールが届きます。インストール済パッケージの設定画面からインストールを確認することもできます。

設定からクイック検索ボックスに `インストール済パッケージ` と入力し、**インストール済パッケージ** を選択します。次のようなコードビルダーの行が表示されます。アプリケーションのインストールに時間がかかっている場合は、**Done (完了)** をクリックするとこのページに自動的にリダイレクトされます。

![インストール済みパッケージ](./images/installed_package.png)

## コードビルダーの組織にユーザーとしてチームメンバーを追加する

コードビルダーは、ユーザーベースのライセンスを通してアクセスでき、[Identity](https://help.salesforce.com/s/articleView?id=sf.users_license_types_available.htm&type=5) ライセンスまたは [Free Limited Access](https://help.salesforce.com/s/articleView?id=release-notes.rn_sfdx_dev_hub.htm&release=218&type=5) ライセンスで動作します。

利用可能なコードビルダーライセンスの数は Salesforce のエディションに依存します。

| Salesforce エディション    | Professional | Enterprise | Unlimited | トライアル組織                                   |
| -------------------------- | ------------ | ---------- | --------- | ------------------------------------------------ |
| コードビルダーユーザーの数 | 10           | 40         | 100       | 組織のエディションが<br>コードビルダーを含む場合 |

**Note**: 追加のコードビルダーのユーザライセンスはスクラッチ組織のアドオン購入の一部として利用可能です。各スクラッチ組織アドオン毎に 1 つのコードビルダーユーザライセンスが付与されます。[『Salesforce Add-on Pricing (英語)』](https://www.salesforce.com/content/dam/web/en_us/www/documents/pricing/all-add-ons.pdf)を参照してください。

コードビルダー組織にまだユーザーではないチームメンバーを追加する手順は次の通りです。

1. コードビルダーの組織にログインします。
2. 設定から、クイック検索ボックスに `ユーザー` と入力し、**ユーザー**を選択します。
3. **New User (新規ユーザー)** または **Add Multiple Users (複数のユーザーの追加)** をクリックします。
4. ユーザーのロールに基づいて適切なライセンス種別を選択します。
5. **Generate passwords and notify user via email (パスワードをリセットしてメールで通知する)** チェックボックスをチェックします。
6. **Save (保存)** をクリックします。

**注**: この手順により、新しいユーザーを組織に招待するメールが送信されます。ただし、コードビルダーの設定が完了するまで、組織内でユーザーが実行できる操作はほとんどありません。チームにコードビルダーを設定していることを知らせ、ログインする前に連絡を待つように伝えることをお勧めします。

## 権限を割り当てる

システム管理者としてユーザー権限を割り当てる手順は次の通りです。

1. 設定から、クイック検索に `Permission Set Groups (権限セットグループ)` と入力し、**権限セットグループ** を選択します。
2. **CodeBuilderGroup** をクリックします。
3. **Manage Assignments (割り当ての管理)** をクリックします。
4. **Add Assignments (割り当てを追加)** をクリックします。
5. 権限セットグループを割り当てるユーザの名前の隣のチェックボックスをチェックし、**Next (次へ)** をクリックします。
6. **Assign (割り当て)** をクリックします。

これでユーザはアプリケーションランチャーから **Code Builder** を起動できるようになります。

## コードビルダーを最新バージョンにアップグレードする

ほとんどの場合、コードビルダーの最新バージョンにアップグレードする作業は不要です。新しいパッケージバージョンがリリースされると、組織が自動的に更新されます。

ただし、転送アップグレードが機能しなくなる場合があります。最新バージョンがない場合は、コードビルダーの設定ページからパッケージを手動でインストールすることをお勧めします。新しいバージョンが存在しない場合、パッケージインストーラーによって、最新バージョンがすでにあることが通知されます。

## その他のリソース

[Installing Packages](https://developer.salesforce.com/docs/atlas.en-us.appExchangeInstallGuide.meta/appExchangeInstallGuide/appexchange_install_installation.htm)

[権限セットの割り当ての管理](https://help.salesforce.com/s/articleView?id=sf.perm_sets_manage_assignments.htm&type=5&language=ja)

[ユーザーの表示および管理](https://help.salesforce.com/s/articleView?id=sf.admin_users.htm&type=5&language=ja)
[標準プロファイル](https://help.salesforce.com/s/articleView?language=ja&id=sf.standard_profiles.htm&type=5)
[ユーザーライセンス](https://help.salesforce.com/s/articleView?language=ja&id=sf.users_understanding_license_types.htm&type=5)
