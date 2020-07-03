---
title: 構成
---
サイトの設定を`_config.yml`または[代替の構成ファイル](#Using-an-Alternate-Config)で変更できます。

### サイト

設定項目 | 説明
--- | ---
`title` | ウェブサイトのタイトル
`subtitle` | ウェブサイトのサブタイトル
`description` | ウェブサイトの説明
`keywords` | ウェブサイトのキーワード。複数のキーワードはカンマ`,`で区切ります。
`author` | ウェブサイト作成者の名前
`language` | ウェブサイトの言語。[２文字のISO-639-1コード](https://ja.wikipedia.org/wiki/ISO_639-1%E3%82%B3%E3%83%BC%E3%83%89%E4%B8%80%E8%A6%A7)か、必要に応じて[コードの変形](/docs/internationalization)を使用します。デフォルトは`en`。
`timezone` | ウェブサイトのタイムゾーン。デフォルトではコンピューターの設定を使用します。利用可能なタイムゾーンのリストは[ここ](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)にあります。例：`America/New_York`, `Japan`, `UTC`.

### URL

設定項目 | 説明 | デフォルト値
--- | --- | ---
`url` | ウェブサイトのURL |
`root` | ウェブサイトのルートディレクトリ |
`permalink` | 記事の[パーマリンク](permalinks.html)形式 | `:year/:month/:day/:title/`
`permalink_defaults` | パーマリンクの各セグメントのデフォルト値 |
`pretty_urls` | [`permalink`](variables.html)変数の綺麗なURLへの書き換え設定 |
`pretty_urls.trailing_index` | `false`に設定すると末尾`index.html`を削除します。 | `true`
`pretty_urls.trailing_html` | `false`に設定すると末尾`.html`を削除します。 (_`index.html`の末尾には適用されません_)  | `true`

{% note info サブディレクトリのウェブサイト %}
あなたのウェブサイトがサブディレクトリにある場合（`http://example.org/blog`など）、`url`を`http://example.org/blog`に、`root`を`/blog/`に設定してください。
{% endnote %}

例:

``` yaml
# e.g. page.permalink is http://example.com/foo/bar/index.html
pretty_urls:
  trailing_index: false
# becomes http://example.com/foo/bar/
```

### ディレクトリ

設定項目 | 説明 | デフォルト値
--- | --- | ---
`source_dir` | ソースフォルダ。コンテンツが保存される場所 | `source`
`public_dir` | パブリックフォルダ。静的サイトが生成される場所 | `public`
`tag_dir` | タグディレクトリ | `tags`
`archive_dir` | アーカイブディレクトリ | `archives`
`category_dir` | カテゴリーディレクトリ | `categories`
`code_dir` | インクルードコードディレクトリ (`source_dir`のサブディレクトリ) | `downloads/code`
`i18n_dir` | i18n ディレクトリ | `:lang`
`skip_render` | レンダリングされずに`public`に直接コピーされるパス。パスマッチングには[glob形式](https://github.com/micromatch/micromatch#extended-globbing)を使用できます。

例:

``` yaml
skip_render: "mypage/**/*"
# `source/mypage/index.html` と `source/mypage/code.js` が変更されずに出力されます

## これは投稿を除外するためにも使用できます
skip_render: "_posts/test-post.md"
# `source/_posts/test-post.md`が無視されます
```

### 投稿の書き込み

設定項目 | 説明 | デフォルト値
--- | --- | ---
`new_post_name` | 新しい投稿のファイル名形式 | `:title.md`
`default_layout` | デフォルトのレイアウト | `post`
`titlecase` | タイトルをタイトルケースに変換するか？ | `false`
`external_link` | 外部リンクを新しいタブで開くか？ |
`external_link.enable` | 外部リンクを新しいタブで開くか？| `true`
`external_link.field` | 適用範囲が`site`全体か、`post`のみかを設定します | `site`
`external_link.exclude` | 除外するホスト名。適用する場合、`www`を含めてサブドメインを指定します。 | `[]`
`filename_case` | ファイル名の変換。`1`：小文字、`2`：大文字 | `0`
`render_drafts` | 下書きを表示するか？ | `false`
`post_asset_folder` | [アセットフォルダ](asset-folders.html)を有効にするか？ | `false`
`relative_link` | ルートディレクトリに関連付いたリンクを作成するか？ | `false`
`future` | 今後の投稿を表示するか？ | `true`
`highlight` | [highlight.js](https://highlightjs.org/)によるコードブロックのシンタックスハイライトを設定 |
`highlight.enable` | シンタックスハイライトの有効化 | `true`
`highlight.auto_detect` | 言語が指定されていない場合に自動検出を有効にします | `false`
`highlight.line_number` | 行番号を表示<br>_このオプションを有効にすると、`wrap`オプションも有効になります。_ | `true`
`highlight.tab_replace` | タブをn個のスペースで置き換えます。設定値が空の場合、タブは置き換えられません。 | `''`
`highlight.wrap` | コードブロックを[`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)タグでラップするか？ | `true`
`highlight.hljs` | CSSクラスに`hljs-*`プレフィックスを使用するか？ | `false`

### ホームページの設定

設定項目 | 説明 | デフォルト値
--- | --- | ---
`index_generator` | [hexo-generator-index](https://github.com/hexojs/hexo-generator-index)を利用して、投稿のアーカイブを生成します |
`index_generator.path` | ブログのインデックスページへのルートパス | `''`
`index_generator.per_page` | ページごとに表示される投稿数 | `10`
`index_generator.order_by` | 投稿を表示する順番。デフォルトでは日付の降順（新しいものから古いものへ）で並べ替えます。 | `-date`
`index_generator.pagination_dir` | URLのフォーマット。以下の[ページネーション](#Pagination)の設定を参照してください。 | `page`

### カテゴリー & タグ

設定項目 | 説明 | デフォルト値
--- | --- | ---
`default_category` | デフォルトのカテゴリー | `uncategorized`
`category_map` | カテゴリーのマッピング |
`tag_map` | タグのマッピング |

### 日付 / 時刻 の形式

Hexo は日付の処理に[Moment.js](http://momentjs.com/)を使用します。

設定項目 | 説明 | デフォルト値
--- | --- | ---
`date_format` | 日付のフォーマット | `YYYY-MM-DD`
`time_format` | 時刻のフォーマット | `HH:mm:ss`
`use_date_for_updated` | 更新日がfront-matterで提供されていない場合、[`post.updated`](/docs/variables#Page-Variables)中の投稿の日付を使用します。通常はGitワークフローで使用されます。 | `true`

### ページネーション

設定項目 | 説明 | デフォルト値
--- | --- | ---
`per_page` | 各ページに表示される投稿の数。`0`を設定するとページネーションが無効化されます。 | `10`
`pagination_dir` | URL フォーマット | `page`

例:
``` yaml
pagination_dir: 'page'
# http://yoursite.com/page/2

pagination_dir: 'awesome-page'
# http://yoursite.com/awesome-page/2
```

### 拡張

設定項目 | 説明
--- | ---
`theme` | テーマ名。`false`の場合、テーマを無効にします。
`theme_config` | テーマの構成。このキーの下にカスタムテーマの設定を含めることで、デフォルトのテーマを上書きします。
`deploy` | デプロイメントの設定
`meta_generator` | [メタジェネレーター](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta#Attributes) タグ。 `false`を設定するとタグの挿入を無効にします。


### ファイルやフォルダのインクルード/エクスクルード

以下のオプションを使用して、特定のファイルやフォルダを明示的に処理したり無視したりすることができます。パスマッチングには、[glob形式](https://github.com/micromatch/micromatch#extended-globbing)をサポートします。

`include` と `exclude` オプションは `source/` フォルダのみに適用されるのに対し、`ignore`オプションは全てのフォルダに適用されます。

設定項目 | 説明
--- | ---
`include` | 隠しファイルを含める (アンダースコアで始まるファイルやフォルダを含めて。ただし、*は除く)
`exclude` | ファイルやフォルダを除外する
`ignore` | ファイルやフォルダを無視する

例:
```yaml
# Include/Exclude Files/Folders
include:
  - ".nojekyll"
  # 'source/css/_typing.css'を含めます。
  - "css/_typing.css"
  # 'source/_css/'の中の全てのファイルを含めます.
  - "_css/*"
  # 'source/_css/'の中の全てのファイルとサブフォルダを含めます。
  - "_css/**/*"

exclude:
  # 'source/js/test.js'を除外します。
  - "js/test.js"
  # 'source/js/'の中の全てのファイルを除外します。
  - "js/*"
  # 'source/js/'の中の全てのファイルとサブフォルダを除外します。
  - "js/**/*"
  # 'source/js/'の中のファイル名が'test'で始まるファイルを全て除外します。
  - "js/test*"
  # 'source/js/'とこのサブフォルダ内に存在するファイルで、ファイル名が'test'で始まるファイルを全て除外します。
  - "js/**/test*"
  # 'source/_posts/'の中にある投稿を除外するために、この機能を使わないでください。
  # 投稿を除外するには、skip_renderを使用するか、ファイル名にアンダースコアを付加してください。
  # - "_posts/hello-world.md" # 動きません

ignore:
  # 'foo'という名前のフォルダを全て無視します。
  - "**/foo"
  # 'themes/'以下にある'foo'フォルダのみを無視します。
  - "**/themes/*/foo"
  # 上と同様ですが、'themes/'の全てのサブフォルダにも適用されます。
  - "**/themes/**/foo"
```

リストの各値は、シングルクォートかダブルクォートで囲む必要があります。

`include:` と `exclude:` は `themes/` フォルダには適用されません。`ignore:`を使用する代わりに、ファイル名やフォルダ名にアンダースコアを付加することでも除外することができます。

\* 注意すべき例外が `source/_posts` フォルダです。このフォルダに含まれるファイルとフォルダは、名前がアンダースコアで始まるものは無視されます。このフォルダに`include:`を適用することは非推奨です。

### 代替構成の使用

カスタム構成ファイルのパスは、`hexo`コマンドに`--config`フラグを追加することで指定できます。指定するファイルは、YAMLかJSONの代替構成ファイルか、複数のYAMLまたはJSONファイルのカンマ区切り（空白ではない）のリストです。

``` bash
# '_config.yml'の代わりに'custom.yml'を使用する
$ hexo server --config custom.yml

# 'custom.yml'と'custom2.json'を使用し、'custom2.json'を優先させる。
$ hexo server --config custom.yml,custom2.json
```

複数のファイルを使用すると、全ての構成ファイルが結合され、`_multiconfig.yml`にマージされた設定が保存されます。設定は後方のものが優先されます。任意の深さのオブジェクトを持つJSONまたはYAMLファイルをいくつでも使用可能です。**リストではスペースを使えない**ことに注意してください。

例えば、上記の例の場合、`custom.yml`に`foo: bar`の設定があり、`custom2.json`に`"foo": "dinosaur"`の設定があった場合、`_multiconfig.yml`には`foo: dinosaur`が設定されます。

### テーマ構成のオーバーライド

Hexoのテーマは、個別の`_config.yml`を使用した独立のプロジェクトです。

テーマをフォークして、設定でカスタムブランチを維持する代わりに、サイトのプライマリ構成ファイルからテーマを構成できます。

設定例:

```yml
# _config.yml
theme_config:
  bio: "My awesome bio"
```

```yml
# themes/my-theme/_config.yml
bio: "Some generic bio"
logo: "a-cool-image.png"
```

テーマ構成の結果:

```json
{
  bio: "My awesome bio",
  logo: "a-cool-image.png"
}
```
