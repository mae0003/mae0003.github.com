---
layout: post
title: オブジェクト
category: JavaScript
tagline: "JavaScript, Object"
---
{% include JB/setup %}

### オブジェクトリテラル式によるオブジェクトの生成
<hr class='section-line'>

プロパティ名は識別子、文字列、数値で設定が可能  
実質的に Singleton となる  

``` JavaScript
{ name:"mae" age:24 }
{ "name":"mae" age:24 }
{ 1:1 24:24 }
{ name:"mae" age:24 etc:{ address:"sapporo" tel:"011-011-1111" } }
```

<br>

### function オブジェクト

<hr class='section-line'>

``` function ``` で定義した関数は typeof の出力結果は "function" となる。

``` JavaScript
js> var mae = function Date() {}
js> typeof mae
"function"
```


<br>

### オブジェクトリテラルを利用した引数と戻り値

<hr class='section-line'>

#### オブジェクトリテラルを利用した引数 (+デフォルト引数)  

``` JavaScript
function incrementAge(mae) {
    mae = mae || { name:"mae" age:0 }
    return mae.age++;
}
```

####  オブジェクトリテラルを利用した戻り値

``` JavaScript
function getTom() {
    return { name:"tom" age:30 }
}
```

<br>

### プロパティ, メソッドのアクセス

<hr class='section-line'>

ドット "." もしくは ブラケット "[]" 演算子

``` JavaScript
// this の値によってメソッドの呼び出しを切り替える
Math[this < 0 ? 'celling' : 'floor'](this)
```

<br>

### プロパティ名・プロパティ値の列挙

<hr class='section-line'>

プロパティ名: `for in`  
プロパティ値: `for each in`  

<br>

### in 演算子

<hr class='section-line'>

オブジェクトにプロパティが存在するかどうかを調べる。

``` JavaScript
js> var map = { '001':'sapporo' };
js> '001' in map
true
js> 'sapporo' in map
false
```

※ プロトタイプ継承を行っているクラスのプロパティも対象になるので注意
