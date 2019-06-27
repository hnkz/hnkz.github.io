+++
title = "Distributed System of Apocalypse"
date = 2019-06-14

[taxonomies]
categories = ["distributed system", "研究", "進捗"]
tags = ["distributed system"]

+++

分散システムについて調べたことをまとめていきます。
- 分散システム資料やリンク

<!-- more -->

## 分散システム資料
- [https://gist.github.com/dominictarr/e804626e0bc4a75e9aa3](https://gist.github.com/dominictarr/e804626e0bc4a75e9aa3)
  - 分散システム入門資料が色々とまとめられていた

## 雑まとめ

### CAP定理
- [https://www.slideshare.net/kumagi/ss-81368169](https://www.slideshare.net/kumagi/ss-81368169)

- Consistency 
- Availability
- Partition Tolerance

上記３つのうち、２つまでしか満たすことができない、とする定理。
あ、なんかこの定理はだめらしいですね。

> あまりこの言説に振り回されてはいけない

### Fault Injection Test
わざと異常を起こして異常系のテストをするやつらしい

### Jepsen??
[https://jepsen.io/services](https://jepsen.io/services)

分散データベースの安全性向上を図る団体らしい

### errfs
ディスクをバグらせたように見せかけることができる

## 所感
- 分散システムは複雑なのでバグの仕込みどころがたくさんある
- え、分散システムむずそうwwwww無理wwwwwでもかっけえwwwwww

以上！
