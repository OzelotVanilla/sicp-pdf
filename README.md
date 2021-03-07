SICP
====

<img src="http://sicpebook.files.wordpress.com/2013/09/dreamsmile3.png"
 alt="Par dreaming and smiling" align="right" />

This is a PDF version of "Structure and Interpretation of Computer Programs" by Harold Abelson, Gerald Jay Sussman, and Julie Sussman. It is a further development of the [Unofficial Texinfo Format](http://www.neilvandyke.org/sicp-texi/) (UTF), which was originally derived from the [HTML version](http://mitpress.mit.edu/sicp/) at The MIT Press.

これはPDF版の"Structure and Interpretation of Computer Programs"です。Harold Abelson, Gerald Jay Sussman, そして Julie Sussmanによる著書です。PDF版は[Unofficial Texinfo Format](http://www.neilvandyke.org/sicp-texi/) (UTF)からのさらなる開発であり、
元々はMIT Pressの[HTML version](http://mitpress.mit.edu/sicp/)からの派生です。

* これはAndres Raba氏による[PDF版SICP](https://github.com/sarabander/sicp-pdf) の日本語翻訳です。この日本語版は、minghai氏による日本語版のテキストを書き換える形で真鍋宏史が翻訳したものです。

Biggest change in this revision (2.andresraba5) is the conversion to LaTeX, which opens the door to design and customization possibilities that the massive CTAN archive enables. Also, the latest typesetting engine XeTeX can be used, along with the Unicode and OpenType goodness it brings.

このバージョン(2.andresraba5)での大きな変更はLaTeXへの変換です。これにより大規模なCTANアーカイブが可能にするデザインとカスタマイズの可能性への扉を開きました。また、最新の組版エンジンであるXeTeXが、それがもたらすUnicodeとOpenTypeの良さと共に使用可能です。

* 日本語版では源ノ角ゴシック・源ノ明朝を使用しました。

Source
------

The `src` directory contains both Texinfo and LaTeX sources. To recompile the book, go there and enter:

`src`ディレクトリがTexinfoとLaTeXの両方のソースを含みます。本をリコンパイルするためにはその場所まで移動して以下を入力して下さい。

```bash
$ make
```

* 日本語版では既にLaTeXファイルとTexinfoファイルとの間の同期が破綻しています。

Chances for successful compilation are increased if you have almost complete installation of recent TeX Live distribution (the pdf here is compiled with 2012 release). The needed OpenType fonts must be installed in the operating system. You also need Inkscape to recreate image PDFs from SVGs.

成功裏のコンパイルの可能性は最新のTeX Liveのディストリビューションをインストールすることにより増します。(ここのPDFファイルは2012のリリースにてコンパイルされています)。必要なOpenTypeフォントがOSにインストールされなければなりません。またSVGをPDFに変換するためにはInkscapeも必要です。

* 日本語を通すには最低でもTeX Live 2013が必要です。日本語対応のminghaiは当初は最新の(RCのUbuntu)ディストリのLinux上で
texi2dviとdvipdfmxを用いてPDF化していました。最終的にはWindowsに最新のW32TeXを入れ、xelatexにてコンパイルしています。
日本語環境では源ノ角ゴシック・源ノ明朝をインストールすることが必須です。また実際には足りないスタイルファイルが結構有りますので、
エラーが出る度にCTANにてスタイルファイルを落としてインストールすることを何度かしなければいけませんでした。

If compilation stops with "LaTeX Error: Too many unprocessed floats.", you could try to increase the width and height of text area in [preamble](https://github.com/sarabander/sicp-pdf/blob/master/src/preamble.tex#L70-L71). Newer TeX Live or updated fonts could result in different character metrics, so that some figures no longer fit. The problem is reported in issue [#5](https://github.com/sarabander/sicp-pdf/issues/5).

コンパイルが"LaTeX Error: Too many unprocessed floats"で停止した場合には、[preamble](https://github.com/sarabander/sicp-pdf/blob/master/src/preamble.tex#L70-L71)の中にあるテキストの幅と高さを増やしてみると良いかもしれません。
新しいTeX Liveや更新されたフォントの使用は異なる文字メトリックスの結果を引き起し、いくつかの図が合わなくなる恐れがあります。
問題がissue [#5](https://github.com/sarabander/sicp-pdf/issues/5)にて報告されています。

* 日本語版の図は第2章まで翻訳しています。残りの図を翻訳して下さる方を募集しています。翻訳される際には、図の中の日本語には特に問題がなければ源ノ角ゴシック・源ノ明朝を使用してください。

To clean up after the build:

ビルド後に全ての不要なファイルを削除するためには以下を入力して下さい。

```bash
$ make clean
```

This deletes the temporary files written during sicp.pdf creation, including sicp.pdf itself. Move it up to root directory if you want to keep it.

これはsicp.pdf作成の間に書かれた一時ファイルをsicp.pdf(日本語版ではjsicp.pdf)自体を含めて削除します。PDFを保持したい場合には(レポジトリの)ルート
ディレクトリに上げて下さい。

To remove all the generated PDFs and auxiliary files in the whole `src` tree:

`src`ツリー内のPDFと全ての補助的なファイルを削除するには以下を実行します。

```bash
$ make clean-all
```

謝辞
----------------

* Lytha Ayth
* Neil Van Dyke
* Gavrie Philipson
* J. E. Johnson
* Mingshen Sun
* holomorph
* Andres Raba
* minghai

License
-------

WARNING: This is not a translation. This is a license only for MY Japanese version.

The files `sicp.texi, sicp.tex, sicp.pdf,` and the diagrams in directory `src/fig` are licensed under Creative Commons Attribution-ShareAlike 4.0 Unported License ([CC BY-SA](http://creativecommons.org/licenses/by-sa/4.0/)).
          
The script files `ex-fig-ref.pl, survey.rb,` and `texi-to-latex.pl` are licensed under GNU General Public License version 3 (for details, see src/LICENSE). (as-is the same with the original PDF version).

日本語版ライセンス：

日本語版のsicp.texi、sicp.texはCreative CommonsのCC BY-SA｜します。改変、再配布は同じCC BY-SA 4.0にて行う限り自由に行っていただいてかまいません。

また`ex-fig-ref.pl, survey.rb,texi-to-latex.pl`は元の作者であるAndres Raba氏の指定によりGPL v3です。
