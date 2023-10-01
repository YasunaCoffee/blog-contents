---
title: "初心者がVtuberを作るまで"
emoji: "🎤"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: [aws,生成ai,StableDiffusion]
published: false
---

## はじめに
Amazon BedrockのPlayGroundで遊んでいます！
https://aws.amazon.com/jp/bedrock/
前回の記事でStablity AIでテキストからイメージ生成できるので試してみました！
https://zenn.dev/yasuna/articles/cc99387fcd3989

## Vtuberを動かすには設計図が必要

次は、生成した2DのVtuberを動かしてみたいのですが、
調べてみたところ、Vtuberを動かすために設計図を作ら

以下、参考にした記事です！
https://developers.freee.co.jp/entry/2022/12/11/090000

今回はStablity AIでキャラクターの三面図をつくっていきます。
https://ja.stability.ai/

## Dream Studioで作る
前回はAmazon Bedrockではテキストからイメージを作成することができました！
ここではStable DiffutionのDream Studioから三面図を作っていきます。

:::message
**三面図とは**
設計図を理解しやすく、詳細に見せるため方法。物体を正確に描写し、視覚的に分かりやすく伝えること。
:::

前回のVtuberを生成したプロンプトに三面図の記述を追加して実行してみました。

```
# プロンプト
"Design a three-view diagram for a VTuber character who like Hatsune Miku, pink hair with bun head and glasses.
 Create front, side, and back views of the character, paying attention to their appearance, outfit, and key features. Consider the character's personality and backstory while designing, and ensure the three views provide a comprehensive and visually appealing representation of the VTuber for their virtual persona."
```

![](https://storage.googleapis.com/zenn-user-upload/3785ca674eae-20231001.png)

3枚の三面図が出来上がりました！
![](https://storage.googleapis.com/zenn-user-upload/e45fb8b1f9f0-20231001.png)
![](https://storage.googleapis.com/zenn-user-upload/84f8cfba1788-20231001.png)
![](https://storage.googleapis.com/zenn-user-upload/d710ddc2f29d-20231001.png)

**すばらしい出来栄え！！！！**



今後はこのYasunaちゃんとともに技術的なアウトプットをしていこうと思います！
https://twitter.com/yasun_ai
