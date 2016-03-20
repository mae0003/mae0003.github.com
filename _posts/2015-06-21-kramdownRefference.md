---
layout: post
title: Markdown (kramdown) のリファレンス
category : markdown
tagline: "markdown, kramdown"
---
{% include JB/setup %}

### Markdown (kramdown) の記法
<hr class='section-line'>

Jekyll でページを作成する際にマークダウンの書き方がいちいちわからないのでまとめてみました。  
僕の環境では kramdown を使用しているのですべては [kramdown - Quick Reference](http://kramdown.gettalong.org/quickref.html) でこと足りるのですが...

このページは Bootstrap(少しカスタマイズ) を使用しているので、表示はそれに従った表示になっています。
<br>

#### ブロックレベル要素
* [段落 - {::nomarkdown}&ltP&gt{:/}](#Paragraphs)
* [ヘッダー - {::nomarkdown}&ltHn&gt{:/}](#Headers)
* [引用 - {::nomarkdown}&ltBLOCKQUOTE&gt{:/}](#Blockquotes)
* [コードブロック - {::nomarkdown}&ltPRE&gt{:/}](#CodeBlocks)
* [水平線 - {::nomarkdown}&ltHR&gt{:/}](#HorizontalRules)
* [リスト - {::nomarkdown}&ltOL&gt{:/}](#Lists)
* [定義型リスト - {::nomarkdown}&ltDL&gt{:/}](#DefinitionLists)
* [テーブル - {::nomarkdown}&ltTABLE&gt{:/}](#Tables)
* [HTML要素 - {::nomarkdown}&ltDIV&gt{:/}, {::nomarkdown}&ltP&gt{:/} ...](#HtmlElements)
* [ブロック要素の属性](#BlockAttributes)
* [エクステンション](#Extensions)

#### スパンレベル要素
* [強調 - {::nomarkdown}&ltEM&gt{:/}, {::nomarkdown}&ltSTRONG&gt{:/}](#Emphasis)
* [リンク - {::nomarkdown}&ltA&gt{:/}](#Links)
* [画像 - {::nomarkdown}&ltIMG&gt{:/}](#Images)
* [インラインコード - {::nomarkdown}&ltCODE&gt{:/}](#InlineCode)
* [脚注 - {::nomarkdown}&ltA&gt{:/}](#Footnotes)
* [インライン要素の属性](#InlineAttributes)

<br>

## ブロックレベル要素

<hr class='section-line'>

<br><!---------------------------------------------------------------->
{: id="Paragraphs"}
<h3>段落 <small>Paragraphs</small></h3>
<hr class='section-line'>

#### syntax
{: style="color: #1b809e; margin-left: 15px"}

```
１行目△△ // △半角スペース
２行目 (同一段落になります。)

３行目 (空行をはさんでいるので、別段落になります。)
```
{: style="margin-left: 30px"}

<br>

#### view
{: style="color: #1b809e; margin-left: 15px"}

１行目  
２行目 (同一段落になります。)
{: style="margin-left: 30px"}

３行目 (空行をはさんでいるので、別段落になります。)
{: style="margin-left: 30px"}

<br>

#### html
{: style="color: #1b809e; margin-left: 15px"}

``` html
<p>
１行目<br />
２行目 (同一段落になります。)
</p>
<p>
３行目 (空行をはさんでいるので、別段落になります。)
</p>
```
{: style="margin-left: 30px"}

<br><!----------------------------------------------------->
<h3>ヘッダー <small>Headers</small></h3>
{: id="Headers"}
<hr class='section-line'>

#### syntax
{: style="color: #1b809e; margin-left: 15px"}

```
# H1 header
## H2 header
### H3 header
#### H4 header
##### H5 header
###### H6 header
```
{: style="margin-left: 30px"}

<br>

#### view
{: style="color: #1b809e; margin-left: 15px"}

# H1 header
{: style="margin-left: 30px"}

## H2 header
{: style="margin-left: 30px"}

### H3 header
{: style="margin-left: 30px"}

#### H4 header
{: style="margin-left: 30px"}

##### H5 header
{: style="margin-left: 30px"}

###### H6 header
{: style="margin-left: 30px"}



<br><!----------------------------------------------------->
<h3>引用 <small>Blockquotes</small></h3>
{: id="Blockquotes"}
<hr class='section-line'>

#### syntax
{: style="color: #1b809e; margin-left: 15px"}

```
> A sample blockquote.
>
> >Nested blockquotes are
> >also possible.
>
> ## 引用の中でもヘッダー(ブロック要素)は有効です
> This is the outer quote again.
```
{: style="margin-left: 30px"}

<br>

#### view
{: style="color: #1b809e; margin-left: 15px"}

> A sample blockquote.
>
> >Nested blockquotes are
> >also possible.
>
> ## 引用の中でもヘッダー(ブロック要素)は有効です
> This is the outer quote again.
{: style="margin-left: 30px"}

<br><!----------------------------------------------------->
<h3>コードブロック <small>Code blocks</small></h3>
{: id="CodeBlocks"}
<hr class='section-line'>

段落を変えて４つのスペースを挿入するとコードブロックに。
(空行がなくて、段落の先頭じゃないと認識されないので注意。)


#### syntax
{: style="color: #1b809e; margin-left: 15px"}

```
This is a sample code block.

    Continued here.
```
{: style="margin-left: 30px"}

<br>

#### view
{: style="color: #1b809e; margin-left: 15px"}

This is a sample code block.
{: style="margin-left: 30px"}

    Continued here.
{: style="margin-left: 30px"}

<br>

#### その他  

コードを {::nomarkdown}<code>~~~</code>{:/} や {::nomarkdown}<code>&#096;&#096;&#096;</code>{:/} で括ります。

<br>

#### syntax
{: style="color: #1b809e; margin-left: 15px"}


<pre>
&#096;&#096;&#096; Java
public class Hoge {
    private int count;
    ・・・
}
&#096;&#096;&#096;
</pre>
{: style="margin-left: 30px"}

<br>

#### view
{: style="color: #1b809e; margin-left: 15px"}

``` Java
public class Hoge {
    private int count;
    ・・・
}
```
{: style="margin-left: 30px"}


<br><!----------------------------------------------------->
<h3>水平線 <small>Horizontal Rules</small></h3>
{: id="HorizontalRules"}
<hr class='section-line'>

<br>

#### syntax
{: style="color: #1b809e; margin-left: 15px"}

```
* * *
---
  _  _  _  _
---------------
```
{: style="margin-left: 30px"}

<br>

#### view
{: style="color: #1b809e; margin-left: 15px"}

* * *
{: style="margin-left: 30px"}

---
{: style="margin-left: 30px"}

  _  _  _  _
  {: style="margin-left: 30px"}

---------------
{: style="margin-left: 30px"}

<br><!----------------------------------------------------->
<h3>リスト <small>Lists</small></h3>
{: id="Lists"}
<hr class='section-line'>

#### 数値のリスト

数字の後にピリオドと半角スペースを入力してなんか書きます。  
数字は勝手に採番するので全部 1 でも構いません。

ネストしたリストは半角スペースを入れるとなんか勝手にやってくれるけど (曖昧) ネストした項目は自動採番だけしてくれないので自分で振ってます。

<br>

#### syntax
{: style="color: #1b809e; margin-left: 15px"}

```
1. リストの項目１
   1．項目１－１
   1．項目１－２
1. リストの項目２
3. リストの項目３
   続く項目
```
{: style="margin-left: 30px"}

<br>

#### view
{: style="color: #1b809e; margin-left: 15px"}

1. リストの項目１
   1．項目１－１
   1．項目１－２
1. リストの項目２
3. リストの項目３
   続く項目
{: style="margin-left: 30px"}

<br>

#### 順序なしリスト

順序なしリストは、段落の先頭で `*`, `+`, `-` と半角スペースで項目を列挙します。

<br>

#### syntax
{: style="color: #1b809e; margin-left: 15px"}

```
* 項目1
+ 項目2
- 項目3
```
{: style="margin-left: 30px"}

<br>

#### view
{: style="color: #1b809e; margin-left: 15px"}

* 項目1
+ 項目2
- 項目3
{: style="margin-left: 30px"}


<br><!----------------------------------------------------->
<h3>定義型リスト <small>Definition Lists</small></h3>
{: id="DefinitionLists"}
<hr class='section-line'>

HTML の定義型 (DTタグ) を表現します。  
定義 (DT) と定義の説明 (DD) のセット。間に空行があっても一つの DL タグにくくられるみたい。

<br>

#### syntax
{: style="color: #1b809e; margin-left: 15px"}

```
定義
: 定義の説明１
: 定義の説明２

定義
その他の定義
: 定義の説明
```
{: style="margin-left: 30px"}

<br>

#### view
{: style="color: #1b809e; margin-left: 15px"}

定義
: 定義の説明１
: 定義の説明２

定義
その他の定義
: 定義の説明
{: style="margin-left: 30px"}

<br><!----------------------------------------------------->
<h3>テーブル <small>Tables</small></h3>
{: id="Tables"}
<hr class='section-line'>

`|` で括って書きます、前後にスペースなくても認識してくれるみたいです。
一つ以上の `-` でHEADERとBODYを分けてくれます。 また `=` でBODYとFOOTERを分けてくれます。  
`:-` は左寄せ、`:-:` は中央寄せ、`-:` は右寄せになります。  
`:` でアライメントを指定しない場合、ヘッダーは中央寄せ、データは左寄せになります。

僕の CSS (Bootstrap) はちょっと変更して無条件で罫線を引く設定になっているので罫線が引かれていますがデフォルトひかれないことが多いと思います。

<br>

#### syntax
{: style="color: #1b809e; margin-left: 15px"}

```
| A simple | table |
| with multiple | lines|

|名前|年|都道府県|
|:---|:-:|---|
|maeda|42|北海道|
|maeda|42|北海道|
|=|=|=|
|フッター1|フッター2|フッター3|
```
{: style="margin-left: 30px"}

<br>

#### view
{: style="color: #1b809e; margin-left: 15px"}

| A simple | table |
| with multiple | lines|
{: style="margin-left: 30px"}

<br>

|名前|年|都道府県|
|:---|:-:|---|
|maeda|42|北海道|
|maeda|42|北海道|
|=|=|=|
|フッター1|フッター2|フッター3|
{: style="margin-left: 30px"}

<br><!----------------------------------------------------->
<h3>ブロック要素の属性 <small>Block Extentions</small></h3>
{: id="BlockExtentions"}
<hr class='section-line'>

ブロック要素に属性を割り当てるにはブロック要素の後に `{:}` で属性を指定します。  
クラスを指定する場合は `{: .ClassName}` ID を指定する場合は `{: #ID}` で可能です。

<br>

#### syntax
{: style="color: #1b809e; margin-left: 15px"}

```
##### 普通のタイトル

##### 属性を付けたタイトル
{: style="color: red; margin-left: 15px"}

##### クラス名を指定する場合
{: .text-info}
```
{: style="margin-left: 30px"}

<br>

#### view
{: style="color: #1b809e; margin-left: 15px"}

{:refdef style="margin-left: 30px"}
##### 普通のタイトル

##### 属性を付けたタイトル
{: style="color: red; margin-left: 30px;"}
{: refdef}

##### クラス名を指定する場合
{: .text-info style="margin-left: 30px;"}

<br>

ALD, ILD についてはよくわからないのでまた今度。

<br><!----------------------------------------------------->
<h3>エクステンション <small>Extensions</small></h3>
{: id="Extensions"}
<hr class='section-line'>

コメントは `{::comment}{:/comment}` で括ります。  
文字列をマークダウンとして処理したくない場合は `{::nomarkdown}{:/}` で括ります。

<br>

#### syntax
{: style="color: #1b809e; margin-left: 15px"}

```
タイトル
{::comment}
ここはコメントなので表示
されることはありません。
{:/comment}
ここは表示されます。

文字列を**太字**にする場合は {::nomarkdown}**太字**{:/} のように書きます。
```
{: style="margin-left: 30px"}

<br>

#### view
{: style="color: #1b809e; margin-left: 15px"}

タイトル
{: style="margin-left: 30px"}

{::comment}
ここはコメントなので表示
されることはありません。
{:/comment}
ここは表示されます。
{: style="margin-left: 30px"}

文字列を**太字**にする場合は {::nomarkdown}**太字**{:/} のように書きます。
{: style="margin-left: 30px"}


<br>

## スパンレベル要素

<hr class='section-line'>

<br><!---------------------------------------------------------------->
{: id="Emphasis"}
<h3>強調 <small>emphasis</small></h3>
<hr class='section-line'>

`*` は Emphasis, `**` は Strong となっていますが、日本語の Emphasis は違いが判りません。

<br>

#### syntax
{: style="color: #1b809e; margin-left: 15px"}

```
これは *日本語 Emphasis* です。  
これは **太文字** です。  
これは __太文字__ です。  
```
{: style="margin-left: 30px"}

<br>

#### view
{: style="color: #1b809e; margin-left: 15px"}

これは *日本語 Emphasis* です。  
これは **強調文字** です。  
これは __強調文字__ です。  
{: style="margin-left: 30px"}

<br><!----------------------------------------------------->
{: id="Links"}
<h3>リンク <small>Links</small></h3>
<hr class='section-line'>

#### syntax
{: style="color: #1b809e; margin-left: 15px"}

```
これは [リンク](http://mae0003.github.io) です。  
これは [情報付きリンク](http://mae0003.github.io "リンク情報(マウスホバーで見れるよ)") です。  
{: style="margin-left: 30px"}
```
{: style="margin-left: 30px"}

#### view
{: style="color: #1b809e; margin-left: 15px"}

これは [リンク](http://mae0003.github.io) です。  
これは [情報付きリンク](http://mae0003.github.io "リンク情報(マウスホバーで見れるよ)") です。  
{: style="margin-left: 30px"}

<br><!----------------------------------------------------->
{: id="Images"}
<h3>画像 <small>Images</small></h3>
<hr class='section-line'>

#### syntax
{: style="color: #1b809e; margin-left: 15px"}

```
これは ![画像](/assets/image/image.png) です。  
[] の中は画像が存在しない場合に表示されます。 ![画像](xxxx.png)
```
{: style="margin-left: 30px"}

<br>

#### view
{: style="color: #1b809e; margin-left: 15px"}

これは ![画像](/assets/image/image.png) です。  
[] の文字は画像が存在しない場合に表示されます。 ![画像](xxxx.png)
{: style="margin-left: 30px"}


<br><!----------------------------------------------------->
{: id="InlineCode"}
<h3>インライン コード <small>Inline Code</small></h3>
<hr class='section-line'>

#### syntax
{: style="color: #1b809e; margin-left: 15px"}

```
インラインコードは `Code` のように。  
これも ```Hoge::method()``` できます。
```
{: style="margin-left: 30px"}

#### view
{: style="color: #1b809e; margin-left: 15px"}

インラインコードは `Code` のように。  
これも ```Hoge::method()``` できます。
{: style="margin-left: 30px"}

<br><!----------------------------------------------------->
{: id="Footnotes"}
<h3>脚注 <small>Footnotes</small></h3>
<hr class='section-line'>

脚注の説明内容はページの一番下のほうに表示されるので注意。

<br>

#### syntax
{: style="color: #1b809e; margin-left: 15px"}

```
タイトル  
: 項目1[^1].  
: 項目2[^2].  

[^1]: 脚注1.  
[^2]: 脚注2.  
```
{: style="margin-left: 30px"}

<br>

#### view
{: style="color: #1b809e; margin-left: 15px"}

タイトル  
: 項目1[^1].  
: 項目2[^2].  
{: style="margin-left: 30px"}

[^1]: 脚注1.  
[^2]: 脚注2.  


<br><!----------------------------------------------------->
{: id="InlineAttributes"}
<h3>インライン要素の属性 <small>Inline Attributes</small></h3>
<hr class='section-line'>

インライン要素の後に `{: }` で指定します。インライン要素と中括弧の間にスペースがあると認識されませんでした。

<br>

#### syntax
{: style="color: #1b809e; margin-left: 15px"}

```
[Google](www.google.com){: style="margin-left: 40px"}
**赤く太く**{: style="color: red;"}
```
{: style="margin-left: 30px"}

#### view
{: style="color: #1b809e; margin-left: 15px"}

[Google](www.google.com){: style="margin-left: 40px"}
**赤く太く**{: style="color: red;"}
{: style="margin-left: 30px"}

<br><!----------------------------------------------------->
{: id=""}
<h3 id="">空 <small>space</small></h3>
<hr class='section-line'>

#### syntax
{: style="color: #1b809e; margin-left: 15px"}

```

```
{: style="margin-left: 30px"}

<br>

#### view
{: style="color: #1b809e; margin-left: 15px"}

{: style="margin-left: 30px"}
