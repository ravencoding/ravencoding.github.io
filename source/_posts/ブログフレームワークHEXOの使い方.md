title: ブログフレームワークHEXOの使い方
date: 2014-12-29 01:12:37
tags:
---
テーマの切り替え方についてメモ.
導入部分はこちらの記事がとてもよくまとまっているので、初めての方はLIGの記事を見ましょう.

- [所要時間3分!? Github PagesとHEXOで爆速ブログ構築してみよう！](http://liginc.co.jp/web/programming/server/104594)

ルートディレクトリでgitリポジトリを作り、gitignoreにthemeを追加しておく.
別途themeフォルダで、Hexoのテーマのリポジトリをgit cloneする.
![tree](img/hexoProjectTree.jpg)
テーマを切り替えたいときは、プロジェクトディレクトリ直下にある_config.ymlのthemeを希望のテーマ名に書き換える.
ちょっとハマったんですが、
**テーマを切り替えるときはhexo cleanを実行すること！**
でないとスタイルが崩れまくります.

``` bash
$ hexo clean
$ hexo generate
$ hexo deploy
```
