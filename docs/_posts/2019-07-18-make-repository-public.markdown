---
layout: post
title: GitHub のリポジトリを公開設定にする
date: 2019-07-18 12:00:00 +0900
categories: github
author: kamataryo
---

# GitHub のリポジトリを公開設定にする

プライベート設定で作成した GitHub のリポジトリは、所有者や権限を持っているユーザー以外からは見ることができません。
これを公開設定（パブリック）にすることで不特定多数に対してリポジトリを閲覧可能にする方法について解説します。

**重要**
公開設定にすることができないリポジトリ（公開したくない個人情報や企業秘密など、センシティブな情報を含むもの）に対して、この操作を行わないでください。

## 手順

1) プライベートリポジトリの `Settings` を開く

  ![settings]({{ site.url }}/{{ site.baseurl }}/images/20190718_01.png)

2) 下部の `Danger Zone` にある `Make public` ボタンを押す

  ![danger zone]({{ site.url }}/{{ site.baseurl }}/images/20190718_02.png)

3) ダイアログが出現するのでよく読む。公開設定にすると不特定多数がリポジトリを見ることができる、という旨が書かれている

4) リポジトリ名を入力して、 `I understand, make this repository public.` というボタンを押す。この操作で間違って別のリポジトリの設定変更を行なっていないかをあなた自身が確認できる

  ![dialog]({{ site.url }}/{{ site.baseurl }}/images/20190718_03.png)

5) パスワードの入力を求められるので入力する

  以上です。なお、同様の手順でリポジトリをプライベートの設定にすることも可能です。
