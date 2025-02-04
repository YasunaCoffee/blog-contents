---
title: "エンタメチャットアプリ「にーいちよん」による課題解決とAIエージェント実装について"
emoji: "🍫"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: [ai, agent, gemini]
published: false
---
## はじめに
本記事は[AI Agent Hackathon with Google Cloud](https://zenn.dev/hackathons/2024-google-cloud-japan-ai-hackathon)への参加のため執筆しています。

こんにちは、個人開発者のyasunaです。
今回は本ハッカソンによせて、個性豊かな３人の女子高生たちとバレンタインデーを楽しむエンタメチャットアプリ「にーいちよん」を開発しました。
![](https://storage.googleapis.com/zenn-user-upload/5087eb0005a4-20250204.png)

もともとは趣味でReactとAIサービスを組み合わせたアプリ開発の練習として作っていたものですが、ちょうどハッカソンが開催されているとのことで、Google CloudのAIサービスと組み合わせてのアプリ開発をしたことがなかったのでとても面白そう！と思い、参加させていただきました。

## 開発期間
このアプリは1月21日から2月2日までの約3週間で開発しました。
1日2~3時間くらいの稼働だったのでこのアプリにかけた時間はそれほど多くはないです。

### 開発ツール
この短期間で開発できた大きな要因はCursor Composer Agentを使用したことです。
AIエージェントハッカソンへの参加プロジェクトをAIエージェントで作るというのも私の中でのもうひとつのチャレンジでした。

### デモ動画


## ユーザー像
それでは、前置きはこのくらいにして、本アプリのユーザー像について解説します。

:::message
ユーザー像：
**学生時代のバレンタインデーを楽しみたい人**
:::

このアプリのユーザーに当てはまる人はずばり**老若男女**です。
誰もがバレンタインというイベントに対してトキメキたいしもっともっとエンジョイしたいはずです。

このアプリの最大の特徴はバレンタインというシーンをあらかじめ設定していることです。
みんなが想像するバレンタインはどんなシーンがあるでしょうか？

「自分は果たしてチョコレートをもらうことができるのだろうか？」
「あの子は誰にチョコレートを渡すんだろうか？」
「あの子は前日にチョコレートは作ったんだろうか？手作りするならどんな形？」

バレンタインと一言で言っても、その中にはさまざまな場面とドラマがあります。
AIを活用したアプリというとどうしても業務効率化など便利な方向のものが多いですが
あえてエンターテインメントとしてユーザーに楽しんでもらえるものを届けたいと考えました。

## 課題
想定するユーザーは常に課題を抱えています。
ここでは「学生時代のバレンタインデーを楽しみたい人」が抱える課題について3点挙げさせていただきます。
:::message
1.立場的制約(学生じゃない・男じゃない)
2.出会い的制約(実際に脈アリの子がいない)
3.共感的制約(知らない女の子に共感できない)
:::

## 課題へのソリューション
### 1.立場的制約へのソリューション
学生時代のバレンタインデーを楽しみたい人はもう学生ではない人も含まれます。
年齢や立場関係なくシチュエーションを楽しむにはエンターテイメントが必要です。

このアプリケーションを通して実年齢や立場を超えた仮想のプロフィールを作ることにより
にーいちよんの世界で学生時代のバレンタインデーを思い切り楽しむことで解決します。
![](https://storage.googleapis.com/zenn-user-upload/e55e3372b6ce-20250204.png)

学生時代のバレンタインデーを楽しみたい人は実は女の子も多かったりします。
女の子はチョコを渡す側、男の子はもらう側みたいな空気がありますよね。女である私も男の子の立場でのドキドキを味わってみたかった。
このアプリケーションを通してユーザーがたとえ女の子だったとしてもバレンタイン当日に本命チョコをもらえるかもしれません。
**エンターテイメントのロールプレイには社会的性別や立場は関係ないということで解決します。**

### 2.出会い的制約へのソリューション
学生時代のバレンタインデーを楽しみたい人は、実際に脈アリの子がいない場合もあります。
実世界での出会いは残念ながらバレンタイン付近に突然脈ありの子が現れることはあまりありません。

そこで、にーいちよんでは３人の全く個性が違ったキャラクターとバレインタイン当日の会話を楽しむことができます。
そして当日だけではなく、その前日にあなたと過ごした学校生活の日記を読むことができます。
![](https://storage.googleapis.com/zenn-user-upload/cb10755e955d-20250204.png)

それにより「いきなり出会う」という訳ではなく、ある程度あなたとの関係性を構築できているということを担保にしながら、バレンタイン当日の会話に臨み自然な"出会い"を演出することで出会い的制約を解決します。

### 3.共感的制約へのソリューション
すでに知っているキャラクターであれば一緒にバレンタインデーを楽しむことができるかもしれませんが、自分についてある程度知ってもらわないとキャラクターへ共感することは難しいです。

そこで具体的なソリューションは3つがあります。
![](https://storage.googleapis.com/zenn-user-upload/6a29a5a67093-20250204.png)

１つ目は、ユーザーの性格分析です。ユーザーは名前とプロフィールを入力することでキャラクターと同じ学校に通う生徒になります。
そして、ユーザープロフィールをもとにAIエージェントが性格分析をして性格に合わせてキャラクターがあなたとの日記を創造してくれます。

２つ目は、キャラクターの感情分析です。
チャットでは、ユーザーが入力した言葉を受けてキャラクターがどう思ったかという気持ちをAIがリアルタイムで判断します。
キャラクターの感情の数値はドキドキメーターとチョコメーターに反映されUIに表示されます。

３つ目は、感情分析結果に基づくチャットの生成です。
性格分析による日記や会話をもとに感情を分析した結果をリアルタイムに返答へと反映します。
![](https://storage.googleapis.com/zenn-user-upload/28c6cdec683f-20250204.png)

キャラクター感情に基づく返答はユーザーに大きく委ねられているため、
学生時代のバレンタインデーのドキドキを感じやすくなったり、共感的制約を解決します。

## システム構成
本アプリのシステム構成を紹介します。
![](https://storage.googleapis.com/zenn-user-upload/7f56ef309fe7-20250204.png)

1. **フロントエンド層**
   ![](https://storage.googleapis.com/zenn-user-upload/9bf01766d9c0-20250204.png)
   **Reactアプリケーション (UI)**
   
   **サービスレイヤー**
   - GameService(ゲームサービス)
     - ゲームフェーズの管理
     - キャラクター選択の制御
     - ハートゲージの更新
     - イベントトリガーの管理

   - ChatService(テキスト生成エージェント)
     - 対話履歴の管理
     - プロンプトの生成
     - 応答の整形
     - 文脈の維持
   
   - DiaryService(日記生成エージェント)
     - ユーザープロフィールによる性格分析
     - キャラクターによる思考生成
     - キャラクターによる日記生成
   
   - EmotionService(感情分析サービス)
     - リアルタイム感情分析
     - 感情値の計算
     - キャラクター別係数の適用
     - 閾値管理

    状態管理コンテキスト
   - GameContext: ゲーム全体の状態
   - ChatContext: 対話の文脈情報
   - EmotionContext: 感情状態の追跡

2. **バックエンド層 (Google Cloud)**
   ![](https://storage.googleapis.com/zenn-user-upload/2d682b4f96b8-20250204.png)
   **Cloud Run**
   - サーバー
     - フロントエンドからのリクエスト処理
     - Vertex AIとの通信制御
   
   **Vertex AI (Gemini-1.0-pro)**
   - 対話生成
   - 感情分析
   - 日記生成

3. **永続化層 (LocalStorage)**
   ![](https://storage.googleapis.com/zenn-user-upload/46c08287374d-20250204.png)

# AIエージェントの実装
このアプリケーションでは、日記生成エージェントと感情認識型対話エージェントの２つを実装しているので、詳しく紹介させてください。

## 日記生成エージェントについて(DiaryService)

日記は段階的な生成プロセスで実行されています。

1. ユーザーの分析(心理カウンセラー)
2. 思考生成(キャラクター)
3. 日記作成(キャラクター)

の３段階で行われます。

まずはユーザープロフィールの分析です。コードを見ていただいたほうが早いので以下に記載します。
```typescript
public async analyzeMaleProfile(userProfile: UserProfile): Promise<string> {
  const prompt = `
    あなたは心理カウンセラーとして、以下の人物の性格分析を行ってください。
    分析結果は、後で女子高生が片思いの気持ちを書くための参考情報として使用されます。

    対象の人物：
    名前：${userProfile.name}さん
    プロフィール：${userProfile.description}

    以下の項目について、具体的に分析してください：
    1. 性格特性
    2. 趣味・興味
    3. 学校生活での様子
    4. 恋愛傾向
    ...
  `;
  return this.sendMessage(prompt, '心理カウンセラー');
}
```

ユーザープロフィールの分析ができたら次に結果をもとにキャラクターが思考生成します。

```typescript
public async generateFemaleThoughts(maleProfile: string, character: BaseCharacter): Promise<string> {
  const prompt = `
    あなたは${character.name}として、片思いの気持ちを独白形式で表現してください。
    ${character.description}という設定を意識して書いてください。

    片思いの相手の特徴：
    ${maleProfile}

    以下の時間帯ごとの心情を、具体的な場面や行動とともに書いてください：
    1. 朝
    2. 昼
    3. 放課後
    ...
  `;
  return this.sendMessage(prompt, character.name);
}
```

最後にバレインタイン前日という設定で日記の文体を整えます。
```typescript
public async generateDiaryContent(thoughts: string, character: BaseCharacter): Promise<string> {
  const prompt = `
    あなたは${character.name}として、2025年2月13日の日記を書いてください。
    ${character.description}という設定を意識して書いてください。

    今日の出来事と気持ち：
    ${thoughts}

    以下の要素を含めて日記を書いてください：
    1. 日記の基本要素
    2. 文体とトーン
    3. 内容の構成
    4. 表現上の注意点
    ...
  `;
  return this.sendMessage(prompt, character.name);
}
```

このように段階的に思考をしてつなげることであなたとキャラクターが生きる学校生活の日記を作成することができます。

## 感情認識型対話エージェント(ChatServiceとEmotionService)
次にキャラクターとチャットを行う部分のAIエージェントのフローについて紹介します。

本アプリではチャット機能と感情分析機能を組み合わせることにより、
ユーザーとキャラクター両方の感情を認識した対話を実現しています。

これにより、ユーザーの感情を揺さぶり共感性の高い会話ができます。
ユーザー入力から応答までのフローは以下の通りです。

![](https://storage.googleapis.com/zenn-user-upload/ca6f9ca99d04-20250204.png)

このエージェントのフローにおけるポイントは３つです。

1.感情分析の二重処理
ユーザーの入力メッセージと、キャラクターの応答の両方に対して感情分析を行っています。

2.状態の管理の重視
感情スコアと状態を継続的に更新しています。

3.プロセスの知的制御
感情分析結果に基づいてプロンプトを動的に生成しています。

## 謝辞
ハッカソンに参加させていただく際にGoogle Cloudのクレジットをいただくことができ今回初めてCloud Run, Cloud Build, Vertex AI Studioを使った
実装をすることができました！機会をいただき本当にありがとうございます！

このアプリケーション開発においては以下の2冊を参考にさせていただきました
[AITuberを作ってみたらプロンプトエンジニアリングがよくわかった件](https://bookplus.nikkei.com/atcl/catalog/24/11/07/01683/)
[LangChainとLangGraphによるRAG・AIエージェント［実践］入門](https://gihyo.jp/book/2024/978-4-297-14530-9)

なお個人的にこのアプリケーションのデモを2月14日に公開する予定ですので
ぜひXをフォローしていただけると嬉しいです。

ここまで読んでいただきありがとうございました！ハッピーバレンタイン！

https://x.com/yasun_ai/status/1885981953620602884

