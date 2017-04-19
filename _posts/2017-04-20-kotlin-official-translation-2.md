---
layout: post
title:  "公式サイトの訳を少し (Interoperable)"
date:   2017-04-20 08:35:22 + Asia/Tokyo
tags: メモ Kotlin
timezone: Asia/Tokyo
---

### Interoperable / 互換性があること

Leverage existing frameworks and libraries of the JVM with 100% Java Interoperability.

JVMの既存のフレームワークとライブラリを活用できるように、100% Javaと互換性があります。

---
Create and consume Java code at will
Javaであればこんなふうに書いて利用します

{% highlight kotlin %}
import io.netty.channel.ChannelInboundMessageHandlerAdapter
import io.netty.channel.ChannelHandlerContext

public class NettyHandler: ChannelInboundMessageHandlerAdapter<Any>() {
    public override fun messageReceived(p0: ChannelHandlerContext?, p1: Any?) {
        throw UnsupportedOperationException()
    }
}
{% endhighlight %}

Or use any existing library on the JVM, as there’s 100% compatibility, including SAM support.

あるいは、JVM上の既存のライブラリを使う場合は、SAMを含め100%互換性があります。

Target either the JVM or JavaScript. Write code in Kotlin and decide where you want to deploy to

対象がJVMであってもJavaScriptであってもどちらでも大丈夫です。
デプロイしたい対象に応じて、Kotlinでコードを書いてみてください。

{% highlight kotlin %}
import js.dom.html.*

fun onLoad() {
    window.document.body.innerHTML += "<br/>Hello, Kotlin!"
}
{% endhighlight %}