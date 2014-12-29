title: ブログフレームワークHEXOの使い方
date: 2014-12-29 01:12:37
tags:
---
導入部分はこちらの記事がとてもよくまとまっているので、初めての方はLIGの記事を見ましょう.

- [所要時間3分!? Github PagesとHEXOで爆速ブログ構築してみよう！](http://liginc.co.jp/web/programming/server/104594)


----
## テーマの切り替え方について

ルートディレクトリでgitリポジトリを作り、gitignoreにthemeを追加しておく.
別途themeフォルダで、Hexoのテーマのリポジトリをgit cloneする.
![themeフォルダの位置](/2014/12/29/ブログフレームワークHEXOの使い方/hexoProjectTree.jpg)
テーマを切り替えたいときは、プロジェクトディレクトリ直下にある_config.ymlのthemeを希望のテーマ名に書き換える.
ちょっとハマったんですが、
**テーマを切り替えるときはhexo cleanを実行すること！**
でないとスタイルが崩れまくります.

``` bash
$ hexo clean
$ hexo generate
$ hexo deploy
```

----
## コミットについて
まだあまりHEXOを触ってないんですが、おそらくなのでメモ.
``` bash
$ hexo deploy -g
```
を実行すると、リモートリポジトリのgithub側でコミットも一緒にしてくれるので、
ローカルではgit commitを実行する必要はない. pullするだけで良いのだ.

``` bash
$ hexo deploy -g
$ git pull
```
じゃぁ下書きのやつはどこにコミットすりゃいいんだ!? と言われそうですが、パッと思いついたのはdevelopブランチとかにコミットすればいいんじゃないでしょうか？(developブランチのコミット見に行ったらもろバレですが...)

----
## 画像について.
markdownで画像を挿入する場合は、

1. _config.yml内のpost_asset_folderをtrueに設定.
2. Markdown記法の画像で、パスを**/YYYY/MM/DD/postName/imagename.jpg**と指定すればうまくいく.

