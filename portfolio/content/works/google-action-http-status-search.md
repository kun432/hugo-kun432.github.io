+++
author = "Kunikai Shimizu"
date = "2018-10-02"
title = "Googleアクション「HTTPステータス検索」"
linktitle = ""
description = ""
tags = []
categories = []
highlight = true
draft = false

+++

### **はじめに**

Actions on Googleアプリ「HTTPステータス検索」のページです。

<img src="/img/google-action-http-status-logo.png" width=600>

### **目次**

<!-- TOC -->

- [**はじめに**](#はじめに)
- [**目次**](#目次)
- [**使い方**](#使い方)
- [**実装について**](#実装について)
- [**更新履歴**](#更新履歴)
- [**プライバシーポリシー**](#プライバシーポリシー)

<!-- /TOC -->

### **使い方**

{{< youtube HFQdbAHYXCI >}}
<br />
「OK, Google、HTTPステータス検索につないで」で起動し、その後、「ステータスコード200を教えて」というと、ステータスコードの意味を教えてくれます。
<br />
<br />
アクションの利用開始に、有効化等の作業は不要です。ぜひご利用ください。

### **実装について**

<img src="/img/design-google-action-http-status-code.png" width=740 style="border: solid 1px #000000" />

Alexa、Clovaに続いて、Google Home向けのアクションとして対応しました。基本的なロジックやVUI設計の考え方はそれほど変わりませんので、短期間で実装できましたが、以下のようなGoogle Home向けに特化した修正も行っています。

- インテントで受け取ったパラメータはWebhookでFirebase Functionsに渡していますが、Firebase Functions側で障害が発生した場合、Dialogflow側でテキストレスポンスを設定することで、利用者への障害通知を明確に伝えるようにしています。
- SimpleResponseを使って、音声出力と画面出力を分けています。
- また、画面出力が可能なデバイス向けに、サジェスチョンチップを表示し、会話のフォローを行えるようにしています。

また、これまでのAlexa, Clovaスキル開発時の経験を生かして以下のような改善も行っています・

- 発話サンプル（Dialogflowでは、"Training phrases"）をエンティティに分解し、発話サンプルの登録数を減らしました。例えば、「ステータスコードXXXを調べて」「ステータスコードXXXを教えて」みたいな微妙な違いに関して、同士部分をエンティティ化することで、対応がやりやすくなります。
- 可能な限り、Dialogflow側だけで処理が完結できるようにして、どうしてもできない場合（受け取ったパラメータを処理する必要がある）にだけWebhookに渡すようにしました。これによりFirebase Functions側のコードは大幅にスッキリしました。

これで３大スマートスピーカー向けアプリ開発を一通り経験できましたので、今後はそれぞれのスピーカーおよびクラウドの特性を活かした機能の活用を進めていきたいと考えています。
<br />
<br />
コードはGithubで公開予定です。
<br />
https://github.com/kun432/google-action-http-status-code
### **更新履歴**

- v1.0(2018/10/4)
  - 公開

### **プライバシーポリシー**

このアプリケーションでは、ご利用になる皆様のいかなるプライバシー情報も収集、使用、共用することはありません。

<div style="text-align: right;">
2018月10月2日 制定<br />
Kuniaki Shimizu<br />
kun432.8d1w@gmail.com<br />
</div>