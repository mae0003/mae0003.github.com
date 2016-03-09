---
layout: post
title: シリアライズ
category: Java
tagline: "Java, Serialize"
---
{% include JB/setup %}

### シリアライズ/デシリアライズ  
<hr class='section-line'>

|名称|変換内容|  
|------------|-----|
| オブジェクト -> 符号化 | シリアライズ |  
| 符号化 -> オブジェクト | デシリアライズ |


<br>
### クラスをシリアライズ可能にするには  
<hr class='section-line'>
Serializable インターフェースを実装する。  
http://docs.oracle.com/javase/jp/8/docs/api/java/io/Serializable.html (Java8)  


<br>
### 特殊なメソッド 3つ  
<hr class='section-line'>

いずれもそれぞれのケースで独自の実装を行ないたい場合に実装する。  

1. void writeObject(ObjectOutputStream out)
1. void readObject(ObjectInputStream in)
1. void readObjectNoData()

<br>
### writeObject() メソッド  
<hr class='section-line'>
* ```ObjectOutputStream.defaultWriteObject()``` はデフォルトのシリアライズ処理を行なう。
* カスタムシリアライズを実装する場合に使用する。  

``` Java
private void writeObject(ObjectOutputStream out) throws IOException {
    out.defaultWriteObject(); // デフォルトのシリアライズ処理

    ・・・ // 独自の実装を行なう
}
```
<br>
### readObject() メソッド  
<hr class='section-line'>
* カスタムデシリアライズを実装する場合に使用する。  
* ```ObjectInputStream.defaultReadObject()``` はデフォルトのデシリアライズ処理を行なう。

``` Java
private void readObject(ObjectInputStream in) throws IOException {
    in.defaultReadObject(); // デフォルトのデシリアライズ処理

    ・・・ // 独自の実装を行なう
}
```
