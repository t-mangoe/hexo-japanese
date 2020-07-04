---
title: コマンド
---
## init

``` bash
$ hexo init [folder]
```

Webサイトを初期化します。`folder`が指定されない場合、Hexoは現在のディレクトリにWebサイトをセットアップします。

## new

``` bash
$ hexo new [layout] <title>
```

新しい記事を作成します。`layout`が指定されない場合、Hexoは[_config.yml](configuration.html)の`default_layout`を使用します。`title`にスペースが含まれる場合、引用符で囲みます。

オプション | 説明
--- | ---
`-p`, `--path` | 投稿パス。投稿のパスをカスタマイズします。
`-r`, `--replace` | 現在の投稿がすでに存在している場合、置き換えます。
`-s`, `--slug` | slugを投稿します。投稿のURLをカスタマイズします。

デフォルトでは、Hexoは投稿のタイトルを使用してファイルのパスを定義します。ページ毎に、タイトルの名前のディレクトリが作られ、この中に`index.md`のファイルが作成されます。`--path`オプションを指定して、この動作を上書きし、ファイルパスを定義します。

```bash
hexo new page --path about/me "About me"
```

上記は、"About me"というタイトルがつけられたファイルを`source/about/me.md`に作成します。

タイトルは必須です。例えば、以下は期待する動作にはなりません。

```bash
hexo new page --path about/me
```

この場合、"page"というタイトルのファイルが`source/_posts/about/me.md`として作成されます。これは、引数が１つ（`page`）しかなく、デフォルトのレイアウトが`post`であるためです。

## generate

``` bash
$ hexo generate
```

静的ファイルを生成します。

オプション | 説明
--- | ---
`-d`, `--deploy` | 生成終了後にデプロイします。
`-w`, `--watch` | ファイルの変更を監視します。
`-b`, `--bail` | ファイル生成中に未処理の例外がスローされた場合、エラーを発生させます。
`-f`, `--force` | 強制的に再生成します。
`-c`, `--concurrency` | 並行して生成されるファイルの最大数。デフォルトは無限です。

## publish

``` bash
$ hexo publish [layout] <filename>
```

下書きを公開します。

## server

``` bash
$ hexo server
```

ローカルサーバーを起動します。デフォルトでは、`http://localhost:4000/`でアクセスできます。

オプション | 説明
--- | ---
`-p`, `--port` | デフォルトのポートを上書きします。
`-s`, `--static` | 静的ファイルのみを提供します。
`-l`, `--log` | ロガーを有効にします。ロガー形式をオーバーライドします。

## deploy

``` bash
$ hexo deploy
```

Webサイトをデプロイします。

オプション | 説明
--- | ---
`-g`, `--generate` | デプロイ前に生成します。

## render

``` bash
$ hexo render <file1> [file2] ...
```

ファイルをレンダリングします。

オプション | 説明
--- | ---
`-o`, `--output` | 出力先を指定します。

## migrate

``` bash
$ hexo migrate <type>
```

他のブログシステムからコンテンツを[移行](migration.html)します。

## clean

``` bash
$ hexo clean
```

キャッシュファイル(`db.json`)および生成されたファイル(`public`)を消去します。

## list

``` bash
$ hexo list <type>
```

全てのルートをリストします。

## version

``` bash
$ hexo version
```

バージョン情報を表示します。

## オプション

### セーフモード

``` bash
$ hexo --safe
```

プラグインとスクリプトの読み込みを無効にします。新しいプラグインのインストール後に問題が発生した場合、こちらを試してみてください。

### デバッグモード

``` bash
$ hexo --debug
```

詳細なメッセージを端末と`debug.log`に出力します。Hexoで問題が発生した場合は、こちらを試してみてください。エラーを見つけたときは、[GitHubにイシューを報告](https://github.com/hexojs/hexo/issues/new)してください。

### サイレントモード

``` bash
$ hexo --silent
```

端末への出力を無効にします。

### 構成ファイルパスのカスタマイズ

``` bash
$ hexo --config custom.yml
```

カスタム構成ファイルを使用します(`_config.yml`の代わりに)。JSONやYAML形式の構成ファイルのカンマ区切りのリストも指定可能です。この場合、リストのファイルは`_multiconfig.yml`に結合されます。

``` bash
$ hexo --config custom.yml,custom2.json
```

### 下書きの表示

``` bash
$ hexo --draft
```

投稿の下書きを表示します（下書きは`source/_drafts`に保存されています）。

### CWDをカスタマイズする

``` bash
$ hexo --cwd /path/to/cwd
```

現在の作業ディレクトリのパスをカスタマイズします。
