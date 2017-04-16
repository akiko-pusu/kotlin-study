---
layout: post
title:  "公式サイトの訳を少し"
date:   2017-04-17 08:27:22 + Asia/Tokyo
tags: メモ Kotlin
timezone: Asia/Tokyo
---

### Concise / スッキリ書ける（簡潔さ）

Drastically reduce the amount of boilerplate code you need to write.

それまで形式的にであっても記述しないといけなかったコードを劇的に減らすことができます。

Create a POJO with getters, setters, equals(), hashCode(), toString() and copy() in a single line:

gettersや, setters, equals(), hashCode(), toString() それから copy()といったメソッドを持つPOJO(Javaの一般的なオブジェクト)であれば、こんな具合に定義できます。

```
data class Customer(val name: String, val email: String, val company: String)
```

Or filter a list using a lambda expression:

それから、フィルタするなら一行だけのラムダ式で記載することもできます。

```
val positiveNumbers = list.filter {it > 0}
```

Want a singleton? Create an object:

シングルトンのオブジェクトが必要ですって？それもこんな感じで作れます。

```
object ThisIsASingleton {
    val companyName: String = "JetBrains"
}
```