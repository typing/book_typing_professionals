# タイピング Professionals

このリポジトリは2011年の冬コミC81で頒布した「タイピング Professionals」本の原稿ファイルを管理しています。

## ビルド方法

docker コマンドが必要です。下記のコマンドを実行すると src ディレクトリの中に gachityipng.pdf ファイルが生成されます。

```sh
# eps ファイルを埋め込むために追加のライブラリを含めた独自の Docker image を作成
docker build -t texbuilder ./script/
# dvi ファイルの作成
docker run --rm -v $(pwd)/src:/workdir texbuilder platex gachityping.tex
# pdf ファイルの作成
docker run --rm -v $(pwd)/src:/workdir texbuilder dvipdfmx -d 5 -m 0.86 gachityping.dvi
```

## ライセンス

このリポジトリで管理しているファイルは著作権法第30条に定める「私的使用のための複製」の範囲内で自由に使用することができます。著作者の許可なく複製、再配布（自動公衆送信）、改変等に利用することはできません。
