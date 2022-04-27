---
layout: post
title: Gitpod を使う
date: 2019-04-17 12:00:00 +0900
categories: gitpod
author: kamataryo
---

# Gitpod を使う

[GitHub](https://github.com) と [Gitpod](https://gitpod.io) を連携して利用する方法について解説します。

## GitHub でリポジトリを作成する

GitHub のセットアップが終わったら新しいリポジトリを作成してください。ここでは、ユーザーの名前は `kamataryo` リポジトリの名前は `sandbox-gitpod` という名前だと仮定して説明します。これらは皆さんの環境に読み替えてください。

GitHub にログインした後で、リポジトリのページ、または右上のプラスのアイコンをクリックするとリポジトリを作成することができます。

![リポジトリ作成ボタン]({{ site.url }}/{{ site.baseurl }}/images/20190417_010_create_repo1.png)![リポジトリ作成ボタン]({{ site.url }}/{{ site.baseurl }}/images/20190417_010_create_repo2.png)

リポジトリの名前を決定します。
![リポジトリ名を入力]({{ site.url }}/{{ site.baseurl }}/images/20190417_020_decide_repo_name.png)

空のリポジトリページができました。
![空のリポジトリ]({{ site.url }}/{{ site.baseurl }}/images/20190417_030_repository_created.png)

ブラウザの URL バーを見て値を確認してください。私の場合は以下のようになります。

```shell
https://github.com/kamataryo/sandbox-gitpod
```

## Gitpod でコンテナを起動する

Gitpod のセットアップが終わっていて、ダッシュボードにログインできていることを確認してください。

![Gitpod dashboard]({{ site.url }}/{{ site.baseurl }}/images/20190417_100_gitpod_dashboard.png)

Gitpod でコンテナを起動する URL を作成します。以下のような URL を作成してください。

```shell
https://gitpod.io#<GitHub の URL>
```

私の場合は以下のような値になります。

```shell
https://gitpod.io#https://github.com/kamataryo/sandbox-gitpod
```

この URL をブラウザに入力すると、 Gitpod のコンテナが起動します。しばらく待つと、開発環境が出来上がります。

![gitpod editor]({{ site.url }}/{{ site.baseurl }}/images/20190417_110_gitpod_editor.png)

ファイルを作成したり、編集したりできることを確認して下さい。

## HTML を編集する

例えば、以下のような値を `index.html` というファイル名で作成して下さい。

```HTML
<html>
    <body>
      <h1>タイトルです</h1>
      <p>これはパラグラフです</p>
    </body>
</html>
```

## Gitpod のプレビューを行う

作成した HTML がどのようにウェブページとして表示されるのかを確認します。
ページ下部に表示されているコンソール（`gitpod /workspace/sandbox-gitpod $` などのような表示とともに、キーボードでの入力が可能なエリアがあります）に、以下のコマンドを入力してください。

```shell
python3 -m http.server 3000
```

`A service is avilable on port 3000` のようなメッセージが上部に表示されます。

![プレビュー]({{ site.url }}/{{ site.baseurl }}/images/20190417_120_gitpod_preview.png)

`Open Browser` というボタンをクリックすると、書いた HTML がブラウザで表示されます。

この状態だと、ターミナルにコマンドの入力ができない状態になっているはずです。 `Control + C` でキャンセルすると、再度入力可能な状態に戻ります。

## 作成した内容を GitHub にプッシュする

以下のコマンドを入力して作成した内容を GitHub にプッシュ（アップロード）します。このことに関する詳細は別の投稿で解説します。

```shell
git add .
git commit -m"HTMLを追加"
git push origin main
```

初回のプッシュでは、 `The command requires permissions` のようなメッセージが表示されます。ダイアログにしたがって、適切な権限を Gitpod に与えて下さい。

![Gitpod grant]({{ site.url }}/{{ site.baseurl }}/images/20190417_130_gitpod_grant.png)

プッシュが成功すると、 GitHub に変更が反映されます。上記で確認した GitHub の URL にアクセスして、 `index.html` が表示されていることを確認して下さい。
