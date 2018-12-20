+++
author = "Kunikai Shimizu"
date = "2018-12-20"
title = "Alexaスキル「関ヶ原こよみ」「本能寺こよみ」"
linktitle = ""
description = ""
tags = []
categories = []
highlight = true
draft = false

+++

### **はじめに**

Alexaスキル「関ヶ原こよみ」「本能寺こよみ」のページです。

<img src="/img/alexa-skill-sekigahara-koyomi.png" width=250 /><img src="/img/alexa-skill-honnouji-koyomi.png" width=250 />

### **目次**

<!-- TOC -->

- [**はじめに**](#はじめに)
- [**目次**](#目次)
- [**使い方**](#使い方)
- [**実装について**](#実装について)
- [**今後の予定**](#今後の予定)
- [**更新履歴**](#更新履歴)
- [**プライバシーポリシー**](#プライバシーポリシー)

<!-- /TOC -->

### **使い方**

「アレクサ、〇〇こよみを開いて」で起動して、その後、「知りたい」と答えると、それぞれの出来事が起こった当日までの日数を数えてくれます。
<br />
<br />
<!-- スキルを利用するには、 Amazonの[スキルページ](https://www.amazon.co.jp/kun432-関ヶ原こよみ/dp/B07KW3C182) か [Alexaダッシュボード]( https://alexa.amazon.co.jp/spa/index.html#skills/dp/B07H96LR81/?ref=skill_dsk_skb_sr_0&qid=1537203503) から有効にして下さい。 -->

### **実装について**

<img src="/img/design-alexa-skill-http-status-code.png" width=740 border=1 />

Alexaスキル開発キャンペーンに応募するために「忠臣蔵こよみ」を横展開しただけです。テーマを変えるだけでほぼ実装はいじっていません（多少当日の時間推移はいじっていますが）ので、これもまた、それぞれの歴史の書籍読んだり調べたりというのが工数の殆どを締めていたりします（笑）
あと「忠臣蔵こよみ」でもそうなのですが、効果音いろいろと使っています。Amazonからも公式にAlexaサウンドライブラリが用意されており、SSMLで指定するだけで簡単に使えて、かつ、華やかになりますね。効果音はおすすめです。
<br />
<br />
コードは、Alexa Skills Kit SDK for Node.jsのバージョン2で書いてます。バックエンドも定番の構成です。コードはGithubで公開予定です。
<br />
https://github.com/kun432/alexa-skill-sekigahara-koyomi<br />
https://github.com/kun432/alexa-skill-honnouji-koyomi

### **今後の予定**

- Clova/Google Home対応

### **更新履歴**

- 関ヶ原こよみ v1.0 (2018/11/26)
  - 公開
- 本能寺こよみ v1.0 (2018/11/26)
  - 公開

### **プライバシーポリシー**

このアプリケーションでは、ご利用になる皆様のいかなるプライバシー情報も収集、使用、共用することはありません。

<div style="text-align: right;">
2018年11月26日 制定<br />
Kuniaki Shimizu<br />
kun432.8d1w@gmail.com<br />
</div>