---
layout: post
title:  "Visual Studio Code を使う上で良くわかっていなかった(基本的な)用語とか"
date:   2016-05-29 12:33:11 +0900
categories: vscode
---

(ちょっと Markdown の記述が変すぎたので、[markdownlint extension](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint) 入れて出直してみました)

Visual Studio Code を Markdown 以外で利用する機会があり、個人的に馴染みのない用語がたくさん出てきたので少しまとめてみた。
主に、Visual Studio Code Docs: [Editing Evolved](https://code.visualstudio.com/docs/editor/editingevolved) に記載されるもの。

マニュアルとしては、 [Get started with Visual Studio Code](https://code.visualstudio.com/Docs) になる。

## Visual Studio Code Insiders Build のマニュアル

また、[Insiders Build](https://code.visualstudio.com/download?insiders=true) と呼ばれる Early Access 版があり、こちらのマニュアルはどんどん更新されている。

* <https://github.com/Microsoft/vscode-docs/tree/vnext>

Visual Studio Code の Tips がまとめられた eBook が Microsoft から提供されていますので、こちらも併せてどうぞ。

* [eBook: Visual Studio Code - Tips & Tricks Vol. 1](https://www.microsoft.com/germany/techwiese/aktionen/visual-studio-code-ebook-download.aspx)
* [Visual Studio Code 1st Step Guide](Guidehttps://download.microsoft.com/download/3/6/F/36FE7C6C-2CDB-44B1-AB66-079E6E9DD219/Visual_Studio_Code_1st_Step_Guide_FullContents.pdf)

## Visual Studio Code の機能

### [Files, Folders & Projects](https://code.visualstudio.com/docs/editor/codebasics#_files-folders-projects)

---

Visual Studio Code は、ファイルまたはフォルダをベースとして扱うプロダクト。
folder の中に存在するファイル(package.json, project.json, tsconfig.json, or ASP.NET Core Visual Studio solution and project files)を判別して、色々と挙動を変えてるみたい。

###  [Command Palette](https://code.visualstudio.com/docs/editor/codebasics#_command-palette)

---

F1 キーや Ctrl/Cmd + Shit + P で上部に開く入力覧みたいなやつ。ここに、コマンドを入力したり選択したりで機能を呼び出す。

### [IntelliSense](https://code.visualstudio.com/Docs/editor/editingevolved#_intellisense) (インテリセンス)

---

  word/code completion 機能を提供する仕組み。Language Mode: JavaScript, JSON, HTML, CSS, Less, Sass, C# and TypeScript で利用できる。
  Visual Studio Code では、Microsoft が Open Source Software として提供する [OmniSharp](http://www.omnisharp.net) を利用している。

### [Snippets (スニペット) and Emmet Abbreviations](https://code.visualstudio.com/Docs/editor/editingevolved#_snippets-and-emmet-abbreviations) (エメット略語とでも言うのかな?)

---

Snippets は、定型文やちょっと直せば使えるような短いコードを挿入することが可能な機能。
Visual Studio Code では、ユーザ定義の snippet を作成することもできるし、エクステンションによる拡張もできる

* [Adding Snippets to Visual Studio Code](https://code.visualstudio.com/docs/customization/userdefinedsnippets)

Emmet は、独自の省略記法による HTML/CSS コーディングの高速化を提供する機能

様々な Editor plugin として提供されている。
Language Mode: HTML, Razor, CSS, Less, Sass, XML or Jade で利用可能。
[Emmet cheat sheet](http://docs.emmet.io/cheat-sheet/) で表記と展開例を見れる。

* [Emmet — the essential toolkit for web-developers](http://docs.emmet.io)
* [HTML/CSSを爆速コーディング Emmet入門](https://blogs.adobe.com/creativestation/serialization/web-learning-emmet)

ちょっと感動した。

### [Gutter indicators](https://code.visualstudio.com/Docs/editor/editingevolved#_gutter-indicators) (ガターインジケーター)

---

Git 連携してる際、下記のような印で

* 赤い三角は削除された行
* 緑のバーは新しく追加された行
* 青いバーは変更された行

変更の概要をルーラー部分に表示してくれる。

### [Reference information](https://code.visualstudio.com/Docs/editor/editingevolved#_reference-information)

---

  CodeLens とも言うのかな?
  インラインで参照情報を表示してくれるみたいだけど、Language Mode: C# のみサポート?
  設定で off にもできるとのこと。

### [Rename symbol](https://code.visualstudio.com/Docs/editor/editingevolved#_rename-symbol)

---

  シンボルのリネームだけど、ファイルをまたがって変更してくれる機能。コメント内のものは対象外となる。
  Language Mode: TypeScript と C# をサポート。

### [Code Action](https://code.visualstudio.com/Docs/editor/editingevolved#_reference-information)

---

  Language Mode: JavaScript と CSS でサポート。
  未定義の変数などのコードの下に電球(lightbulb)マークが表示され、クリックすることで解決策を提供してくれる

### [Peek](https://code.visualstudio.com/Docs/editor/editingevolved#_peek) (ピーク)

---

ウィンドウを切り替えることなく下記の情報を取得できる機能

* Shiftt + F12 で Reference Search (変数やオブジェクトの参照箇所を表示)
* Option + F12 で Peek Definition (変数やオブジェクトの定義を表示)

### [Hover](https://code.visualstudio.com/Docs/editor/editingevolved#_hover) (ホバー)

---

コードにマウスカーソルを重ねることで、シンボルのタイプや役立つ情報を表示してくれる機能
さらに Ctrl を押すと定義内容を表示してくれたり、クリックすることで定義にジャンプしてくれる

### [Task](https://code.visualstudio.com/docs/editor/tasks)

---

外部ツールを使い様々な作業の自動化を可能にする機能。
[Automating Markdown compilation](https://code.visualstudio.com/docs/languages/markdown#_automating-markdown-compilation) の例では、Markdown ファイルの変更を監視し変更が入ると自動的に HTML ファイルを生成するというもの。
gulp と gulp-markdown を組み合わせている。

## その他

* 別なファイルを選択してしまい、Active Window が上書きされた Ctrl + - を押すことで戻せる

* [Salsa](https://code.visualstudio.com/Updates#_javascript-salsa-preview)
  * Javascript 向けの IntelliSense 機能などを Typescript の機能で強化する実装。February update から default になる模様。
  * 設定や詳細は、こちら。[Visual Studio Code - NEW FEATURES: JavaScript - Salsa Preview](http://blogs.msdn.com/b/user_ed/archive/2016/02/09/visual-studio-code-new-features-javascript-salsa-preview.aspx)

* TextMate (.tmLanguage)

  ハイライトなどのカラースキームの定義？
  * .tmLanguage ファイルの解説？
    * <https://manual.macromates.com/ja/language_grammars>
  * [tmTheme Editor](http://tmtheme-editor.herokuapp.com/)
    * Color scheme editor for SublimeText, Textmate and a bunch of other text editors

  Visual Studio Code では、JSON または PLIST フォーマットをサポート。下記の実装が使われている。

  * [VSCode TextMate](https://github.com/Microsoft/vscode-textmate)

   Mac OS X には JSON <-> PLIST のコンバータとして使える plutil(1) コマンドがある。
   さらに、Xcode には、Property List Editor.app なるツールが含まれているとのこと。これだけ抜け出せないかな・・・<https://developer.apple.com/downloads/>

* TypeScript 型定義ファイル

  TypeScriptには、「型定義ファイル」と呼ばれる型情報のみを記述したスクリプトファイルを参照する仕組みが用意されている。
  JavaScript は型の定義を持たないため、TypeScript から Javascript ライブラリやフレームワークなどを利用する場合に必要になる。

  そのため、基本的には型定義ファイルを用意して開発を行うことになる。
  ファイル内では宣言のみ記載され、IntelliSense などでも利用される。
  自由に作成することも可能だし、用意されているものを利用することも可能。

* TypeScript Definition Manager (TSD)

  TypeScript 型定義ファイル管理ツール。

  * [TypeScript Definition manager for DefinitelyTyped](http://definitelytyped.org/tsd/)
  * [Node.js Applications with VS Code](https://code.visualstudio.com/Docs/runtimes/nodejs)

<!---
## メモ

* [Netbeans Emmet Plugin](http://plugins.netbeans.org/plugin/48315/emmet)
* http://download.emmet.io/org-lorenzos-emmet.nbm
-->