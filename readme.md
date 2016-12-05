# 概要
研究室内で使っている、レポート用のLatexテンプレートです。
宇宙工学が専門の研究室なので、参考文献の書き方はjeconを使ってその流儀に合わせてあります。

テンプレートと名乗っていますが、ドキュメントクラスにbxjsarticleを使用しているなんちゃってテンプレートです。
その他よく使うであろうパッケージを`PrettyLatexReport.sty`にまとめています。
手抜きで作った分、改変はしやすかろうと思います。

# 使い方
PrettyLatexReportスタイルファイルを`\usepackage`してください。

日本語が文章中に含まれる場合にはuplatex, upbibtex ないしは platex, pbibtexを使用してください。
汎用性の観点から前者を推奨します。
使っているドキュメントクラスはxetexなどにも対応しています。
後者を使用する際には`\documentclass`のオプションをuplatexからplatexに変更してください。
bibtexのままコンパイルしようとすると、巨大な中間ファイルが生成される場合がありますので注意してください。


輪講（力学ゼミ）用出力は次のように`dynamics`オプションをつけることで有効となり、CONTENTS(担当ページ数)が`\maketitle`部に表示されます。

~~~
\usepackage[dynamics]{PrettyLatexReport} % for dynamics seminar
~~~

`\title`, `\author`, `\date`, `\contents`のパラメータ指定が必要です(`\contents`は力学ゼミの場合のみ)。

引用文献は`\thebibliography`環境を使って書いてもよいですが、いい感じの書式になるようjecon.bstを編集してあるので、bibファイルから読み込むと楽です。

jeconやスタイルファイルは、文書本体と同じフォルダに置いても機能します。
ですが、Latexの適当なフォルダにインストールした方が、文書ごとにテンプレートをコピーしなくてよいので楽です。
インストール方法は以下のとおり。
## jecon.bst
jplain.bstのあるフォルダ（`C:/w32tex/share/texmf-dist/pbibtex/bst`など）にファイルを配置
## PrettyLatexReport.sty
`C:/w32tex/share/texmf-local/tex/latex/PrettyLatexReport` に`PrettyLatexReport.sty`ファイルを配置後、コマンドプロンプトから`mktexlsr`を叩く。

Texstudio使用者は、`PrettyLatexReport.cwl`を`%APPDATA%\texstudio\completion\user`に入れるとエディタで補完が効くようになります。
