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

### 事前準備

1. VM のセットアップ:
   プログラミング演習に使う VM イメージを配布しています。授業までに[手順に従ってセットアップ](https://github.com/handai-trema/deck/blob/develop/week1/VM.md)しておいてください。
2. GitHub アカウント:
   課題はすべて [GitHub](https://github.com/) 上に提出してもらいます。
   [GitHubのドキュメント](https://help.github.com/articles/signing-up-for-a-new-github-account/)に従ってアカウントを作っておいてください。
3. Ruby の予習:
   演習ではプログラミング言語として Ruby を使います。必要な構文などは授業で説明しますが、ある程度はオブジェクト指向の基本を知っている前提で授業を進めます。こちらの[リンク集](https://github.com/handai-trema/deck/blob/develop/week1/ruby.md)を参考に、あらかじめ Ruby を予習しておいてください。

### 課題提出の注意

ソースコードやアイデアの再利用はソフトウェア開発の基本です。職業プログラマでも、すべてをイチから開発することはありません。この演習ではあえて、他の学生のソースコードやファイルは誰からも見える状態になっています。他の人を参考にしたりそこから学ぶことを推奨します。

ただし、他人のソースコードのまる写しは**減点の対象になりえます** (変数名を変えてコピペしても、[ツール](https://github.com/seattlerb/flay)を使えばすぐに分かります)。ただし、どうしてもコードが似てしまう場合もあります。その場合には、どうしてそのようなコードになったのか、レポートにはきちんと説明を書いてください。

もし、GitHubやインターネットで見つけたソースコードや文章を流用する場合には、元のコピーライトとライセンスを尊重してください。提出物の中にコメントとして、流用した部分のコピーライトとライセンス、URLなどを明記してください。

## 第1回 (10/5)

情報ネットワーク学演習IIへようこそ! 第1回は、SDNの基礎概念 --- ネットワークの動作をプログラミングする --- を紹介します。

SDNプログラミングを始めるにあたって、まずは Git と GitHub の使い方を学びます。本演習では演習問題を GitHub で配布し、課題の提出も GitHub で行います。演習に参加するには Git の知識が必要ですので、必ず習得してください。

SDNプログラミング環境として[Trema](https://github.com/handai-trema/self_intro)を使います。Tremaは OpenFlow プログラミングのためのプログラミングフレームワークです。定番の Hello World から始め、OpenFlow のコントローラの動作や、イベントドリブンモデル、そしてプログラミング言語 Ruby の基礎を学びます。

### イントロダクション

1. イントロダクション
   - [スライド](http://handai-trema.github.io/deck/week1/sdn_course_intro.pdf)
2. SDN/OpenFlow入門
   - [スライド](http://handai-trema.github.io/deck/week1/sdn_intro.pdf)

### Git/GitHub入門

1. Git 入門
   - [スライド](http://handai-trema.github.io/deck/week1/git.html#1)
   - [Git 入門 参考書・参考サイト](https://github.com/handai-trema/deck/blob/develop/week1/git.md)
2. GitHub 入門
   - [スライド](http://handai-trema.github.io/deck/week1/github.html#1)
   - 課題: [GitHub で自己紹介](https://github.com/handai-trema/self_intro)

### Hello Trema

1. Hello Trema
   - [スライド](http://handai-trema.github.io/deck/week1/hello_trema.pdf)
   - [課題用リポジトリ](https://classroom.github.com/assignment-invitations/1432105c8d4577dee37a0e001de48830)
   - テキスト: [3章 "Hello, Trema!"](http://yasuhito.github.io/trema-book/#hello_trema)
2. Ruby 入門・Tremaのハンドラ
   - [スライド](http://handai-trema.github.io/deck/week1/ruby_intro.pdf)
   - 課題: [スイッチの切断イベント](https://github.com/handai-trema/deck/blob/develop/week1/assignment_bye_switch.md)
3. イントロスペクション
   - [スライド](http://handai-trema.github.io/deck/week1/ruby_introspection.pdf)
   - 課題: [Hello Trema](https://github.com/handai-trema/deck/blob/develop/week1/assignment_hello_trema.md)


## 第2回 (10/12)

OpenFlow や Trema の概要がわかったところで、もう少し細かい仕様の理解と実用的な OpenFlow プログラミングに進みましょう。

まずは OpenFlow 1.0 仕様のポイントとよく使う用語を押さえます。そして、本格的な OpenFlow プログラミングの第一歩として、スイッチのフローテーブル書き換えに挑戦します。OpenFlow コントローラ用マイクロベンチマークツール Cbench を題材に、OpenFlow の重要なメッセージである Packet In と Flow Mod メッセージの使い方を学びます。

最後に、一般的な L2 スイッチを OpenFlow で実装する方法を学びます。L2 スイッチの仕組みと OpenFlow での実装方法が分かれば、これをベースに改造することでより複雑な OpenFlow アプリケーションを作れるようになるでしょう。

1. OpenFlow プロトコル入門
   - [スライド](http://handai-trema.github.io/deck/week2/open_flow.pdf)
   - [Slide](https://github.com/handai-trema/deck/raw/develop/week2/open_flow_english.pdf)
   - テキスト: [1章 "OpenFlow の仕組み"](http://yasuhito.github.io/trema-book/#how_does_openflow_work)

2. cbench: Packet In と Flow Mod メッセージを使ってみよう
   - [スライド](http://handai-trema.github.io/deck/week2/cbench.pdf)
   - [Slide](http://handai-trema.github.io/deck/week2/cbench_english.pdf)
   - 課題: [Cbenchの高速化](https://github.com/handai-trema/deck/blob/develop/week2/assignment_cbench.md)
   - Assignment: [Accelerating Cbench](https://github.com/handai-trema/deck/blob/develop/week2/assignment_cbench_english.md)
   - [課題用リポジトリ](https://classroom.github.com/assignment-invitations/d8e5b9494f8c31c2de889464b6ab4038)
   - テキスト: [5章 "マイクロベンチマークCbench"](http://yasuhito.github.io/trema-book/#cbench)

3. L2スイッチを作ろう
   - [スライド](http://handai-trema.github.io/deck/week2/learning_switch.pdf)
   - [Slide](http://handai-trema.github.io/deck/week2/learning_switch_english.pdf)
   - 課題: [複数スイッチ対応](https://github.com/handai-trema/deck/blob/develop/week2/assignment_learning_switch.md)
   - Assignment: [Multi-Learning Switch](https://github.com/handai-trema/deck/blob/develop/week2/assignment_learning_switch_english.md)
   - [課題用リポジトリ](https://classroom.github.com/assignment-invitations/12547fca10261e602080952dff521266)
   - テキスト: [7章 "すべての基本、ラーニングスイッチ"](http://yasuhito.github.io/trema-book/#learning_switch)


## 第3回 (10/19)

次週から始まる実機 OpenFlow スイッチを使った演習に向けて、物理ネットワークで便利に使える実用的なコントローラを実装しましょう。

まずは高価なネットワーク機器「インテリジェント・パッチパネル」の簡易版を OpenFlow で作ります。基本的な FlowMod メッセージと Trema プログラミングだけで、実用性の高いネットワーク機器を作れます。

そして、最も普及している OpenFlow バージョン 1.3 の基本を学びます。OpenFlow 1.0 で明らかになっている欠点と OpenFlow 1.3 での解決方法を理解しましょう。ここで習得した OpenFlow 1.3 の知識は後半のルータ実装に使います。


1. パッチパネルを作ろう
   - [スライド](http://handai-trema.github.io/deck/week3/patch_panel.pdf)
   - [Slide](https://github.com/handai-trema/deck/raw/develop/week3/patch_panel_english.pdf)
   - 課題: [パッチパネルの機能拡張](https://github.com/handai-trema/deck/blob/develop/week3/assignment_patch_panel.md)
   - Assignment: [Extending Patch Panel](https://github.com/handai-trema/deck/blob/develop/week3/assignment_patch_panel_english.md)
   - [課題用リポジトリ](https://classroom.github.com/assignment-invitations/bbb97d7a62c248e391ab75fef095402c)
   - テキスト: [6章 "インテリジェントなパッチパネル"](http://yasuhito.github.io/trema-book/#patch_panel)
2. OpenFlow 1.3 版 L2 スイッチを作ろう
   - [スライド](http://handai-trema.github.io/deck/week3/learning_switch13.pdf)
   - [Slide](https://github.com/handai-trema/deck/raw/develop/week3/learning_switch13_english.pdf)
   - 課題: [マルチプルテーブルを読む](https://github.com/handai-trema/deck/blob/develop/week3/assignment_learning_switch13.md)
   - Assignment: [Inspecting Multiple Tables](https://github.com/handai-trema/deck/blob/develop/week3/assignment_learning_switch13_english.md)
   - [課題用リポジトリ](https://classroom.github.com/assignment-invitations/12547fca10261e602080952dff521266)(「L2スイッチを作ろう」と同じリポジトリです)
   - テキスト: [8章 "OpenFlow1.3版ラーニングスイッチ"](http://yasuhito.github.io/trema-book/#learning_switch13)
3. OpenFlow 1.3 プロトコル入門
   - [スライド](http://handai-trema.github.io/deck/week3/open_flow13.pdf)
   - [Slide](https://github.com/handai-trema/deck/raw/develop/week3/open_flow13_english.pdf)
   - テキスト: [2章 "OpenFlow の仕様"](http://yasuhito.github.io/trema-book/#openflow_spec)


## 第4回 (10/26)

今回は実機演習です。今までは作ったコントローラをソフトウェアスイッチと接続してきましたが、今回は実機の OpenFlow スイッチに接続し動作させます。

まずは実機 OpenFlow スイッチの操作方法や仮想スイッチとの違いを説明します。また Trema で作ったコントローラと接続するための設定を行います。

そして、いよいよ実機 OpenFlow スイッチを便利なパッチパネルとして動作させます。先週作成した「インテリジェント・パッチパネル」コントローラとの接続に挑戦することで、実機 OpenFlow スイッチの扱いやトラブルシュートに慣れましょう。

1. 実機演習
   - [スライド](http://handai-trema.github.io/deck/week4/hardware_switch.pdf)


## 第5回 (11/2)

今まで学んだ知識を総動員して、ラーニングスイッチよりも高度なルータの実装に挑戦しましょう。まずは、スイッチとルータの違いをきちんと理解することからスタートです。

後半ではルータが持つ重要な機能であるルーティングテーブルの詳細を見ていきましょう。ルータは実に巧妙な仕組みで転送先の情報を管理します。

1. ルータを作ろう (前編)
   - [スライド](http://handai-trema.github.io/deck/week5/simple_router1.pdf)
   - [Slide](http://handai-trema.github.io/deck/week5/simple_router1_english.pdf)
   - テキスト: [12章 "ルータ (前編)"](http://yasuhito.github.io/trema-book/#router_part1)
2. ルータを作ろう (後編)
   - [スライド](http://handai-trema.github.io/deck/week5/simple_router2.pdf)
   - [Slide](http://handai-trema.github.io/deck/week5/simple_router2_english.pdf)
   - テキスト: [13章 "ルータ (後編)"](http://yasuhito.github.io/trema-book/#router_part2)
   - [課題用リポジトリ](https://classroom.github.com/assignment-invitations/7463a3fb27a0e49d93f202b2f4e3a748)
   - 課題: [ルータのCLIを作ろう](https://github.com/handai-trema/deck/blob/develop/week5/assignment_simple_router.md)
   - Assignment: [Developing Router CLI](https://github.com/handai-trema/deck/blob/develop/week5/assignment_simple_router_english.md)


## 第6回 (11/9)

データセンターのような大規模ネットワークを制御する前準備として、ネットワークトポロジを OpenFlow で検出してみましょう。OpenFlow ではコントローラがトポロジ情報を管理します。ネットワーク全体を集中管理するコントローラがトポロジも把握することで、パケットを思いのままに転送できます。

1. ネットワークトポロジを検出しよう
   - [スライド](http://handai-trema.github.io/deck/week6/topology.pdf)
   - [Slide](http://handai-trema.github.io/deck/week6/topology_english.pdf)
   - テキスト: [15章 "ネットワークトポロジを検出する"](http://yasuhito.github.io/trema-book/#topology)
   - グループ課題1: [実機でトポロジを動かそう](https://github.com/handai-trema/deck/blob/develop/week6/assignment1_topology.md)
   - Assignment 1: [Run "Topology" on a physical switch](https://github.com/handai-trema/deck/blob/develop/week6/assignment_topology.md)
   - グループ課題2: [トポロジコントローラの拡張](https://github.com/handai-trema/deck/blob/develop/week6/assignment2_topology.md)
   - Assignment 2: [Extending "Topology"](https://github.com/handai-trema/deck/blob/develop/week6/assignment2_topology_english.md)
   - [グループ課題用リポジトリ](https://classroom.github.com/group-assignment-invitations/edf6cbbe9843c977d228bde7a62a98d1)


## 第7回 (11/16)

検出したトポロジ情報を使って、たくさんのスイッチを連携させてみましょう。たくさんの OpenFlow スイッチがつながった環境では、パケットを目的地まで転送するためにスイッチを連携させる必要があります。複数の OpenFlow スイッチを連携し、1 台の大きな仮想スイッチとして扱う方法を見て行きましょう。

1. たくさんのスイッチを制御する
   - [スライド](http://handai-trema.github.io/deck/week7/routing_switch.pdf)
   - [Slide](http://handai-trema.github.io/deck/week7/routing_switch_english.pdf)
   - テキスト: [16章 "たくさんのスイッチを制御する"](http://yasuhito.github.io/trema-book/#routing_switch)
   - グループ課題: [経路選択アルゴリズムの実装と可視化](https://github.com/handai-trema/deck/blob/develop/week7/assignment_routing_switch.md)
   - Assignment: [Implementing a routing algorithm and a visualization function](https://github.com/handai-trema/deck/blob/develop/week7/assignment_routing_switch_english.md)
   - [グループ課題用リポジトリ](https://classroom.github.com/group-assignment-invitations/2064a701edd70e52302d5bcf21def7a6)


## 第8回 (11/30)

IaaS (Infrastructure as a Service) の構築に必要な仮想ネットワークを OpenFlow で実現しましょう。前回解説したルーティングスイッチの応用です。

1. 仮想ネットワーク (スライス機能)
   - [スライド](http://handai-trema.github.io/deck/week8/sliceable_switch.pdf)
   - [Slide](http://handai-trema.github.io/deck/week8/sliceable_switch_english.pdf)
   - テキスト: [17章 "ネットワークを仮想化する"](http://yasuhito.github.io/trema-book/#sliceable_switch)
   - グループ課題: [スライス機能の拡張](https://github.com/handai-trema/deck/blob/develop/week8/assignment_sliceable_switch.md)
   - Assignment: [Extending the slice function](https://github.com/handai-trema/deck/blob/develop/week8/assignment_sliceable_switch_english.md)
   - [グループ課題用リポジトリ](https://classroom.github.com/group-assignment-invitations/c471116bfa738709e58f8251a5948b42)


## 第9回 (12/14)

最終課題: Mini IaaS を作ろう

1. Mini IaaS を作ろう
   - [スライド](http://handai-trema.github.io/deck/week9/mini_iaas.pdf)
