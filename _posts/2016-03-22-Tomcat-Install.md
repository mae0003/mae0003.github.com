---
layout: post
title: Tomcat のインストール・設定
category: CentOS
tagline: "CentOS, Tomcat, Install"
---
{% include JB/setup %}

### インストーラのダウンロード

<hr class='section-line'>

Tomcat は現時点での安定板 7.0.68 をインストールします。

まずは [http://tomcat.apache.org/](http://tomcat.apache.org/)のダウンロードサイトからインストーラをダウンロードします。  
Core の tar.gz を選択。  

![a](/assets/image/posts/20160322/tomcat01.png)

で今回も、他のサイトを参考に・・・・  
[CentOSにTomcat7をインストールする方法と起動スクリプトについて](http://www.task-notes.com/entry/20150702/1435806000)

でインストールしました。

クズ。

けど、出来ました。 `127.0.0.1:8080` で以下の表示を確認して終了！  

![a](/assets/image/posts/20160322/tomcat.png)
