# 情報ネットワーク学演習II

授業の[公式ページ](http://www.ane.cmc.osaka-u.ac.jp/~hasegawa/mdwiki/mdwiki.html#!lectures/ein2-2015.md)も読んでください。

* **インストラクタ:**
  * 高宮 安仁 (たかみや やすひと), [yasuhito@gmail.com](mailto:yasuhito@gmail.com)
* **TA**
  * 石野 正典 (いしの まさのり), [m-ishino@ist.osaka-u.ac.jp](mailto:m-ishino@ist.osaka-u.ac.jp)
  * 豊永 慎也 (とよなが しんや), [s-toyonaga@ist.osaka-u.ac.jp](mailto:s-toyonaga@ist.osaka-u.ac.jp)
* **Need help?**
  * [![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/handai-trema/syllabus?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)
    * チャットルームでの質問はすべてメールでも届きますので、もし誰もいない場合でも気軽に質問してください
  * [GitHub のイシュー](https://github.com/advanced-js/syllabus/issues)を使った質問も歓迎です。


## 事前準備

* [GitHub](https://github.com/)のアカウントを作る
  * 課題提出は GitHub で行います。事前に[GitHubのアカウントを作って](https://help.github.com/articles/signing-up-for-a-new-github-account/)おいてください。
* [Virtual Box](https://www.virtualbox.org/)をインストールする
* 課題用の[VMイメージ](http://www.ane.cmc.osaka-u.ac.jp/~hasegawa/mdwiki/mdwiki.html#!lectures/2015-ein2/ensyuuVB1.ova)をVirtual Boxにインポートする
  1. VirtualBox のメニュー→ファイル→仮想アプライアンスのインポート→ensyuuVB1.ovaを選択→次へ→インポート
  2. インポートした VM イメージを起動。ユーザ名、パスワードは `ensyuu2`

なおRubyやLinuxに慣れていて開発環境をすでに持っている人は、VMを使わずに自前の開発環境を使ってもらってもかまいません。


## 課題

### 第1回 (10/7)

1. SDN/OpenFlow入門
   - [スライド](http://handai-trema.github.io/deck/sdn_intro.pdf)
2. Git&GitHub入門: GitやGitHubの練習として自己紹介を書いてコミットしよう
   - [スライド](http://handai-trema.github.io/deck/git.html#1)
   - [演習用リポジトリ](https://github.com/handai-trema/self_intro)

### 第2回 (10/14)

1. Hello, Trema: Tremaで簡単なOpenFlowコントローラを書こう
   - [スライド](https://github.com/handai-trema/deck/blob/develop/hello_trema.pdf)
   - [演習用リポジトリ](https://github.com/handai-trema/hello_trema)
2. cbench: Packet In と Flow Mod メッセージを使ってみよう
   - [スライド](https://github.com/handai-trema/deck/blob/develop/cbench.pdf)
   - [演習用リポジトリ](https://classroom.github.com/assignment-invitations/4dd0b372d5813f33997dbe3b0af5919b)

### 第3回 (10/21)

1. L2スイッチを作ろう
   - [スライド](https://github.com/handai-trema/deck/blob/develop/learning_switch.pdf)
   - [演習用リポジトリ](https://classroom.github.com/assignment-invitations/df8da63f5440cbc0286f94b227da9fa3)

### 第4回 (10/28)

1. OpenFlow1.3でL2スイッチを作ろう
   - [スライド](https://github.com/handai-trema/deck/blob/develop/learning_switch13.pdf)
   - 配布した learning_switch13.rb いくつかバグがありました。[こちら](https://github.com/trema/learning_switch/blob/develop/lib/learning_switch13.rb)を使ってください。

### 第5回 (11/11)

1. グループ課題: OpenFlow1.3でルータを作ろう
   - [テキスト 前編](http://yasuhito.github.io/trema-book/#router_part1)
   - [テキスト 後編](http://yasuhito.github.io/trema-book/#router_part2)
   - [演習用リポジトリ(まだクリックしないで!)](https://classroom.github.com/group-assignment-invitations/18cf775b61c35cc99a5062ea8bba4aa9)

今回の課題には新しい Open vSwitch が必要です。次の手順で Open vSwitch をアップグレードしてください。

```
$ sudo add-apt-repository ppa:suawekk/openvswitch
$ sudo apt-get update
$ sudo apt-get upgrade
```

## 必須の読み物

* [TremaでOpenFlowプログラミング](http://yasuhito.github.io/trema-book/)

本演習で使うテキストで、フリーで読めます。技術評論社から発売中の[OpenFlow実践入門](http://www.amazon.co.jp/dp/4774154652/)の続編です。演習ごとに読むべき章は連絡します。


## 推奨する読み物

### Ruby

演習ではプログラミング言語として Ruby を使います。Ruby を独学するためのサイトや書籍を紹介します。ある程度は Ruby やオブジェクト指向の基本を知っている前提で授業を進めますので、演習が始まる前に各自で習得しておいてください。

#### Ruby 初心者向け
はじめて Ruby に触れる人は、次のサイトで基礎をマスターしてください。
Ruby のインストールから実行方法まで、丁寧な解説が載っています。

* Rubyプログラミングを始めるための基礎知識とインストール http://www.atmarkit.co.jp/ait/articles/1402/27/news042.html

基礎が分かったら Ruby の基本的な構文を押さえましょう。
次のサイトでは、演習で使う Ruby バージョン 2.0/2.1 の構文が学べます。

* Ruby 2.1の基本構文／基本文法まとめ＆Pryの使い方
  http://www.atmarkit.co.jp/ait/articles/1403/26/news030.html

最後に Ruby のオブジェクト指向を理解してください。
ここまでできれば、演習に必要な知識はすべて身に付きます。

* Rubyのオブジェクト指向におけるクラスとモジュール、継承、Mixin、アクセス制御の使い方
http://www.atmarkit.co.jp/ait/articles/1408/28/news035.html

もうすこしやってみたい人のために、いくつか有名な Ruby 入門サイトを紹介しておきます。

* Try Ruby
  https://www.codeschool.com/courses/try-ruby

  ブラウザ上で Ruby を動かしながら学べるチュートリアルです。

* ホワイの (感動的) Ruby ガイドhttp://www.aoky.net/articles/why_poignant_guide_to_ruby/
  有名な Ruby ハッカーによる入門マンガです。クセが強い部分もありますが、Ruby プログラミングの世界を俯瞰できる良い内容です。

#### Ruby 初心者向け (書籍)

Web ページよりも本が好きな人は、次の入門書をどうぞ。

* パーフェクトRuby (書籍、有料)
  http://www.amazon.co.jp/dp/4774158798

#### 中・上級者向け

本格的に Ruby プログラミングに取り組みたい人向けに、いくつか紹介しておきます。

* RubyTapas (動画、有料)
  http://www.rubytapas.com/
  Ruby でよく使うイディオムを紹介しているスクリーンキャストです。どれも 5 分くらいの長さで手頃です。
* メタプログラミング Ruby (書籍、有料)
  http://www.amazon.co.jp/dp/4048687158
  Ruby プログラムを短く書くためのテクニックをたくさん紹介しています。
  プロっぽいプログラムを書きたい人は読んでください。

### Git と GitHub

演習では Git と GitHub をたくさん使うので、あらかじめ慣れておいてください。なお Git とはバージョン管理ツールの一種です。GitHub は Git を使ってソースコードを公開できるサービスの一つです。

* [サルでもわかるGit入門](http://www.backlog.jp/git-guide/)
* [いつやるの？Git入門 v1.1.0](http://www.slideshare.net/matsukaz/git-28304397)
* [こわくないGit](http://www.slideshare.net/kotas/git-15276118)
* [Learn Git Branching](http://k.swd.cc/learnGitBranching-ja/)

このほかにも、はてなブックマークで["git" + "入門" タグの付いた人気記事を検索](http://b.hatena.ne.jp/search/tag?safe=on&sort=popular&q=git+%E5%85%A5%E9%96%80)すれば、人気記事がたくさんみつかります。


## 成績評価

* 出席 30%、レポート 40%、プレゼンテーション 30%
* グループ演習課題では、どれだけコードを書いたかという点も評価の対象になります


## 注意書き

ソースコードやアイデアの再利用はソフトウェア開発の基本です。職業プログラマでも、すべてをイチから開発することはありません。この演習ではあえて、他の学生のソースコードやファイルは誰からも見える状態になっています。他の人を参考にしたりそこから学ぶことを推奨します。

ただし、他人のソースコードのまる写しは**減点の対象になりえます** (変数名を変えてコピペしても、[ツール](https://github.com/seattlerb/flay)を使えばすぐに分かります)。ただし、どうしてもコードが似てしまう場合もあります。その場合には、どうしてそのようなコードになったのか、レポートにはきちんと説明を書いてください。

もし、GitHubやインターネットで見つけたソースコードや文章を流用する場合には、元のコピーライトとライセンスを尊重してください。提出物の中にコメントとして、流用した部分のコピーライトとライセンス、URLなどを明記してください。
