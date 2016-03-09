---
layout: post
category : Java
title: Java8 のインターフェースの変更点
tagline: "Java8"
tags : [Java8, interface, default, static]
---
{% include JB/setup %}

### interface に default, static メソッドが定義できるようになった

<hr class='section-line'>

ちょっと前から Java8 でインターフェースに static メソッドが書けるのは気づいていて、strategy の Factory とか作るとき、クラスに切り出すのめんどくさくなったら Static Factory メソッドに書こうかとひそかにもくろんでいたんだけど。

``` Java
public interface HogeI {

  // Static factory method
  static HogeI createHoge(Type type) {
    if (type == ***) {
      return new Hoge***();
    } else if (type == xxx) {
      return new Hogexxx()
    }
    throw new XxxxException();
  }

  void update();
  void remove();
  ・・・
}
```

最近 ここの記事を見ていたら default っていうキーワードでインスタンスメソッドも定義できるようになっていて驚きました。

<script src="https://gist.github.com/mae0003/79cdaf655f3315959d74.js"></script>

何が便利かというと。僕が説明するより ↓ の説明が大変わかりやすかった。  


浅はかな僕は **「じゃー abstract なんていらないじゃない!」** と思っていたけど。。。  

メソッド公開したくない時 interface じゃできないから abstract が必要だと同僚に指摘されました。  

オーバーライドも何か違いがあるのかもしれないけど確認してません。  

ぎゃふん。
