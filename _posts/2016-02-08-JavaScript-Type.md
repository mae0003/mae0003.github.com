---
layout: post
title: Type of JavaScript
category: JavaScript
tagline: "JavaScript, Type, 型"
---
{% include JB/setup %}


### JavaScript の型

<hr class='section-line'>

* JavaScript は動的言語 = 変数に型がない

|種類|型|typeof の返却値|説明|
|----|---|---|---|
|基本型|文字列型|string||
||数値型|number|64bit の double 値|
||Boolean 型|boolean||
||null 型|object (!!!)|型を判定する場合は null と ===(同値判定)|
||undefined 型|undefined|定義済グローバル変数(ECMAScript 5~ 代入不可)|
|参照型|オブジェクト型|object||

<br>

### == と ===

<hr class='section-line'>

    == は暗黙の変換を行う  
    === は暗黙の変換を行わない  

<br>

### NaN

<hr class='section-line'>

> NaN == NaN は false  
> NaN を調べるには ```isNaN()``` メソッドを使用します。  

``` JavaScript
js> isNaN(NaN)
js> true
```

<br>

### 文字列 -> 数値変換

<hr class='section-line'>

Number, parseInt, parseFloat を使う。  

``` JavaScript
js> Number('100x');  // 数値以外の文字を判定する
NaN

js> parseInt('100x');  // 数値以外の文字を判定しない
100

js> parseInt('100x', 2);  // 第2パラメータは奇数 (2進数)
4
```

こう見ると Number のほうが安全のような気がする・・・  

<br>

### 数値 -> 文字列変換

<hr class='section-line'>

基本は ``` toString() ``` メソッドを使う。  

以下も有効

``` JavaScript
js> 'mae' + 100
mae100

js> 100 + 'mae';
100mae
```

<br>

### -> boolean への変換

<hr class='section-line'>

"!!" を使って変換します。(もしくは ```Boolean()``` メソッド)  

``` JavaScript
js> !!0;     // 0 以外は true
js> !!NaN;
js> !!null;
js> !!undefined;
js> !!'';     // '' 以外は true

// 上記の結果はすべて false
```

*****
