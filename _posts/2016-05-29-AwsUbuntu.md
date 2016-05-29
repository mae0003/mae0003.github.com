---
layout: post
title: AWSにUbuntu, Tomcat, GitBucket
category: AWS
tagline: "AWS, Ubuntu, GitBucket"
---
{% include JB/setup %}

# SpringBatch のメモっていうかリンク

<hr class='section-line'>


## Awsに無料のUbuntuのインスタンスインスタンス作成

<hr class='section-line'>

でインスタンスの作成方法はなんか見て。

#### ポート8080を開放しておく。
インスタンスを表示して、セキュリティグループを編集してポート8080を開きます。  
 ![画像](/assets/image/posts/20160529/port.png)

#### WindowsにSSHクライアントインストール
PuttyとかTeraTermとか見た目気に入らないし、タブも使えないのでmobaXtermってのを使いました。けどなんかおせぇです。  
[mobaXtermの紹介ページ](http://did2memo.net/2015/09/19/mobaxterm-install/)

## Java8 のインストール

<hr class='section-line'>

何となく、JavaFXも使えるからoracleのJDKをインストール。

#### Java SDK インストール

```
$ sudo add-apt-repository ppa:webupd8team/java
$ sudo apt-get update
$ sudo apt-get install oracle-java8-installer
```

#### SDK の切り替えは
```
update-alternatives --config java
```

## Tomcat のインストール

<hr class='section-line'>

```
sudo apt-get install tomcat7 tomcat7-admin tomcat7-common tomcat7-docs tomcat7-examples tomcat7-user
```

#### GitBucketのインストール
```
sudo tomcat7-instance-create /usr/local/webapps/gitbucket/
```

## GitBucketの取得とデプロイ

<hr class='section-line'>

やることはダウンロードして、配置するだけです。

#### GitBucketのダウンロード

```
cd /usr/local/webapps/gitbucket/
sudo wget https://github.com/gitbucket/gitbucket/releases/download/4.0/gitbucket.war
```

URLは [https://github.com/gitbucket/gitbucket/releases] (https://github.com/gitbucket/gitbucket/releases)で確認すること。

#### インスタンスの起動
```
cd /usr/local/webapps/gitbucket/bin
sudo ./startup.sh
```

#### 起動の確認

ブラウザで
`http://***.***.***.***:8080/gitbucket` にアクセス。  

以上だ！
