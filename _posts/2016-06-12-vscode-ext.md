---
layout: post
title:  "[vscode] 勉強に利用した Visual Studio Code の Extension"
---

Visual Studio Code のエクステンション機能の source code を参考にして勉強している中で、Extensin そのものを修正してたりしてしまったので、記念にリスト化してみる。
いつのまにか、Extension のために Javascript や Typescript を勉強しはじめているオレがいた・・・

## Issue や PR したエクステンション

* vscode-pandoc
 * [https://github.com/dfinke/vscode-pandoc](https://github.com/dfinke/vscode-pandoc)
 * OS X での挙動確認とオプションを個別に記述できるように機能を追加。
   はじめて PR に挑戦。 
* Project Manager Extension for Visual Studio Code
 * [https://github.com/alefragnani/vscode-project-manager](https://github.com/alefragnani/vscode-project-manager)
  * こちらも Mac OS X で動作するようにお手伝い
* vscode-ext-yandex-translate
 * [https://github.com/airstep/vscode-ext-yandex-translate](https://github.com/airstep/vscode-ext-yandex-translate)
 * 日本語も変換候補として対応していたので追加してもらう
   * [Add "en-ja" and "ja-en" combinations](https://github.com/airstep/vscode-ext-yandex-translate/pulls?q=is%3Apr+is%3Aclosed)
* vscode-gist
 * [https://github.com/dbankier/vscode-gist](https://github.com/dbankier/vscode-gist)
 * secret gist が public gist になってしまう問題の対応
   * [PRIVATE gist is public #4](https://github.com/dbankier/vscode-gist/issues/4)
* MarkdownTOC(Table Of Contents) Plugin for Visual Studio Code.
 * [https://github.com/AlanWalk/Markdown-TOC](https://github.com/AlanWalk/Markdown-TOC)
 * codeblocks がエラーになるので、その対策を PR
   * [Fix : Interim fix for the codeblock](https://github.com/AlanWalk/Markdown-TOC/pulls)


## 自分で作ってみたエクステンション

* vscode-insert-date
  * [https://github.com/satokaz/insert-date](https://github.com/satokaz/insert-date)
  * カーソルがいる場所に日付と時刻を挿入するエクステンション。見よう見ままねで作成。
* vscode-toggleProxy
  * [https://github.com/satokaz/vscode-toggleProxy](https://github.com/satokaz/vscode-toggleProxy)
  * settings.json にある http.proxy 設定をステータスバーの地球アイコンで on/off するエクステンション。settings.json の入れ替え処理を atomic にできていない気がするので怖いひ・・・
  