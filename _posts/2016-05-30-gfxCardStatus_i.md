---
layout: post
title:  "gfxCardStatus を強化した gfxCardStatus.i"
date:   2016-05-30 07:48:00 +0900
categories: macbook
---

gfxCardStatus.i は、original の gfxCardStatus project:[codykrieger/gfxCardStatus](https://github.com/codykrieger/gfxCardStatus) から fork されたもの。
Integrated-Only mode への固定処理をより改善するいくつかの変更が追加されている。

最近、original gfxCardStatus の Integrated-Only mode 設定をスルーして、Discrete GPU へ切り替えるようなアプリケーションが増えてきている。
そのため、MacBook Pro 15' mid 2010 など NVIDIA GPU に起因するカーネルパニック問題を抱えている MacBook Pro ユーザーにとってはとてもありがたい。

* https://github.com/steveschow/gfxCardStatus