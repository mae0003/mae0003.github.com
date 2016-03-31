---
layout: post
title: CentOS, Apache, Tomcat 環境構築
category: CentOS
tagline: "Linux"
---
{% include JB/setup %}

### CentOS 7, Apache 2.4, Tomcat 7 の環境を作る

<hr class='section-line'>

Java ベースの Web Application の環境構築を思い立ったのでメモ。  
それぞれのバージョンと役割は以下の通り。

| CentOS | Linuxサーバ |
| Apache | httpサーバ |
| Tomcat | Webコンテナ（サーブレットコンテナ、サーブレットエンジン）|

<br>
Tomcat単体でもWebサーバとしては動作するけど、簡易的なサーバなのでApacheを入れて連携させます。
作業は以下の手順で進めることに。  


1. [CentOS のインストール・設定]({% post_url 2016-03-11-CentOS-Install %})
1. [Tomcat のインストール・設定]({% post_url 2016-03-22-Tomcat-Install %})
1. [Apache のインストール・設定]()

はて？できるかな
