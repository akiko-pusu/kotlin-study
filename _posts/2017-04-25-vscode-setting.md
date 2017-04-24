---
layout: post
title:  "VisualStudio CodeでのKotlin"
date:   2017-04-25 07:13:01 + Asia/Tokyo
tags: メモ Kotlin
timezone: Asia/Tokyo
---

* TOC
{:toc}

### VisualStudioでコンパイルする

昨日の続き。コード学習は全然進んでいませんが、少しでも毎日書くのが大事と思って、Visual Studio Codeのネタを。

IntelliJを使うともっと早くて楽でしょうし、本来はMavenやGradleでビルドするようにした方がいいのかもしれませんが...。そのあたりはこれからの学習の課題とします。

ひとまず、Command + P -> Run Task でkotlincでコンパイルする設定を組んでみました。
tasks.jsonはこんな感じです。

```
{
    "version": "0.1.0",
    "tasks": [
        {
            "taskName": "kotlinc",
            "command": "kotlinc",
            "showOutput": "always",
            // *.ktのようにワイルドカード指定だと上手くいかないので、ディレクトリ指定で
            // kotlin_HOMEは ~/bin/kotlin に設定
            "args": ["-d","${workspaceRoot}\\build\\classes","-kotlin-home",
                "${env.HOME}/bin/kotlinc", "-verbose", "${workspaceRoot}/src/tutorial/"],
            "isShellCommand": true
        },
        // ビルドされたバイナリを実行してみる
        // 実行時に対象のクラスを指定するにはどうするのかわからないので、クラスごとにハードコード
        // ここはなんとかしたい....
        {
            "taskName": "Run HelloKt",
            "command": "kotlin",
            "args": ["-classpath","build/classes/", "HelloKt"],
            "isShellCommand": true
        }
    ]
}
```

VisualStudio Codeでは、Kotlinのプラグインがありますがシンタックスハイライトが中心で、ビルドの補助機能は無いようです。自分でプラグインを書くか、先に触れたMavenやGradleのビルドの手順を用意するか、誰かが作ってくれるのを待つ...かな？

------

### 本日のJekyllメモ

#### 日付のフォーマットを変更するには？

POSTの日付が "Apr 23, 2017" の書式になっていたので、これは変更したい...。
ということで、minima (テーマ)の公式を見ると、記述があったので変更してみました。

- [Change default date format](https://github.com/jekyll/minima#change-default-date-format)
- _config.yml を修正

```
minima:
  date_format: "%Y-%m-%d"
```
ただし、jekylle sで表示している場合は、 _config.ymlを修正したらプロセス再起動しないと設定変更が反映されません。


