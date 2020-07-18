---
title: Front-matter
---

{% youtube pfD6FCZdW4Q %}

Front-matterは、ファイルの先頭にあるYAMLまたはJSONのブロックで、書き込みの設定を構成するために使用されます。YAMLで記述した場合、Front-matterは３つのダッシュで記述を終了します。また、JSONで記述した場合は、３つのセミコロンで記述を終了します。

**YAML**
``` yaml
---
title: Hello World
date: 2013/7/13 20:46:25
---
```

**JSON**
``` json
"title": "Hello World",
"date": "2013/7/13 20:46:25"
;;;
```

### 設定とデフォルト値

設定項目 | 説明 | デフォルト値
--- | --- | ---
`layout` | レイアウト |
`title` | タイトル | ファイル名 (投稿のみ)
`date` | 公開日 | ファイル作成日
`updated` | 更新日 | ファイル更新日
`comments` | 投稿へのコメント機能を有効化 | true
`tags` | タグ (ページでは使用できません) |
`categories` | カテゴリー (ページでは使用できません) |
`permalink` | 投稿のデフォルトのパーマリンクを上書きします |
`keywords` | メタタグとオープングラフでのみ使用されるキーワード (非推奨) |
`excerpt` | プレーンテキストでのページの抜粋。テキストをフォーマットするには、[このプラグイン](https://hexo.io/docs/tag-plugins#Post-Excerpt)を使用する。 |

#### カテゴリーとタグ

投稿にのみ、カテゴリーとタグの使用がサポートされます。カテゴリーは投稿に対して順番に適用され、分類とサブ分類の階層になります。一方、タグは全て同じ階層レベルで定義されるため、タグの記載順は重要ではありません。

**例**

``` yaml
categories:
- Sports
- Baseball
tags:
- Injury
- Fight
- Shocking
```

複数のカテゴリー階層を適用する場合は、単一のカテゴリー名ではなく、カテゴリー名のリストを使用してください。Hexoがこの方法で定義されたカテゴリーを投稿中に見つけた場合、その投稿の各カテゴリーは独自の独立した階層として扱われます。

**例**

``` yaml
categories:
- [Sports, Baseball]
- [MLB, American League, Boston Red Sox]
- [MLB, American League, New York Yankees]
- Rivalries
```
