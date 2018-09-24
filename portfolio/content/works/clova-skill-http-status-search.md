+++
author = "Kunikai Shimizu"
date = "2018-09-24"
title = "Clovaスキル「HTTPステータス検索」"
linktitle = ""
description = ""
tags = []
categories = []
highlight = true
draft = false

+++

### **はじめに**

Clovaアプリ「HTTPステータス検索」のページです。```(※2018/9/24現在、申請中です)```

<img src="/img/icon-clova-skill-http-status-code.jpg" width=250 />

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

{{< youtube 34GxyOC8Td4 >}}
<br />
「ねぇClova、HTTPステータス検索を開いて」で起動し、その後、「ステータスコード200を教えて」というと、ステータスコードの意味を教えてくれます。
<br />
<br />
スキルを利用するには、 Clovaアプリから有効にしてください。

### **実装について**

<img src="/img/design-clova-skill-http-status-code.png" width=740 style="border: solid 1px #000000" />

CEKのExtension Serverは、公式のハンズオン等ではHerokuが使用されていますが、

- HerokuのDynoは一定期間アクセスがなければ停止する。再アクセスすれば起動するが、起き上がるのに時間がかかる。
- 一般的には外から定期的に叩くことで回避するようだが、アクセスがそれほどないのにずっと起動している必要性もなければ、そのためにわざわざ別の機構を用意するのはナンセンス。
- 必要なときだけ、瞬時に上がるLambdaがベター。 ただし、CEKから直接Lambdaは叩けないので、API Gatewayを経由。

ということで、AWS API GatewayとAWS Lambdaを使用しています。 また、LambdaのエイリアスとAPI Gatewayのステージを使ったバージョン管理にも対応しています。Code Pipelineを使うともっと楽に管理できるようなので、次回への課題とします。
<br />
<br />
コードは、CEK SDK for Node.jsを使用しています。AlexaとClovaで日本語の認識に差があったり、スロットのエラー処理がやや異なる、などの差異があったもの、比較的ライトに対応でき、Alexaスキル「HTTPステータスコード」から流用できた部分が多かったこと、ClovaにおけるLambda実装例も揃ってきたこともあり、全体的には短期間で実装できました。
<br />
<br />
コードはGithubで公開予定です。
<br />
https://github.com/kun432/clova-skill-http-status-code

### **更新履歴**

- v1.0(2018/9/24)
  - ※申請中

### **プライバシーポリシー**

このアプリケーションでは、ご利用になる皆様のいかなるプライバシー情報も収集、使用、共用することはありません。

<div style="text-align: right;">
2018月9月24日 制定<br />
Kuniaki Shimizu<br />
kun432.8d1w@gmail.com<br />
</div>