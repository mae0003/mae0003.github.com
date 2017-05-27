## svnにコマンドらいんでログインしてパスワードキャッシュを有効にする

git svn コマンドでパスワード認証を行うとAD認証のせいかなぜか失敗してしまいます。なのでコマンドラインでログインして認証のキャッシュを残します。  

```
svn co svn://url project
```

## ローカルにsvnサーバを立ち上げてそこにログインするようにします。

[https://www.ipentec.com/document/document.aspx?page=subversion-password](https://www.ipentec.com/document/document.aspx?page=subversion-password)

[]()

## svnサーバにパスワード認証も有効にするように変更する。

### ユーザ追加

```
htpasswd -c /etc/httpd/.htpasswd {USERNAME1}
```

### subversion の設定

[http://d.hatena.ne.jp/bonvivant/20090514/1242231536](http://d.hatena.ne.jp/bonvivant/20090514/1242231536)

```
vi /etc/httpd/conf.d/subversion.conf
```

``` XML
<Location /repos>
　DAV svn
　SVNParentPath /var/www/svn

#　<LimitExcept GET PROPFIND OPTIONS REPORT>
#　　　SSLRequireSSL

　　　AuthType Basic
　　　AuthName "Authorization"
　　　AuthUserFile /etc/httpd/.htpasswd
　　　Require valid-user
#　</LimitExcept>
</Location>
```

