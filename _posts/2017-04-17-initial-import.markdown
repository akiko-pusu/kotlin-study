---
layout: post
title:  "はじめのいっぽ"
date:   2017-04-17 00:27:22 + Asia/Tokyo
categories: メモ Kotlin
timezone: Asia/Tokyo
---
2017年春になりまして、新しい言語を覚えたいなあ...と思い、Kotlinにトライすることにしました。

ただ、この手のものは思い立っても三日坊主になりがち...。
せっかくなので、GitHub Pageを使って、少しずつ学習の記録をつけていこうと思います。


{% highlight kotlin %}
fun myCode() {
    var date: String = "2017-04-17"
    println("今日: ${date} から初めてみます！")
}

fun main(args:Array<String>) {
    myCode()
}

#=> 今日: 2017-04-17 から初めてみます！
{% endhighlight %}

なお、このメモは [Jekyll](http://jekyllrb.com)で記録していく予定です。

### 今日のお試し

- [http://kotlinlang.org](http://kotlinlang.org) （公式サイト）を少しだけ見る
- [Try Kotlin](http://try.kotlinlang.org) で、オンラインで上記の簡単なコードを試してみる

### Jekyllのメモ

- Jekyllで記載する場合、timezoneをメタデータで指定しないと、GitHub Page側での記事の生成日付がずれたりするので注意
