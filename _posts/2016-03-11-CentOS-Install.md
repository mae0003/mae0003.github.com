---
layout: post
title: CentOS のインストール・設定
category: CentOS
tagline: "CentOS7, 解像度, ディスプレイ"
---
{% include JB/setup %}

### インストーラのダウンロード

<hr class='section-line'>

まずは[https://www.centos.org/download/](https://www.centos.org/download/)のダウンロードサイトからインストーラをダウンロードします。

![a](/assets/image/posts/20160311/pict01.png)

上記の画像の通りインストーラは

* DVD ISO - 一般的なパッケージ
* EveryThing ISO - 上記 + 追加の機能 + オンメモリ用のLive ISOイメージ
* Minimal ISO - 必要最低限のパッケージ、Windowベースのデスクトップ環境がない
の３種類がありますが、 *DVD ISO* を選択します。

4GBもあります。（間違えてテザリング中にダウンロードしてえらいことになりました。）

インストーラの詳細は [CentOS 7インストーラーの新機能と注意点](https://thinkit.co.jp/story/2014/11/21/5368) が参考になると思います。

でダウンロードしたISOイメージをDVDに焼いてイントールの開始です。

<br>

### CentOS7 のインストール

<hr class='section-line'>

でインストールを説明しようと思ったのですが。。。。  
画面のキャプチャがめんどくさい上に説明サイトがあってわかりやすかったので書く気が失せました。{::nomarkdown}(*‘∀‘){:/}

で参考にしたサイトは [初めての自宅サーバ構築 - CentOS7 のインストール手順](http://kajuhome.com/centos7_inst.shtml)  

素晴らしい！

<br>

### 解像度の変更

<hr class='section-line'>

使っているモニターは解像度が 1920x1200 なのですが、{::nomarkdown} [設定] - [ディスプレイ] {:/} を見ると *unknown display* になっており、解像度が 1024x768 になっていました。

直し方がわからず....

Google で調べると  

Fedora10 あたりから xorg.conf は使わなくなっているようで、 `xrandr` を使うみたい。

[Fedoraで自動認識していない画面解像度に変更する方法](http://mo.kerosoft.com/0167) を参考にさせていただいて直しました。

と思ったら、それだと再起動のたびに修正しないとならないので、

[Ubuntu 11.04 Beta の解像度を追加する](http://pc-usr.seesaa.net/article/196645544.html) を再度参考に修正しました。

時間かかった。。。。

<br>

### 日本語入力の設定

<hr class='section-line'>

更に作業をしていると、日本語入力が行えないことが判明。設定したのでメモ。

1. [アプリケーション]ｰ[システムツール]-[設定]を選択して、[地域と言語]を選択する。
![a](/assets/image/posts/20160311/fep.png)

1. 入力ソースの横にある [+] ボタンをおして、″日本語（かな漢字）″ を追加します。
![a](/assets/image/posts/20160311/fep2.png)

1. すると [Windows] + [スペース] で入力を切り換えられるようになります。
