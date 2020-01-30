# 概要
研究室内で使っていた、レポート用のLatexテンプレートです。
宇宙工学が専門の研究室なので、参考文献の書き方はjeconを使ってその流儀に合わせてあります。

テンプレートと名乗っていますが、ドキュメントクラスにbxjsarticleを使用しているなんちゃってテンプレートです。
その他よく使うであろうパッケージを`PrettyLatexReport.sty`にまとめています。
手抜きで作った分、改変はしやすかろうと思います。

# 使い方
基本的にはリポジトリの`template.tex`をリネームして使ってください。

日本語が文章中に含まれる場合にはuplatex, upbibtex ないしは platex, pbibtexを使用してコンパイルしてください。
汎用性の観点から前者を推奨します。
`template.tex`で読み込んでいるドキュメントクラスはxetexなどにも対応しています。
platexを使用する際には`\documentclass`のオプションをuplatexからplatexに変更してください。
bibtexのままコンパイルしようとすると、巨大な中間ファイルが生成される場合がありますので注意してください。

`bxjsarticle`の読み込み時に`draft`オプションをつけると図が描画されなくなり、コンパイル時間を短縮できます。
文章確認の際に便利です。
~~~
%\documentclass[a4paper,uplatex,dvipdfmx,ja=standard,11pt,draft]{bxjsarticle}
~~~

輪講（力学ゼミ）用出力は次のように`dynamics`オプションをつけることで有効となり、CONTENTS(担当ページ数)が`\maketitle`部に表示されます。

~~~
\usepackage[dynamics]{PrettyLatexReport} % for dynamics seminar
~~~

`\title`, `\author`, `\date`, `\contents`はパラメータ指定が必須です(`\contents`は力学ゼミの場合のみ)。

引用文献は`\thebibliography`環境を使って書いてもよいですが、いい感じの書式になるようjecon.bstを編集してあるので、bibファイルから読み込むと楽です。

jeconやスタイルファイルは、文書本体と同じフォルダに置いても機能します。
ですが、Latexの適当なフォルダにインストールすると、文書ごとにスタイルファイルなどをコピーしなくてよいので楽です。
インストール方法は以下のとおり。
## jecon.bst
`C:/w32tex/share/texmf-local/pbibtex/bst`などにファイルを配置後、コマンドプロンプトから`mktexlsr`を叩く。
## PrettyLatexReport.sty
`C:/w32tex/share/texmf-local/tex/latex/PrettyLatexReport` に`PrettyLatexReport.sty`ファイルを配置後、コマンドプロンプトから`mktexlsr`を叩く。

Texstudio使用者は、`PrettyLatexReport.cwl`を`%APPDATA%\texstudio\completion\user`に入れるとエディタで補完が効くようになります。
