---
title: 書き込み
---

{% youtube AIqBubK6ZLc %}

新しい投稿または新しいページを作成するには、次のコマンドを実行します。

``` bash
$ hexo new [layout] <title>
```

`post`がデフォルトの`layout`ですが、独自のものを指定することも可能です。`_config.yml`の`default_layout`を編集することで、デフォルトのレイアウトを変更できます。

### レイアウト

Hexoには`post`、 `page` 、 `draft`の３つのレイアウトがあります。それぞれのレイアウトで作成されたファイルは、別々のパスに保存されます。新しく作成された投稿は`source/_posts`フォルダに保存されます。

レイアウト | パス
--- | ---
`post` | `source/_posts`
`page` | `source`
`draft` | `source/_drafts`

{% note tip 投稿を処理しないで！ %}
投稿を処理したくない場合は、front-matterで`layout: false`を設定します。
{% endnote %}

### ファイル名

デフォルトでは、Hexoは投稿のタイトルをファイル名として使用します。デフォルトのファイル名を変更する場合、`_config.yml`の`new_post_name`を編集します。例えば、`:year-:month-:day-:title.md`と設定すると、ファイル名の先頭に投稿の作成日を付加します。以下のプレースホルダーが使用可能です。

プレースホルダー | 説明
--- | ---
`:title` | 投稿のタイトル (小文字。スペースはハイフンに置き換え)
`:year` | 作成年。例：`2015`
`:month` | 作成された月（先行ゼロ）。例：`04`
`:i_month` | 作成された月（先行ゼロなし）。例：`4`
`:day` | 作成日（先行ゼロ）。例：`07`
`:i_day` | 作成日（先行ゼロなし）。例：`7`

### 下書き

以前、Hexoでの特別なレイアウトである`draft`について説明しました。このレイアウトで初期化された投稿は、`source/_drafts`フォルダに保存されます。`publish`コマンドを使うことで、下書きを`source/_posts`フォルダに移動できます。`publish`は`new`コマンドと同じように機能します。

``` bash
$ hexo publish [layout] <title>
```

下書きはデフォルトでは表示されません。Hexoの実行時に`--draft`オプションを追加するか、`_config.yml`の`render_drafts`を有効化すると、下書きをレンダリングできます。

### Scaffolds

投稿を作成するとき、Hexoは`scaffolds`フォルダ内の対応するファイルに基づいてファイルを作成します。例えば、以下：

``` bash
$ hexo new photo "My Gallery"
```

このコマンドを実行すると、Hexoは`scaffolds`フォルダから`photo.md`を検索し、それに基づいて投稿を作成します。次のプレースホルダーが、scaffoldsで使用可能です。

プレースホルダー | 説明
--- | ---
`layout` | レイアウト
`title` | タイトル
`date` | ファイル作成日
