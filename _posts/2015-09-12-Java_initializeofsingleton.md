---
layout: post
category : Java
title: Singleton Lazy/Eager initialization
tagline: "Java"
tags : [Java, デザインパターン]
---
{% include JB/setup %}
## Lazy initialization (レイジな初期化)
<hr class='section-line'>

レイジな初期化って言葉の意味を把握していなかったんだけど *必要な時に初期する* って意味だとさっき把握しました。  
なので Singleton の実装だと、

``` Java
public Class Singleton {
  private Singleton instance;

  private Singleton() {};

  public static synchronized Singleton getInstance() {
    if (instance == null) {
      instance = new Singleton();
    }
    return instance;
  }
}

```  

これが Lazy initialize になります。  
`getInstance()` 内で生成しているので必要な時に生成しているということになります。
<br>
<br>
## Eager initialization (性急な初期化)  

対照的に性急な初期化はもう想像がつくかと思いますが  

``` Java
public Class Singleton {
  private static Singleton instance = new Singleton();

  private Singleton() {};

  public staic Singleton getInstance() {
    return instance;
  }
}

```  

static 変数の宣言時に生成してしまうパターンです。
<br>
<br>
## で、どっちを使うのか  
<hr class='section-line'>
ってことですが、実践 UML によると  
必要ないときにコンストラクタの高コストな処理を咲けることができる  
*レイジな初期化は複雑で条件の付いた生成ロジックを含んでいることが多い*

からレイジが好まれると書いてあるけどいまいちピンと来ないです。

<br>
<br>
<div id="disqus_thread"></div>
<script type="text/javascript">
    var disqus_shortname = 'mae0003';

    (function() {
        var dsq = document.createElement('script'); dsq.type = 'text/javascript'; dsq.async = true;
        dsq.src = '//' + disqus_shortname + '.disqus.com/embed.js';
        (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(dsq);
    })();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript" rel="nofollow">comments powered by Disqus.</a></noscript>

This website is created with Jekyll. [Other Jekyll websites](https://github.com/mojombo/jekyll/wiki/Sites).
