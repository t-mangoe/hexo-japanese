---
title: タグプラグイン
---
タグプラグインは投稿タグとは異なります。Octopressから移植されたもので、特定のコンテンツを投稿に素早く追加するための便利な方法を提供します。

{% youtube I07XMi7MHd4 %}

## ブロック引用

著者や引用元、タイトル情報などを選択し、投稿に引用を追加するのに最適です。

**Alias:** quote

```
{% blockquote [author[, source]] [link] [source_link_title] %}
content
{% endblockquote %}
```

### 例

**引数なし。単純なブロック引用**

```
{% blockquote %}
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque hendrerit lacus ut purus iaculis feugiat. Sed nec tempor elit, quis aliquam neque. Curabitur sed diam eget dolor fermentum semper at eu lorem.
{% endblockquote %}
```

{% blockquote %}
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque hendrerit lacus ut purus iaculis feugiat. Sed nec tempor elit, quis aliquam neque. Curabitur sed diam eget dolor fermentum semper at eu lorem.
{% endblockquote %}

**本からの引用**

```
{% blockquote David Levithan, Wide Awake %}
Do not just seek happiness for yourself. Seek happiness for all. Through kindness. Through mercy.
{% endblockquote %}
```

{% blockquote David Levithan, Wide Awake %}
Do not just seek happiness for yourself. Seek happiness for all. Through kindness. Through mercy.
{% endblockquote %}

**Twitterからの引用**

```
{% blockquote @DevDocs https://twitter.com/devdocs/status/356095192085962752 %}
NEW: DevDocs now comes with syntax highlighting. http://devdocs.io
{% endblockquote %}
```

{% blockquote @DevDocs https://twitter.com/devdocs/status/356095192085962752 %}
NEW: DevDocs now comes with syntax highlighting. http://devdocs.io
{% endblockquote %}

**Webの記事からの引用**

```
{% blockquote Seth Godin http://sethgodin.typepad.com/seths_blog/2009/07/welcome-to-island-marketing.html Welcome to Island Marketing %}
Every interaction is both precious and an opportunity to delight.
{% endblockquote %}
```

{% blockquote Seth Godin http://sethgodin.typepad.com/seths_blog/2009/07/welcome-to-island-marketing.html Welcome to Island Marketing %}
Every interaction is both precious and an opportunity to delight.
{% endblockquote %}

## コードブロック

コードスニペットを投稿に追加するための便利な機能です。

**Alias:** code

```
{% codeblock [title] [lang:language] [url] [link text] [additional options] %}
code snippet
{% endcodeblock %}
```

追加オプションの指定は、`option:value`の形式で行います。e.g. `line_number:false first_line:5`。

追加オプション | 説明 | デフォルト
--- | --- | ---
`line_number` | 行番号を表示 | `true`
`highlight` | コードの強調表示を有効化 | `true`
`first_line` | 最初の行番号を指定 | `1`
`mark` | カンマ区切りで行を指定し、特定の行を強調表示します。ダッシュを使用して番号の範囲も指定できます。<br>例：`mark:1,4-7,10`は1,４~7,10をマークします。 |
`wrap` | [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)でコードブロックを囲みます | `true`

### 例

**単純なコードブロック**

```
{% codeblock %}
alert('Hello World!');
{% endcodeblock %}
```

{% codeblock %}
alert('Hello World!');
{% endcodeblock %}

**言語を指定**

```
{% codeblock lang:objc %}
[rectangle setX: 10 y: 10 width: 20 height: 20];
{% endcodeblock %}
```

{% codeblock lang:objc %}
[rectangle setX: 10 y: 10 width: 20 height: 20];
{% endcodeblock %}

**コードブロックにキャプションを追加**

```
{% codeblock Array.map %}
array.map(callback[, thisArg])
{% endcodeblock %}
```

{% codeblock Array.map %}
array.map(callback[, thisArg])
{% endcodeblock %}

**キャプションとURLを追加**

```
{% codeblock _.compact http://underscorejs.org/#compact Underscore.js %}
_.compact([0, 1, false, 2, '', 3]);
=> [1, 2, 3]
{% endcodeblock %}
```

{% codeblock _.compact http://underscorejs.org/#compact Underscore.js %}
_.compact([0, 1, false, 2, '', 3]);
=> [1, 2, 3]
{% endcodeblock %}

## バックティックコードブロック

コードブロックの使用と同じですが、代わりに3つのバックティックを使用してブロックを区切ります。

{% raw %}
&#96`` [language] [title] [url] [link text]
code snippet
&#96;``
{% endraw %}

## 抜粋

投稿に引用を追加します：

```
{% pullquote [class] %}
content
{% endpullquote %}
```

## jsFiddle

jsFiddleスニペットを埋め込みます：

```
{% jsfiddle shorttag [tabs] [skin] [width] [height] %}
```

## Gist

Gistスニペットを埋め込みます：

```
{% gist gist_id [filename] %}
```

## iframe

iframeを埋め込みます：

```
{% iframe url [width] [height] %}
```

## Image

指定したサイズの画像を挿入します。

```
{% img [class names] /path/to/image [width] [height] '"title text" "alt text"' %}
```

## Link

`target="_blank"`属性がついたリンクを挿入します。

```
{% link text url [external] [title] %}
```

## コードの挿入

`source/downloads/code`フォルダーにコードスニペットを挿入します。フォルダーの場所は、構成の`code_dir`オプションで指定可能です。

```
{% include_code [title] [lang:language] [from:line] [to:line] path/to/file %}
```

### 例

**test.jsのコンテンツ全体を埋め込む**

```
{% include_code lang:javascript test.js %}
```

**３行目のみを埋め込む**

```
{% include_code lang:javascript from:3 to:3 test.js %}
```

**5行目から8行目を埋め込む**

```
{% include_code lang:javascript from:5 to:8 test.js %}
```

**5行目からファイルの最後までを埋め込む**

```
{% include_code lang:javascript from:5 test.js %}
```

**1行目から8行目までを埋め込む**

```
{% include_code lang:javascript to:8 test.js %}
```

## YouTube

YouTubeビデオを挿入します。

```
{% youtube video_id %}
```

## Vimeo

レスポンシブまたは指定サイズのVimeoビデオを挿入します。

```
{% vimeo video_id [width] [height] %}
```

## 投稿を含める

他の投稿へのリンクを含めます。

```
{% post_path filename %}
{% post_link filename [title] [escape] %}
```

このタグを使用する場合は、言語や日付などのパーマリンクやフォルダ情報を無視できます。

例： `{% raw %}{% post_link how-to-bake-a-cake %}{% endraw %}`.

これは、投稿が`source/posts/2015-02-my-family-holiday`にあり、`2018/en/how-to-bake-a-cake`のパーマリンクがある場合でも、投稿のファイル名が`how-to-bake-a-cake.md`である限り機能します。

投稿のタイトルを表示する代わりに、表示するテキストをカスタマイズできます。マークダウン構文の`[]()`内での`post_path`の使用はサポートされていません。

投稿のタイトルとカスタムテキストはデフォルトでエスケープされています。エスケープを無効にすルには、`escape`オプションを使用します。

例：

**投稿のタイトルを表示**

`{% raw %}{% post_link hexo-3-8-released %}{% endraw %}`

{% post_link hexo-3-8-released %}

**カスタムテキストを表示**

`{% raw %}{% post_link hexo-3-8-released 'Link to a post' %}{% endraw %}`

{% post_link hexo-3-8-released 'Link to a post' %}

**タイトルのエスケープ**

```
{% post_link hexo-4-released 'How to use <b> tag in title' %}
```
{% post_link hexo-4-released 'How to use <b> tag in title' %}

**タイトルをエスケープしない**

```
{% post_link hexo-4-released '<b>bold</b> custom title' false %}
```
{% post_link hexo-4-released '<b>bold</b> custom title' false %}

## Assetsを含める

投稿のassetsを含めます。

```
{% asset_path filename %}
{% asset_img filename [title] %}
{% asset_link filename [title] [escape] %}
```

## Raw

特定のコンテンツが投稿の処理に問題を引き起こしている場合、`raw`タグでコンテンツをラップし、レンダリングエラーを回避できます。

```
{% raw %}
content
{% endraw %}
```


## 抜粋を投稿

`<!-- more -->`タグの前に配置されたテキストを投稿の抜粋として使用します。[front-matter](/docs/front-matter#Settings-amp-Their-Default-Values)にて`excerpt:`の値が指定されている場合、こちらが優先されます。

**例：**

```
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
<!-- more -->
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
```
