---
title: セットアップ
---

{% youtube 0m2HnATkHOk %}

Hexoがインストールされたら、ターゲットの`<folder>`に次のコマンドを実行し、Hexoを初期化します。

``` bash
$ hexo init <folder>
$ cd <folder>
$ npm install
```

初期化が完了すると、プロジェクトフォルダーは次のようになります。

``` plain
.
├── _config.yml
├── package.json
├── scaffolds
├── source
|   ├── _drafts
|   └── _posts
└── themes
```

### _config.yml

サイトの [構成](configuration.html) ファイル。ここでほとんどの構成を設定できます。

### package.json

アプリケーションデータ。[EJS](https://ejs.co/)と[Stylus](http://learnboost.github.io/stylus/)、[Markdown](http://daringfireball.net/projects/markdown/)の各レンダラーはデフォルトでインストールされています。必要に応じて、あとでアンインストールできます。

``` json package.json
{
  "name": "hexo-site",
  "version": "0.0.0",
  "private": true,
  "hexo": {
    "version": ""
  },
  "dependencies": {
    "hexo": "^3.8.0",
    "hexo-generator-archive": "^0.1.5",
    "hexo-generator-category": "^0.1.3",
    "hexo-generator-index": "^0.2.1",
    "hexo-generator-tag": "^0.2.0",
    "hexo-renderer-ejs": "^0.3.1",
    "hexo-renderer-stylus": "^0.3.3",
    "hexo-renderer-marked": "^0.3.2",
    "hexo-server": "^0.3.3"
  }
}
```

### scaffolds

[Scaffold](writing.html#Scaffolds) フォルダ。新規の投稿は、scaffoldフォルダのファイルを基に作成されます。

### source

ソースフォルダ。ここに、サイトのコンテンツを配置します。Hexoは隠しファイルと、名前の前に`_` (アンダースコア）がついたファイルおよびフォルダを無視します（`_posts`は除く）。レンダリング可能なファイル（MarkdownやHTMLなど）は処理されて`public`フォルダに入れられ、それ以外のファイルは単にコピーされます。

### themes

[テーマ](themes.html) フォルダ。Hexoはサイトのコンテンツとテーマを組み合わせることにより、静的なWebサイトを生成します。