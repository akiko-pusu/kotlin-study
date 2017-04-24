---
layout: post
title:  "Kotlinのコマンドラインツール"
date:   2017-04-24 00:19:39 + Asia/Tokyo
tags: メモ Kotlin
timezone: Asia/Tokyo
---

* TOC
{:toc}

### Tutorialsをはじめてみる

まずは少しずつ [Reference](https://kotlinlang.org/docs/reference/) を読んでみていったのですが、実際に動かさないと分からないことも多い...。

そして、なんだかんだでRails5のメモも混じってきて、これではKotlinのほうが進まない！

ということで、とにかく毎日少しでもメモを書いて進めなくては、動かせる状態にしなくてはと、コマンドラインのコンパイラを入れることにします。

### コマンドラインコンパイラを入れる

手順はこちらに従って。

- [Working with the Command Line Compiler](https://kotlinlang.org/docs/tutorials/command-line.html)

コンパイラはGitHubのリリースページからダウンロード可能です。
MacOSなら、homebrewでもインストールできます。
また、Unixベースのマシンなら、インストール用のシェルを実行して、オンラインでインストールできます。

こんな感じ。

```
$ curl -s https://get.sdkman.io | bash
```

ただ、無闇にインターネット上のスクリプトを確認せずにそのまま実行するのは気をつけましょう...。
ざっとなにをやっているのか見てから、ちょっと処理が理解できなかったので、リリースページからzipファイルをダウンロードして使うことにしました...。

```
$ sudo mv ~/Downloads/kotlinc ~/bin/
$ export PATH=$PATH:~/bin/kotlinc/bin

$ kotlin -version
Kotlin version 1.1.1 (JRE 1.8.0_65-b17)
```
### 最初のアプリケーションを作る

早速チュートリアルに従って、ファイルを作ってみます。

{% highlight kotlin %}
fun main(args: Array<String>) {
    println("Hello, World!")
}
{% endhighlight %}

ファイル名は hello.kt です。
Visual Studio CodeにもKotlinのプラグインがあるので、そちらを追加してみました。
ただし、ビルドはまだ設定出来ない模様...

![image]({{ site.baseurl }}/assets/images/20170424-vscode-and-kotlin.png){: .img-shadow}

### ビルドしてみる

ビルドの仕方にはいくつかオプションがあるのですが、単純に kotlinc コマンドだと、.class (クラスファイル)が出来ます。
こちらを実行する場合は、*.classの場所をclasspathに追加して、以下のようにします。

```
$ kotlinc src/tutorial/hello.kt -d out/
      Regenerating: 2 file(s) changed at 2017-04-24 00:47:24 ...done in 0.651356 seconds.
mb:kotlin-memo akiko$ ls out/
HelloKt.class	META-INF

$ kotlin -classpath out HelloKt
Hello, World!

```
なんとか出来ました！
これで次にすすめそうです....


