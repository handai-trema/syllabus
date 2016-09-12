# 情報ネットワーク学演習II

## はじめに

本演習ではネットワーク制御技術 SDN/OpenFlow を紹介します。大阪大学の授業公式ページは[こちら](http://www.ane.cmc.osaka-u.ac.jp/~hasegawa/mdwiki/mdwiki.html#!lectures/ein2-2016.md)です。

### 演習の内容

演習でカバーする内容は次の通りです。

* ネットワークのソフトウェア制御や仮想化の仕組み
* OpenFlowプログラミング
* SDNを使ったアプリケーション開発
* 複数人でのソフトウェア分散開発

本演習で使うテキストは「[TremaでOpenFlowプログラミング](http://yasuhito.github.io/trema-book/)」です。オンラインで読めますが、書籍も[発売しています](https://www.amazon.co.jp/dp/4774179833/)。

### インストラクタ

* **インストラクタ:**
  * 高宮 安仁 (たかみや やすひと), [yasuhito@gmail.com](mailto:yasuhito@gmail.com)
* **TA**
  * 石野 正典 (いしの まさのり), [m-ishino@ist.osaka-u.ac.jp](mailto:m-ishino@ist.osaka-u.ac.jp)
  * 大歳 達也 (おおとし たつや), [t-otoshi@ist.osaka-u.ac.jp](mailto:t-otoshi@ist.osaka-u.ac.jp)

内容についての質問やバグ報告は [GitHub のイシュー](https://github.com/advanced-js/syllabus/issues)でも受け付けています。

### 成績評価

* 出席 30%、レポート 40%、プレゼンテーション 30%
* グループ演習課題では、どれだけコードを書いたかという点も評価の対象になります

### 課題提出の注意

ソースコードやアイデアの再利用はソフトウェア開発の基本です。職業プログラマでも、すべてをイチから開発することはありません。この演習ではあえて、他の学生のソースコードやファイルは誰からも見える状態になっています。他の人を参考にしたりそこから学ぶことを推奨します。

ただし、他人のソースコードのまる写しは**減点の対象になりえます** (変数名を変えてコピペしても、[ツール](https://github.com/seattlerb/flay)を使えばすぐに分かります)。ただし、どうしてもコードが似てしまう場合もあります。その場合には、どうしてそのようなコードになったのか、レポートにはきちんと説明を書いてください。

もし、GitHubやインターネットで見つけたソースコードや文章を流用する場合には、元のコピーライトとライセンスを尊重してください。提出物の中にコメントとして、流用した部分のコピーライトとライセンス、URLなどを明記してください。


## 第1回 (10/5)

情報ネットワーク学演習IIへようこそ! 第1回は、SDNの基礎概念 --- ネットワークの動作をプログラミングする --- を紹介します。

SDNプログラミングを始めるにあたって、まずは Git と GitHub の使い方を学びます。本演習では演習問題を GitHub で配布し、課題の提出も GitHub で行います。演習に参加するには Git の知識が必要ですので、必ず習得してください。

SDNプログラミング環境として[Trema](https://github.com/handai-trema/self_intro)を使います。Tremaは OpenFlow プログラミングのためのプログラミングフレームワークです。定番の Hello World から始め、OpenFlow のコントローラの動作や、イベントドリブンモデル、そしてプログラミング言語 Ruby の基礎を学びます。

### イントロダクション

1. イントロダクション ([スライド](http://handai-trema.github.io/deck/week1/sdn_course_intro.pdf))
2. SDN/OpenFlow入門 ([スライド](http://handai-trema.github.io/deck/sdn_intro.pdf))

### Git/GitHub入門

1. Git 入門 ([スライド](http://handai-trema.github.io/deck/week1/git_intro.html#1)) ([リンク集](https://github.com/handai-trema/deck/blob/develop/week1/git.md))
2. GitHub 入門
3. [GitHub](https://github.com/)のアカウント作成 ([GitHubのドキュメント](https://help.github.com/articles/signing-up-for-a-new-github-account/))

### Hello Trema

1. 課題用VMのセットアップ
2. Hello Trema ([スライド](http://handai-trema.github.io/deck/week1/hello_trema.pdf))
3. Ruby 入門 ([スライド](http://handai-trema.github.io/deck/week1/ruby_intro.pdf)) ([参考書・参考サイト](https://github.com/handai-trema/deck/blob/develop/week1/ruby.md))
4. Ruby のテクニック ([スライド](http://handai-trema.github.io/deck/week1/advanced_ruby.pdf))

## 第2回 (10/12)

準備中
