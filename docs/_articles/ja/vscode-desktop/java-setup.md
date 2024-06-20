---
title: Java の設定
lang: ja
---

VS Code 向け Salesforce Apex 拡張機能に付属する Apex 言語サーバは、Java Platform, Standard Edition Development Kit \(JDK\) に依存しています。そのため、JDK バージョン 17 \(推奨\) と JDK バージョン 11 のいずれかのインストールが必要です。この拡張機能はデフォルトで、コンピュータ上の `JAVA_HOME` または `JDK_HOME` 環境変数を探し、ローカルの Java インストールを見つけようとします。拡張機能が Java インストールを見つけられない場合や、あなたが別のインストールを使用したい場合は、`salesforcedx-vscode-apex.java.home` 設定を変更します。

## JDK のダウンロードとインストール

JDK は以下の場所からダウンロードできます。

### Adoptium

[Adoptium](https://adoptium.net) は認証や複雑な手続きなしに、ビルド済みの OpenJDK バイナリを無料で提供しています。

1. [Adoptium](https://adoptium.net/?variant=openjdk17) に移動します。
2. 使用している OS および命令セットアーキテクチャに沿った最新のリリースをダウンロードします。
3. ダウンロードしたファイルを開き、インストール手順を実行します。

### Zulu

TCK テスト済みの無料の Zulu Java ビルドは、無制限にダウンロードして使用できます。

1. [Zulu のダウンロードページ](https://www.azul.com/downloads/zulu/)に移動します。
2. Java Version で **[Java 17 (LTS)]** を選択します。
3. Operating System で使用している OS を選択します。
4. Architecture 使用している命令セットアーキテクチャを選択します。
5. Java Package で JDK を選択します。
6. インストーラをダウンロードします。
7. ダウンロードしたファイルを開き、インストール手順を実行します。

### Oracle Java 17 \(正式にテスト済\)

1. [ダウンロードページ](https://www.oracle.com/java/technologies/downloads/)に移動します。
2. **[JDK 17]** タブの **[Download \(ダウンロード\)]** ボタンをクリックします。
3. 各自の OS に対応するダウンロードリンクをクリックします。
4. ログインを求められた場合は、Oracle アカウントを使用してログインする必要があります。
5. ダウンロードしたファイルを開き、インストール手順を実行します。

**注**: 実行可能ファイルからインストールすると、Java が標準の Java Home パス (C:\Program Files\) にインストールされ、JDK パスの設定が簡単になります。

## JDK パスの更新

salesforcedx-vscode-apex.java.home 設定を、Apex サーバの起動に使用される Java ランタイムのフルパス名に更新します。

1. **[File \(ファイル\)]** > **[Preferences \(基本設定\)]** > **[Settings \(設定\)]** \(Windows、Linux\) または **[Code \(コード\)]** > **[Preferences \(基本設定\)]** > **[Settings \(設定\)]** \(macOS\) を選択します。
2. `apex` を検索します。
3. `salesforcedx-vscode-apex.java.home` 設定を Java ランタイムのフルパス名に変更します。Java 実行可能ファイル自体には**設定しない**でください。

**注**: このパス名にはプロジェクトフォルダ内の場所を指定することはできません。また、Windows ではバックスラッシュはエスケープする必要があります。

![Apex の Java 設定](./images/apex-java-home-setting.png)

Java 11 または Java 17 ランタイムへのフォルダパスの例:

**MacOS**:

```json
{
  "salesforcedx-vscode-apex.java.home": "/Library/Java/JavaVirtualMachines/temurin-17.jdk/Contents/Home"
}
```

**Windows**:

```json
{
  "salesforcedx-vscode-apex.java.home": "C:\\Program Files\\Eclipse Adoptium\\jdk-17.0.2.8-hotspot"
}
```

**Linux**:

**Pop! OS 20.04 (installation via aptitude)**:

```json
{
  "salesforcedx-vscode-apex.java.home": "/usr/lib/jvm/java-17-openjdk-amd64"
}
```

**Arch Linux (installation via AUR using package `jdk17-adoptopenjdk`)**:

```json
{
  "salesforcedx-vscode-apex.java.home": "/usr/lib/jvm/java-17-adoptopenjdk"
}
```

## トラブルシューティングのヒント

- Java のバージョンがサポートされていないというエラーメッセージが表示された場合は、VS Code の下部にある Output タブを開いてください。'Apex' でフィルタリングします。また、'問題' タブで Apex 言語サーバが起動できていることを確認します。
- Windows の場合、JDK の場所へのパスが適切にエスケープされていることを確認してください。

  Java のバージョンが次のパスにある場合：

              `C:\Program Files\Java\jdk-17`

  Java Home のパスは次のようになります:

              `C:\\Program Files\\Java\\jdk-17`

## 高度な設定

デフォルトでは、JVM は、Apex 言語サーバのプロセスに対してシステムの物理メモリの 4 分の 1 までを割り当てます。もしより多くのメモリ要求を必要とするプロジェクトに取り組んでいる場合は、`salesforcedx-vscode-apex.java.memory` 設定を使用してデフォルト値を上書きしてください。この設定を使用して、メモリ割り当ての最大サイズをメガバイト単位でかつ、1024 の倍数で指定します。

```json
{
  "salesforcedx-vscode-apex.java.memory": 4096
}
```
