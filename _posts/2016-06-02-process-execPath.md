---
layout: post
title:  "[vscode] Stable or Insiders build どちらを使っているか判定してみる
categories: vscode
---

Visual Studio Code でエクステンションを作っている時に、そのエクステンションが動作する vscode が Stable build なのか Insider build なのかを判断するにはどうすればいいか？
判別できる API などあればいいけど、なさそうなので。

とりあえず、process.execPath か process.title から割り出す方法を考えてみた。
ファイル名に Insiders と入っているからだけど、変更されたらダメなパターン。

Mac OS X の例。

## Stable Build

```bash
> process.title
"/Applications/Visual Studio Code.app/Contents/Frameworks/Electron Helper.app/Contents/MacOS/Electron Helper"

>process.execPath
"/Applications/Visual Studio Code.app/Contents/Frameworks/Electron Helper.app/Contents/MacOS/Electron Helper"
```

## Insiders Build

```bash
> process.execPath
"/Applications/Visual Studio Code - Insiders.app/Contents/Frameworks/Electron Helper.app/Contents/MacOS/Electron Helper"

> process.title
"/Applications/Visual Studio Code - Insiders.app/Contents/Frameworks/Electron Helper.app/Contents/MacOS/Electron Helper"
```

## こんなんでいいですかね？

```js
    // Stable or Insiders build? 
    if ((process.execPath).match(/Insiders/)) {
      console.log('Insiders 使ってますね ');
    } 
```
