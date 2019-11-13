---
layout: post
title: JavaScript をターミナル上で実行する
date: 2019-11-13 09:00:00 +0900
categories: javascript
author: kamataryo
---

# JavaScript をターミナル上で実行する

Gitpod を使って作成した JavaScript のプログラムをターミナル上で実行する方法について解説します。JavaScript の実行は Node.js というプログラムを用います。

## ターミナルを起動する

ターミナルは、Gitpod の画面下に表示されているテキストの入力が可能なエリアです。`$` という入力可能な位置を示すマーク（プロンプトと呼ばれます）が表示されています。ここにコマンド呼ばれる命令を入力し、コンピューターを操作します。
ターミナルは Gitpod を起動した時にデフォルトで表示されているはずですが、見あたらなかった場合メニューバーにある `terminal` から `New Terminal` というメニューを選択することで表示できます。

![open terminal]({{ site.url }}/{{ site.baseurl }}/images/20191112/00-terminal.png)

## Node.js の確認

ターミナルから Node.js のプログラムが存在することを確認します。以下のコマンドを Gitpod のターミナルで実行してください。

```shell
$ node -v
v10.15.3
```

Node.js が存在していることが確認できました。

## Node.js のプログラムを REPL を使って実行する

以下のコマンドを実行すると、 REPL と呼ばれるプログラム逐次実行モードが起動します。

```shell
$ node
>
```

REPL では、ターミナルのプロンプトが `$` から `>` という記号に変わります。JavaScirpt のプログラムを一行づつ入力して実行し、評価された値を確認することができます。

```shell
> 1+1
2
> const hello = "Hello"
undefined
> hello + ", World!"
'Hello, World!'
```

![REPL]({{ site.url }}/{{ site.baseurl }}/images/20191112/02-repl.png)

REPL は、 `CTRL + C` を 2 回押すと終了できます。

## ファイルとして作成した JavaScript のプログラムを実行する

以下のコマンドでファイルとして作成した JavaScript のプログラムを実行することができます。 `path/to/index.js` には、作成した JavaScript ファイルの _パス_ を指定してください。

```shell
$ node path/to/index.js
```

![execute file]({{ site.url }}/{{ site.baseurl }}/images/20191112/03-file.png)

### ファイルのパスとは？

ファイルのパスとは、どのフォルダにどのような名前でファイルが格納されているかを文字列で表したものです。例えば、 `folder-a` の中に入っている `folder-b` の中に入っている `index.js` というファイルのパスは、 `folder-a/folder-b/index.js` のように表せられます。

また、この JavaScript プログラムを Node.js で実行するには以下のコマンドを使います。

```shell
$ node folder-a/folder-b/index.js
```
