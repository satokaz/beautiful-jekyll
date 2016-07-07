---
layout: post
title:  "[vscode] Visual Studio Code Insiders の Markdown サポート"
---


# markdown-it 


## 気が付いたこと

* markdown-it plugin を追加することはできない

* スペースを含んだ PATH を link で扱えない
  これは、markdown-it を採用したことにより commonmark spec に準拠することになったため。commonmark spec ではスペースを含むことは許されていないため。
  * [can not Markdown preview an image file that contains a space in the file name #7871](https://github.com/Microsoft/vscode/issues/7871)
