---
layout: post
title: プロトタイプチェーン
category: JavaScript
tagline: "JavaScript, 継承, protptype chain"
---
{% include JB/setup %}

<style>
div.uml-box {
    margin-left: 30px;
    margin-top: 30px;
    margin-bottom: 30px;
}
div.class-box {
    border: 1px solid #8c8b8b;
    width: 150px;
    border-radius: 3px;
    text-align: center;
}

div.diagram-row {
    width: 150px;
    text-align: center;
}

</style>

### プロトタイプチェーンによる継承

<hr class='section-line'>

``` var concrete = new Base(); ```
でベースオブジェクトのプロトタイプ継承を実装できる。

<br>

#### 1. 1つのチェーン

<div class='uml-box'>
    <div class='class-box'> MaeBase </div>
    <div class='diagram-row'>↑</div>
    <div class='class-box'> MaeConcrete </div>
</div>

``` JavaScript
js> function MaeBase() { print('this is MaeBase'); this.name = 'MaeBase'; };
js> var maeConcrete = new MaeBase();
this is MaeBase

// prototype(MaeBase) の name プロパティが表示される
js> print( maeConcrete.name );      
MaeBase
```

<br>

#### 2．複数のチェーン

<div class='uml-box'>
    <div class='class-box'> MaeBase </div>
    <div class='diagram-row'>↑</div>
    <div class='class-box'> MaeBase1 </div>
    <div class='diagram-row'>↑</div>
    <div class='class-box'> MaeConcrete </div>
</div>

``` JavaScript
js> function MaeBase() { print('this is MaeBase'); this.name = 'MaeBase'; };
js> function MaeBase1() { };
js> MaeBase1.prototype = new MaeBase();
this is MaeBase
js> var maeConcrete = new MaeBase();
this is MaeBase
```


<br>

### 型の判定

<hr class='section-line'>

#### constructor プロパティによる判定

``` JavaScript
// 定義
js> function MaeBase() { print('this is MaeBase'); this.name = 'MaeBase'; };
js> var maeConcrete = new MaeBase();
this is MaeBase

// 判定
js> maeConcrete.constructor        
function MaeBase() { print('this is MaeBase'); this.name = 'MaeBase'; }
```

***
