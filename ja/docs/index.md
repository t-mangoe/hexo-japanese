---
title: 概要
---
Hexo のドキュメントへようこそ。Hexo の使用中に問題が発生した場合は、[トラブルシューティングガイド](troubleshooting.html)を参照するか、[GitHub](https://github.com/hexojs/hexo/issues)でイシューを上げる、または[Google グループ](https://groups.google.com/group/hexo)でトピックを開始してください。

## Hexoとは?

Hexoは高速でシンプルかつ強力なブログフレームワークです。[Markdown](http://daringfireball.net/projects/markdown/)（または他のマークアップ言語）で投稿を書くと、Hexoは数秒で美しいテーマの静的ファイルを生成します。

## インストール

Hexoのセットアップには数分しかかかりません。問題が発生し、ここで解決策が見つからない場合は、[GitHubのイシューに送信](https://github.com/hexojs/hexo/issues)してください。

{% youtube ARted4RniaU %}

### 必要条件

Hexoのインストールは非常に簡単で、事前に必要なものは次のとおりです。

- [Node.js](http://nodejs.org/) (最低でもNode.js 8.10, 推奨は 10.0 以上)
- [Git](http://git-scm.com/)

お使いのコンピュータにこれらがインストール済みの場合、[Hexo のインストール](#Install-Hexo)のステップはスキップできます。

そうでない場合は、次の手順に従ってインストールを行ってください。

### Gitのインストール

- Windows: [git](https://git-scm.com/download/win)をダウンロードしてインストールします。
- Mac: [Homebrew](https://brew.sh/), [MacPorts](http://www.macports.org/) または [インストーラー](http://sourceforge.net/projects/git-osx-installer/)でインストールします。
- Linux (Ubuntu, Debian): `sudo apt-get install git-core`でインストールします。
- Linux (Fedora, Red Hat, CentOS): `sudo yum install git-core`でインストールします。

{% note warn Macユーザの皆さまへ %}
コンパイル時に問題が発生する場合ががあります。まずはApp StoreからXcodeをインストールしてください。インストール後、Xcodeを開き、**Preferences -> Download -> Command Line Tools -> Install**と移動してコマンドラインツールをインストールします。
{% endnote %}

### Node.jsのインストール

Node.js はほとんどのプラットフォームに[公式インストーラー](https://nodejs.org/en/download/)を提供しています。

その他のインストール方法:

- Windows: [nvs](https://github.com/jasongin/nvs/) (推奨)または[nvm](https://github.com/nvm-sh/nvm)でインストールします。
- Mac: [Homebrew](https://brew.sh/) または [MacPorts](http://www.macports.org/)でインストールします。
- Linux (DEB/RPM-based): [NodeSource](https://github.com/nodesource/distributions)でインストールします。
- その他: それぞれのパッケージマネージャーからインストールします。Node.jsから提供されている[ガイド](https://nodejs.org/en/download/package-manager/) を参照してください。

権限の問題を回避するために、MacおよびLinuxでもnvsを推奨します。

{% note info Windows %}
公式インストーラーを使用している場合、**PATHに追加**がオンになっていることを確認してください（デフォルトでオンになっています）。
{% endnote %}

{% note warn Mac / Linux %}
Hexoのインストール中に`EACCES`パーミッションエラーが発生した場合、npmjsより提供されている[回避策](https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally)に従ってください。root / sudoでのオーバーライドはお勧めしません。
{% endnote %}

### Hexoのインストール

必要なものが全てインストールできたら、npmを使ってHexoをインストールします。

``` bash
$ npm install -g hexo-cli
```

### 高度なインストールと使用法

上級ユーザーは`hexo`パッケージをインストールすることを好むかもしれません。

``` bash
$ npm install hexo
```

この方法でインストールした場合、次の２つの方法でHexoを実行できます。

1. `npx hexo <command>`
2. Linux ユーザーは`node_modules/`の相対パスを設定できます：

  ``` bash
  echo 'PATH="$PATH:./node_modules/.bin"' >> ~/.profile
  ```

  その後、`hexo <command>`でHexoを実行します。

### 互換性

古いNode.jsを使用している場合、Hexoの過去バージョンのインストールを検討してください。

注意：Hexoの過去バージョンに対するバグ修正は提供していません。

可能な限り、常に[最新バージョン](https://www.npmjs.com/package/hexo?activeTab=versions)のHexoと[推奨バージョン](#Requirements)のNode.jsをインストールすることを強く推奨します。

Hexoのバージョン | Node.jsの最低バージョン
--- | ---
4.1+ | 8.10
4.0 | 8.6
3.3 - 3.9 | 6.9
3.2 - 3.3 | 0.12
3.0 - 3.1 | 0.10 or iojs
0.0.1 - 2.8 | 0.10
