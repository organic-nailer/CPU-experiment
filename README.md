<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [CSG-CPU-experiment](#csg-cpu-experiment)
- [ver](#ver)
- [前準備](#%E5%89%8D%E6%BA%96%E5%82%99)
- [実験目的](#%E5%AE%9F%E9%A8%93%E7%9B%AE%E7%9A%84)
    - [身につく技術](#%E8%BA%AB%E3%81%AB%E3%81%A4%E3%81%8F%E6%8A%80%E8%A1%93)
- [1日目](#1%E6%97%A5%E7%9B%AE)
  - [自己紹介](#%E8%87%AA%E5%B7%B1%E7%B4%B9%E4%BB%8B)
  - [このセミナー開始にあたって](#%E3%81%93%E3%81%AE%E3%82%BB%E3%83%9F%E3%83%8A%E3%83%BC%E9%96%8B%E5%A7%8B%E3%81%AB%E3%81%82%E3%81%9F%E3%81%A3%E3%81%A6)
    - [環境設定](#%E7%92%B0%E5%A2%83%E8%A8%AD%E5%AE%9A)
    - [テキスト](#%E3%83%86%E3%82%AD%E3%82%B9%E3%83%88)
  - [1日目終了後課題](#1%E6%97%A5%E7%9B%AE%E7%B5%82%E4%BA%86%E5%BE%8C%E8%AA%B2%E9%A1%8C)
- [2日目](#2%E6%97%A5%E7%9B%AE)
  - [2日目課題](#2%E6%97%A5%E7%9B%AE%E8%AA%B2%E9%A1%8C)
- [3日目](#3%E6%97%A5%E7%9B%AE)
  - [3日目課題](#3%E6%97%A5%E7%9B%AE%E8%AA%B2%E9%A1%8C)
  - [単純命令セット](#%E5%8D%98%E7%B4%94%E5%91%BD%E4%BB%A4%E3%82%BB%E3%83%83%E3%83%88)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# CSG-CPU-experiment
- [CSG-CPU-experiment](#csg-cpu-experiment)
- [ver](#ver)
- [前準備](#前準備)
- [実験目的](#実験目的)
    - [身につく技術](#身につく技術)
- [1日目](#1日目)
  - [自己紹介](#自己紹介)
  - [このセミナー開始にあたって](#このセミナー開始にあたって)
    - [環境設定](#環境設定)
    - [シミュレータ(Modelsim)の準備](#シミュレータmodelsimの準備)
    - [テキスト](#テキスト)
  - [1日目終了後課題](#1日目終了後課題)
- [2日目](#2日目)
  - [2日目課題](#2日目課題)
- [3日目](#3日目)
  - [3日目課題](#3日目課題)
  - [単純命令セット](#単純命令セット)

# ver
* 2022/11/1 2022年度のTA用に改定

TODO: 学生配布用のrepoを作成した方が良い。作成する回路は空白にしておかないと正解が書いてあるので面白くない。

# 前準備

* Slack開設

* Githubアカウント作成

* VSCodeインストール+Verilogシンタックス登録（すると便利）

# 実験目的

- シングルサイクルCPUで四則演算を行うこと

具体的には提示された簡易命令セットで最小構成のマイCPUを作り、CPUの基本を作って理解する。

### 身につく技術

* SystemVerilogの扱い、シミュレーション

* 論理回路の理解

* CPU、コンピュータ・アーキテクチャに関する理解


# 1日目
## 自己紹介

* 吉岡、TAの自己紹介

* みんなの自己紹介

~~ペアを作成~~

## このセミナー開始にあたって

この授業の目的は**研究体験**であると解釈しています。まず研究と授業は全然違います。授業は基本的に受け身でよく、最悪授業に出席し言われた通りの範囲を勉強しレポートやテストに望めばOKです。

一方で研究は最先端の更にその先を目指す行為です。そのため教員もまだ知らないことも勉強する必要があり、研究遂行に必要な知識やスキルを教員が全て丁寧に教えることはありません（というか無理です）。もちろんベースとなる技術や論文、教科書を最初に提示しますし、輪講などで基本は教えます（それは教員の義務です）が卒論・修論を書くには**自分で情報を調べること**がかなり重要となります。

これは会社に入っても同様であり、今はどの会社でも新人研修よりもOJTで仕事スキルを付けることが多いかと思います。OJTというと聞こえは良いのですが、メンターは自分の仕事をしながらあなたの指導をするので大学の授業のように懇切丁寧に教えてくれるわけではなく、要点を絞って自分で調べてもわからない範囲で質問をする必要があります。なので研究における姿勢と仕事の姿勢はちょっと似ていますね。

### 環境設定

* Slack、github、VSCodeの設定をフォロー

  ### シミュレータ(Modelsim)の準備

`ModelSim`をインストールします。インストール方法については[リンク](https://sites.google.com/site/playsystemverilog/)を参照してください。

Windows、Linux使用の方は[リンク](https://drive.google.com/file/d/1X2uY70ez27wvgCxB3hqmlao8dA3sdv7_/view?usp=sharing)からModelSimをダウンロードし、インストールしてください。

ModelSimは記述したハードウェアコード（Verilog)のコンパイラ＋シミュレータとなっています。ハードウェアでは波形表示で結果を見ることが多く、GUIソフトが必要となり結果としてファイルサイズなども大きくなってしまいます。ModelSimはフリーの古いソフトですが、今回の実験に必要な結果は得られるはずです。Xilinx社のVivadoの方が高性能ですが有料だったため今回は見送りました。

(MACの方向け)

https://qiita.com/RotaryKer/items/d8f6d218962c213b0577

Brewでシミュレータ（IcarusVerilog, WaveGen)が入ります。試してみてください。（当方MAC持っていないため未確認です）

* (インストールできたら)ModelSimの動作テスト

  ⇨[説明](https://sites.google.com/site/playsystemverilog/)を元に`00_helloworld_verilog/helloworld.v`を実行してみましょう。

* 半加算器をModelSimで動かそう

  （参考）Verilogのテストベンチの書き方

  https://www.macnica.co.jp/business/semiconductor/articles/intel/110605/

* （参考）Verilogの書き方について

  Verilogについてネットを探すといくつか文法についての記事が見つかります。
  教科書の4章を参考にする他、例えばQiitaのこの記事

  https://qiita.com/thtitech/items/8cc898dda7a10780f495

  など参照してください。

### テキスト

本セミナーでは**ディジタル回路設計とコンピュータアーキテクチャ[ARM版]**をベースに勉強します。この本はCPUの作り方まで勉強できる上、比較的わかりやすく書かれています。

3章までは必修のディジタル・アナログ回路の復習ですがデジタル回路は後半なのでまだ履修していないかもですね。

最初から読んでいきましょう、そして4章以降は新たに学ぶ内容です。

まず今日は4章の途中まで読むことを目標としましょう。

そして4章に書いてある例題をいくつかVerilogで記述し動作を確認してみましょう。

## 1日目終了後課題
設計してテストベンチを書き、動作を確認してみましょう。
1.  入力a,bを与えられてa>bならば1を、a≦bならば0を出力する比較器を設計してください。
2. 入力aを入力bでビットシフト（2^b倍する）回路を設計してください。
3. a*bを行う掛け算回路を設計してください。
4. 組み合わせ回路と順序回路の違いを説明してください。
5. 2.8章の2:1マルチプレクサを実装してください。
6. 4:1マルチプレクサを実装してください。
7. 2:4デコーダを実装してください。
8. (チャレンジ課題）テキスト1.4章にある通り、与えられた加算器は符号付き2の補数を用いたものでした（Verilogでは特に宣言をしないと2の補数で実装されます）符号なし表現を用いた（uintと呼ばれます)加算器を作ってみてください。
9. Dフリップフロップはとても重要な回路です。回路動作を説明できるようにしてください。

詰まったら4章を見てみると実装が載っています。確認してみて下さい。

# 2日目
*メモ*：去年はこの日は吉岡がずっと会議だったため、学生に自習してもらいました。各自教科書を読み進めていたのですが、あまり進捗は良くなかったのでもう少しアクティビティぽくした方がよいかも。

教科書の：
・`4.1-4.4, 4.9`を読む。

・`5.1-5.2, 5.4`を読む。（CPU設計にそこまで関係ないので流し読みで良いです）

・6章はCPU設計の本質です。`6.1-6.4`を本気で読みましょう。

Slackで送った課題が終わっていない方は課題にチャレンジしてみよう。

## 2日目課題
1. カウンタ回路を設計してください。0から255までの値を数えられるように設計し、テストベンチで確認してください。
（カウンタ回路はクロックが入るたびに出力が1増える回路です。
リセット信号をもたせ、リセットが1の時は出力は0になり、リセットが0の時はカウンタ動作するようにしてください）

2. 足し算、引き算、掛け算の機能を切り替えられる演算器（ALU)を設計してください。
入力はa, bそれぞれ32bitで出力も32bitとしてください。
2bitのsel（セレクタ）信号を受け取り、000の時は足し算、001の時は引き算、010の時は掛け算となるように設計してください。

# 3日目

## 3日目課題
1. 教科書図7.2のレジスタファイルを作成する。
(参考：L22 https://github.com/kentaroy47/CPU-experiment/blob/main/99_cpuexample_verilog/MEMORY.v)
2. 教科書図7.2のデータメモリを作成する。
addrは10bitでデータ数は1024とする。
WEとclkで書き込み機能を加え、各データはレジスタと同様32bitとしてください。
3. 各種演算器を作成し、下記命令セットのR型、L型、W型を実装する。
4. `python 09_complier/compiler.py`を実行して出てくる命令コードをCPUに与え、命令どおりの計算ができることを確認する。

## 単純命令セット
命令セット
* R型 [7:0]opcode, [12:8]rd1, [17:13]rd2, [22:18] rw, [31:23] 空き （計算に使う命令）
* L型 [7:0]opcode==4, [17:8]memory, [22:18] r, [31:23]空き （データメモリからレジスタにデータ書き込みする命令）
* W型 [7:0]opcode==5, [17:8]memory, [22:18] r, [31:23]空き  （レジスタからデータメモリにデータ書き込みする命令）

単純にR型は
* opcode==0: 足し算
* opcode==1: 引き算
* opcode==2: 掛け算
* opcode==3: 割り算
とします。