---
layout: page
title: 開発のメモ!
tagline: Supporting tagline
---
{% include JB/setup %}

普段の開発と勉強したことで気になったことを備忘録代わりに残します。  
Java(Fx), JavaScript とか。  

<br>

## 最近の投稿
<hr class='section-line'>

<ul>
{% for post in site.posts %}
    <li>
        <a href="{{ post.url }}">
            {{ post.title }}
        </a>　({{ site.time | date_to_string }})
    </li>
{% endfor %}
</ul>


### My favorite movies  

* ギルバートグレイプ
* ボビー
* ニューシネマパラダイス  
* シリアナ  
* 恋愛小説家  
* インターステラ―  
* 裏切りのサーカス  

### My favorite books  

* グーニーズ  
* 暗号解読、フェルマーの最終定理  
* 予想通りに不合理  
* 高村薫 マークスの山、レディジョーカー、照柿、冷血、（太陽を曳く馬は読んでない）  
* 日本の一番長い日
* 山岳小説、山野井さんのやつとか  

<i class="fa fa-child fa-fw"></i>

Complete usage and documentation available at: [Jekyll Bootstrap](http://jekyllbootstrap.com)

## Update Author Attributes

{% highlight Java %}
List<String> messages = new List<>();
for(String message : messages) {
    System.out.println(message);
}
{% endhighlight %}
