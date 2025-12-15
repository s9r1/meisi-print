# meisi-print

55mm×91mmのカードをA4用紙のページ中央に5×2で配置したPDFを作成する

## 使い方

### 1. `meisi-print.tex`でカードのファイルを読み込む

```latex
\includegraphics[width=91mm,height=55mm]{my-meisi.pdf}% <- ファイルを指定
```

### 2. 用紙にカード間のマージンがある場合はそれを指定

たとえば[こちら](https://www.a-one.co.jp/product/search/detail.php?id=51678)の用紙を使う場合は以下のようになる

```latex
\newlength{\hmargin}
\setlength{\hmargin}{4mm}% <- アンコメント
\newlength{\vmargin}
\setlength{\vmargin}{2mm}% <- アンコメント
```

### 3. データと印刷結果で印刷位置にズレが生じる場合は微調整

たとえば全体を下方向に0.9mmずらす場合は以下のようになる

```latex
\newlength{\offsetY}
\setlength{\offsetY}{0.9mm}% <- アンコメント
```

印刷の際にはサイズを100%で指定することを忘れないように

### 4. 必要に応じて塗り足す

```latex
\newbool{bleed}
\booltrue{bleed}% <- アンコメント
```

ただしカードの背景が透明のとき、塗り足しに侵食されるケースがある。その場合は、カード最背面の全体に白などの色付き長方形を配置すると良い。
