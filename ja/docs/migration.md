---
title: マイグレーション
---
## RSS

まず、`hexo-migrator-rss`プラグインをインストールします。

``` bash
$ npm install hexo-migrator-rss --save
```

プラグインをインストールしたら、次のコマンドを実行してRSSからすべての投稿を移行します。`source`はファイルパスまたはURLで指定します。

``` bash
$ hexo migrate rss <source>
```

## Jekyll

Jekyllの `_posts` フォルダー内にあるすべてのファイルを、`source/_posts`フォルダーに移動させます。

そして、`_config.yml`にある`new_post_name`の設定を変更します：

``` yaml
new_post_name: :year-:month-:day-:title.md
```

## Octopress

Octopressの`source/_posts`フォルダー内にあるすべてのファイルを、`source/_posts`フォルダーに移動させます。

そして、`_config.yml`にある`new_post_name`の設定を変更します：

``` yaml
new_post_name: :year-:month-:day-:title.md
```

## WordPress

まず、`hexo-migrator-wordpress`プラグインをインストールします。

``` bash
$ npm install hexo-migrator-wordpress --save
```

WordPressのダッシュボードから"Tools" → "Export" → "WordPress"と移動し、WordPressのサイトをエクスポートします（詳細については、[WordPress サポートページ](http://en.support.wordpress.com/export/)を参照してください）。

そして以下を実行します:

``` bash
$ hexo migrate wordpress <source>
```

`source`にはWordPressのエクスポートファイルに対するファイルパスかURLを指定します。

## Joomla

まず、`hexo-migrator-joomla`プラグインをインストールします。

```bash
$ npm install hexo-migrator-joomla --save
```

[J2XML](http://extensions.joomla.org/extensions/migration-a-conversion/data-import-a-export/12816?qh=YToxOntpOjA7czo1OiJqMnhtbCI7fQ%3D%3D)コンポーネントを使用して、Joomlaの記事をエクスポートします。

そして以下を実行します:

```bash
$ hexo migrate joomla <source>
```

`source`にはJoomlaのエクスポートファイルに対するファイルパスかURLを指定します。
