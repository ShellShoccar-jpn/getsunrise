# 郵便番号→緯度経度→日の出時刻 コマンド

[jq](http://stedolan.github.io/jq/)や[xmllint](http://xmlsoft.org/xmllint.html)といったコマンドの使い勝手がなっておらんので、[独自JSON&XML解析コマンド](https://github.com/ShellShoccar-jpn/Parsrs)と、その応用品であるこのコマンド“**getsunrise.sh**”を作った。どこがなっておらんのかは[Qiita](http://qiita.com/)上に記した次の[セクション](http://qiita.com/richmikan@github/items/e051b5d882c3dd2a39c6#jq%E3%82%84xmllint%E7%AD%89%E3%81%AFunix%E5%93%B2%E5%AD%A6%E3%81%AB%E6%9F%93%E3%81%BE%E3%82%8A%E3%81%8D%E3%81%A3%E3%81%A6%E3%81%84%E3%81%AA%E3%81%84)でこってり書いたので読んでくるがよい。

まあとにかく、ここではこのgetsunriseを使ってみよ。

## インストール方法

[curl](http://curl.haxx.se/)か[wget](http://www.gnu.org/software/wget/)が入っているUNIX環境ならほとんどの環境で動く。もちろん **jqとかxmllintとか不要。JSONとXMLの解析はsedやAWKで済ませておる。

よって、上記のどちらかをインストールした後、次のようにしてこのリポジトリーをgit cloneすれば完了だ。

```sh:インストール方法
$ git clone https://github.com/ShellShoccar-jpn/getsunrise.git
```

そうか、gitがインストールされておらんと上記のコマンドは使えんな。gitが無くともunzipコマンドがあるなら
> [https://github.com/ShellShoccar-jpn/getsunrise/archive/master.zip](https://github.com/ShellShoccar-jpn/getsunrise/archive/master.zip)

からファイルをダウンロード、展開、中のREADME.md以外のすべてのファイルに実行パーミッションセットで使えるようになるぞ。

## 使い方

コマンドの引数に郵便番号（`nnn-nnnn`）を付ければよいだけだ。

```bash:実行例
$ ./getsunrise.sh 288-0012 2014/01/01
千葉県銚子市犬吠埼、20140101の日の出・日の入時刻を調べます。
(15秒くらい待ってね...)

千葉県銚子市犬吠埼(緯度=35.706987,経度=140.861803)における、
2014年1月1日の 日の出時刻は6:46、日の入時刻は16:34、みたいですよ。
$ ./getsunrise.sh 100-2100 2014/01/01 # ←日本一早い初日の出の時刻は？
#(実際に動かしてみてください)
$ 
```

結果が出るまで15秒くらい待たされるが、これはAPIの仕様だ。我々のシェルスクリプトのせいではないぞ！

## 技術解説

このコマンドがやっている事は下記のとおりだ。要するにWebAPIを渡り歩いておるのだ。

1. コマンド引数から郵便番号を受け取る。
2. [郵便番号検索WebAPI](http://geoapi.heartrails.com/)に掛けて、地名と緯度・経度を得る。
3. さらに、[日の出・日の入時刻WebAPI](http://labs.bitmeister.jp/ohakon/index.cgi)に掛けて、日の出・日の入り時刻を得る。

ソースコードに興味がある者は、このリポジトリーの中身をじっくり見まわすがよい。[getsunrise.sh](https://github.com/ShellShoccar-jpn/getsunrise/blob/master/getsunrise.sh)本体など、コメントや空行を除けばたかだか85行のシェルスクリプトだ。
