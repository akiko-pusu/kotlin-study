---
layout: post
title:  "公式サイトの訳を少し (Safe)"
date:   2017-04-19 08:30:22 + Asia/Tokyo
tags: メモ Kotlin
timezone: Asia/Tokyo
---

### Safe / 安全であること

Avoid entire classes of errors such as null pointer exceptions.

NullPointerExceptionのような、あらゆるクラスに発生しうるエラーを防ぐことができます。

------

Get rid of those pesky NullPointerExceptions, you know, The Billion Dollar Mistake

Kotlinでは、10億ドル規模の損害を引き起こすような誤りを取り除くことができます。
たとえば、みなさんご存知の通り、NullPointerExceptionのように困ったエラーとか。

{% highlight kotlin %}
var output : String

/* ここで Null can not be a value of a non-null type String のエラーが出ます */
output = null
{% endhighlight %}

And of course, Kotlin protects you from mistakenly operating on nullable types, including those from Java

もちろん、Kotlinはこういった nullの値を取る可能性のある変数に対して、誤った操作を行ことを防いでくれます。


{% highlight kotlin %}
println(output.length())

/*
 実行するとこんなエラーが出ます：
 Only safe (?.) or non-null asserted (!!.) calls are allowed on a nullable receiver of type String
 Expression 'length' of type 'Int' cannot be invoked as a function. The function 'invoke()' is not found
*/
{% endhighlight %}

And if you check a type is right, the compiler will auto-cast it for you

それから、もし適切に型のチェックをしていれば、こんな具合にコンパイラが自動で型変換をしてくれます。

{% highlight kotlin %}
fun calculateTotal(obj: Any) {
    /* ここで型のチェックをしてOKだった場合に処理、とか */
    if (obj is Invoice) {
        obj.calculateTotal()
    }
}
{% endhighlight %}

--------

The Billion Dollar Mistake =>「10億ドル規模の損失をもたらす過ち」

参考:
- http://www.buildinsider.net/column/iwanaga-nobuyuki/011
- https://ja.wikipedia.org/wiki/アントニー・ホーア