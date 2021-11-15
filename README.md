# CPU-experiment

```html
<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->



<!-- END doctoc generated TOC please keep comment here to allow auto update -->
```



# 前準備

Slack開設

Githubアカウント作成

# 目的

## 最終目標：

- シングルサイクルCPUで足し算を行うこと

命令セットはMIPSでもRISC-Vでもどちらでも良い。まずは教科書にあるMIPS命令セットでCPUを作り、その後RISC-Vに換装するのが良いと思う。

### 付属して付く技術

VerilogHDLの扱い、シミュレーション

論理回路の理解

（最低限の）CPU、コンピュータ・アーキテクチャに関する理解や技術

# はじめまして

吉岡の自己紹介

みんなの自己紹介

ペアを作成

# このセミナー開始にあたって

この授業の目的は**研究体験**であると解釈しています。まず研究と授業は全然違います。授業は基本的に受け身でよく、最悪授業に出席し言われた通りの範囲を勉強しレポートやテストに望めばOKです。

一方で研究は最先端の更にその先を目指す行為です。そのため教員もまだ知らないことも勉強する必要があり、研究遂行に必要な知識やスキルを教員が全て丁寧に教えることはありません（というか無理です）。もちろんベースとなる技術や論文、教科書を最初に提示しますし、輪講などで基本は教えます（それは教員の義務です）が卒論・修論を書くには**自分で情報を調べること**がかなり重要となります。

これは会社に入っても同様であり、今はどの会社でも新人研修よりもOJTで仕事スキルを付けることが多いかと思います。OJTというと聞こえは良いのですが、メンターは自分の仕事をしながらあなたの指導をするので大学の授業のように懇切丁寧に教えてくれるわけではなく、要点を絞って自分で調べてもわからない範囲で質問をする必要があります。なので研究における姿勢と仕事の姿勢はちょっと似ていますね。

### 10分質問ルール

じゃあ質問するなってこと。。？というのは少し違います。

わかりやすく今回のセミナーで適応したいルールにGoogle Brainの15 minute ruleがあります。

[Google人工知能チームの「15分ルール」 - BppLOG](https://tkybpp.hatenablog.com/entry/2016/08/16/173055)

問題が起きた時は

【1】最初の15分は自分自身で解決を試みる【2】15分後も解決していなかったら必ず人に聞く

15分以内で自分で考えず、調べずに質問するのは他者の時間の無駄である。

15分以上自分で考えるのは自分の時間を無駄にしているので**必ず質問をする**、というのが15分ルールです。

今回のセミナーではわからないことだらけなので10分調べたりしてもわからなかったらSlackや吉岡がそこにいたら聞く、というルールで運用しましょう。**（これは実際の設計時の話で環境設定では遠慮なく聞いてください）**

できるだけSlackの公開チャネル（Question）で聞くと他の人にも共有できるため、推奨しています。

# 1日目

### 環境設定

Slack、githubを整備

シミュレータ整備

動作テスト

教科書配布

### テキスト

本セミナーでは”ディジタル回路設計とコンピュータアーキテクチャ[ARM版]”をベースに勉強します。

3章までは必修のディジタル・アナログ回路の復習となると思います。4章以降は新たに学ぶ内容です。

まず今日は4章の終わりまで読むことを目標としましょう。

そして4章に書いてある例題をいくつかVerilogで記述し動作を確認してみましょう。



## 吉岡TODO

Githubページ

参考ページ Qiitaまとめる

# 2日目