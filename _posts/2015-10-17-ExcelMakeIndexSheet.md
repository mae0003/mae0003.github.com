---
layout: post
title: エクセルでシート毎の目次を作る
category : Excel
tagline: "Excel, Macro"
---
{% include JB/setup %}

### Excel でシートの一覧のリンク可能な目次を作成する  

<hr class='section-line'>

Excel でシートが増えてくるとシートが探しにくくなってくるのでシートにリンクした目次のページを良く作ります。  
で、その手順とマクロをメモ。  



1. "目次" ってシートを作る
2. メニューやリボンで [開発] から [Visual Basic] を開く
3. 目次のシートに以下のコードを張り付けて実行する。


``` VB
Sub make_index()
    Dim i As Integer
    Dim sheetNo As Integer

    Columns("A:B").Select
    Selection.ClearContents

    sheetNo = 1
    'リンク先をC10に設定
    For i = 1 To Worksheets.Count
        If Worksheets(i).Name <> "目次" Then
            Worksheets("目次").Hyperlinks.Add anchor:=Cells(i, 2), _
                Address:="", _
                SubAddress:="'" & Worksheets(i).Name & "'" & "!C10", _
                TextToDisplay:=Worksheets(i).Name
            Cells(i, 1) = sheetNo
            sheetNo = sheetNo + 1
        End If
    Next
End Sub
```  
