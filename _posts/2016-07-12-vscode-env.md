---
layout: post
title:  "[vscode] locale が引き継がれないんじゃない。引き継ぐべきものがなかったのだ (OS X)"
date:   2016-07-12 08:00:33 +0900
---

知りませんでした。

※ Visuasl Studio Code 限定のお話ではありません

Visual Studio Code 1.3 (stable or Insiders) でターミナルへのコピペができなくなっていたり、環境変数 LANG が引き継がれなくて日本語ファイル名が文字化けしたりで、実装中だからそういうものかなと思っていたのだけど、そうじゃなかった。

OS X で vscode を起動する場合は、2 つの方法がある

  * OS X のターミナルから `code` or `code-insiders` で起動
  * Dock からアイコンをポチっ

ようは、前者は ~/.bashrc に環境変数 LANGが設定されているので、この環境変数が有効になっているターミナルから起動された vscode は、環境変数を持って起動してくる。  
なので、vscode のターミナルから環境変数を確認すると LANG が設定され、日本語のコピペが可能。
エディタ部分で選択された文字列を vscode のターミナルへ送信し実行させる `Terminal: Run Selected Text Active Terminal` でも、日本語を選択して実行できる。

一方、Dock から起動された vscode は、~/.bashrc に設定された環境変数を全て引き継いで起動するわけではないっぽく、LANG などは設定されていないので、起動した vscode は locale が `C` で起動する。一部の環境変数は設定されているので、LANG などは unset されるのかな？ 

そのため、vscode のターミナル内では日本語ファイル名などが文字化けするしコピペができない。と、判断してみた。

vscode のターミナルに IME から日本語入力できない件は、別問題。




## 一時的に設定する方法

OS X のターミナルで下記を実行してから、Dock から vscode を起動して vscode のターミナルで locale やコピペを確認してみる。(LANG=ja_JP.UTF-8 がセットされている)

```bash
$ launchctl setenv LANG ja_JP.UTF-8
```

確認方法: 

```bash
$ launchctl getenv LANG 
ja_JP.UTF-8
```

## 永続的に設定する方法

ログイン時から常に有効にするには、launchd を利用する方法。

`~/Library/LaunchAgents/environment.plist` を作成することで、設定される。

```bash
$ vi ~/Library/LaunchAgents/environment.plist
```

```plist
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
  <key>Label</key>
  <string>my.startup</string>
  <key>ProgramArguments</key>
  <array>
    <string>sh</string>
    <string>-c</string>
    <string>
    launchctl setenv LANG ja_JP.UTF-8
    </string>
  </array>
  <key>RunAtLoad</key>
  <true/>
</dict>
</plist>
Kazuyuki-no-MacBook-Pro:LaunchAgents satokaz$ 
```

## 参考

* [Setting environment variables via launchd.conf no longer works in OS X Yosemite/El Capitan?](http://stackoverflow.com/questions/25385934/setting-environment-variables-via-launchd-conf-no-longer-works-in-os-x-yosemite)
