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
   - [スライド](https://github.com/handai-trema/deck/blob/develop/simple_router.pdf)
   - [テキスト 前編](http://yasuhito.github.io/trema-book/#router_part1)
   - [テキスト 後編](http://yasuhito.github.io/trema-book/#router_part2)

今回の課題には新しい Open vSwitch が必要です。次の手順で Open vSwitch をアップデートしてください。

```
$ sudo add-apt-repository ppa:suawekk/openvswitch
$ sudo apt-get update
$ sudo apt-get upgrade
```

### 第6回 (11/18)

1. グループ課題: ルータをマルチプルテーブルで実装しよう
   - [スライド](https://github.com/handai-trema/deck/blob/develop/simple_router2.pdf)

今回の課題には新しいTremaが必要です。次の手順でTremaをアップデートしてください。

```
$ bundle update
```

課題の大ヒント
```
$ sudo ovs-ofctl dump-flows br0x1 --protocols=OpenFlow13
OFPST_FLOW reply (OF1.3) (xid=0x2):
 cookie=0x0, duration=12.684s, table=0, n_packets=11, n_bytes=858, priority=0 actions=goto_table:1
 cookie=0x0, duration=12.684s, table=1, n_packets=0, n_bytes=0, priority=0,arp actions=goto_table:2
 cookie=0x0, duration=12.684s, table=1, n_packets=0, n_bytes=0, priority=0,ip actions=goto_table:3
 cookie=0x0, duration=12.674s, table=2, n_packets=0, n_bytes=0, priority=0,arp,in_port=1,arp_tpa=192.168.1.1,arp_op=1 actions=CONTROLLER:65535,move:NXM_OF_ETH_SRC[]->NXM_OF_ETH_DST[],set_field:01:01:01:01:01:01->eth_src,set_field:2->arp_op,move:NXM_NX_ARP_SHA[]->NXM_NX_ARP_THA[],move:NXM_OF_ARP_SPA[]->NXM_OF_ARP_TPA[],set_field:01:01:01:01:01:01->arp_sha,set_field:192.168.1.1->arp_spa,load:0xffff->OXM_OF_IN_PORT[],load:0x1->NXM_NX_REG1[],goto_table:6
 cookie=0x0, duration=12.665s, table=2, n_packets=0, n_bytes=0, priority=0,arp,in_port=1,arp_tpa=192.168.1.1,arp_op=2 actions=CONTROLLER:65535
 cookie=0x0, duration=12.632s, table=2, n_packets=0, n_bytes=0, priority=0,arp,in_port=2,arp_tpa=192.168.2.1,arp_op=1 actions=CONTROLLER:65535,move:NXM_OF_ETH_SRC[]->NXM_OF_ETH_DST[],set_field:02:02:02:02:02:02->eth_src,set_field:2->arp_op,move:NXM_NX_ARP_SHA[]->NXM_NX_ARP_THA[],move:NXM_OF_ARP_SPA[]->NXM_OF_ARP_TPA[],set_field:02:02:02:02:02:02->arp_sha,set_field:192.168.2.1->arp_spa,load:0xffff->OXM_OF_IN_PORT[],load:0x2->NXM_NX_REG1[],goto_table:6
 cookie=0x0, duration=12.623s, table=2, n_packets=0, n_bytes=0, priority=0,arp,in_port=2,arp_tpa=192.168.2.1,arp_op=2 actions=CONTROLLER:65535
 cookie=0x0, duration=12.654s, table=2, n_packets=0, n_bytes=0, priority=0,arp,reg1=0x1 actions=set_field:01:01:01:01:01:01->eth_src,set_field:01:01:01:01:01:01->arp_sha,set_field:192.168.1.1->arp_spa,goto_table:6
 cookie=0x0, duration=12.612s, table=2, n_packets=0, n_bytes=0, priority=0,arp,reg1=0x2 actions=set_field:02:02:02:02:02:02->eth_src,set_field:02:02:02:02:02:02->arp_sha,set_field:192.168.2.1->arp_spa,goto_table:6
 cookie=0x0, duration=12.594s, table=3, n_packets=0, n_bytes=0, priority=40024,ip,nw_dst=192.168.1.0/24 actions=move:NXM_OF_IP_DST[]->NXM_NX_REG0[],goto_table:4
 cookie=0x0, duration=12.585s, table=3, n_packets=0, n_bytes=0, priority=40024,ip,nw_dst=192.168.2.0/24 actions=move:NXM_OF_IP_DST[]->NXM_NX_REG0[],goto_table:4
 cookie=0x0, duration=12.603s, table=3, n_packets=0, n_bytes=0, priority=0,ip actions=load:0xc0a80102->NXM_NX_REG0[],goto_table:4
 cookie=0x0, duration=12.577s, table=4, n_packets=0, n_bytes=0, priority=0,reg0=0xc0a80100/0xffffff00 actions=load:0x1->NXM_NX_REG1[],set_field:01:01:01:01:01:01->eth_src,goto_table:5
 cookie=0x0, duration=12.569s, table=4, n_packets=0, n_bytes=0, priority=0,reg0=0xc0a80200/0xffffff00 actions=load:0x2->NXM_NX_REG1[],set_field:02:02:02:02:02:02->eth_src,goto_table:5
 cookie=0x0, duration=12.525s, table=5, n_packets=0, n_bytes=0, priority=1,ip actions=CONTROLLER:65535
 cookie=0x0, duration=12.520s, table=6, n_packets=0, n_bytes=0, priority=0 actions=output:NXM_NX_REG1[]
```

### 第7回 (11/25)

1. ネットワークトポロジを検出しよう
   - [スライド](https://github.com/handai-trema/deck/blob/develop/topology.pdf)
   - [テキスト](http://yasuhito.github.io/trema-book/#topology)
   - [演習用リポジトリ](https://classroom.github.com/assignment-invitations/139380be27c68b1e207771444914a482)
2. 実機のスイッチを使ってみよう
   - [スライド](https://github.com/handai-trema/deck/blob/develop/topology2.pdf)

今回の課題には Graphviz が必要です。次の手順で graphviz パッケージをインストールしてください。

```
$ apt-get install graphviz
```

### 第8回 (12/2)
1. たくさんのスイッチを制御しよう
   - [テキスト](http://yasuhito.github.io/trema-book/#routing_switch)
   - [演習用リポジトリ](https://classroom.github.com/group-assignment-invitations/551c05d1103894adb81df27a8b487e94)

### 第9回 (12/9)
1. 仮想ネットワークを作ろう
   - [テキスト](http://yasuhito.github.io/trema-book/#sliceable_switch)

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
