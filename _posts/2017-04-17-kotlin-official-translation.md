---
layout: post
title:  "公式サイトの訳を少し (Concise) "
date:   2017-04-17 08:27:22 + Asia/Tokyo
tags: メモ Kotlin
timezone: Asia/Tokyo
---

### Concise / スッキリ書ける（簡潔さ）

Drastically reduce the amount of boilerplate code you need to write.

それまで形式的にであっても記述しないといけなかったコードを劇的に減らすことができます。

Create a POJO with getters, setters, equals(), hashCode(), toString() and copy() in a single line:

gettersや, setters, equals(), hashCode(), toString() それから copy()といったメソッドを持つPOJO(Javaの一般的なオブジェクト)であれば、こんな具合に定義できます。

{% highlight kotlin %}
data class Customer(val name: String, val email: String, val company: String)
{% endhighlight %}

Or filter a list using a lambda expression:

それから、フィルタするなら一行だけのラムダ式で記載することもできます。

{% highlight kotlin %}
val positiveNumbers = list.filter {it > 0}
{% endhighlight %}

Want a singleton? Create an object:

シングルトンのオブジェクトが必要ですって？それもこんな感じで作れます。

{% highlight kotlin %}
object ThisIsASingleton {
    val companyName: String = "JetBrains"
}
{% endhighlight %}