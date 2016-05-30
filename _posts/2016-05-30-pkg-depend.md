---
layout: post
title:  IPS パッケージの依存関係だけを抜き出してみる
---

ターゲットとなる IPS パッケージが、どのようなパッケージに依存しているかを確認する。
pkg contents -m でもいいけど、depend だけを抜き出す方法。