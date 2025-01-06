---
title: "AIと個人開発するときにまずやることはCursorで要件定義だ！"
emoji: "🎉"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: [個人開発, AI, 要件定義]
published: false
---

# はじめに
こんにちは！yasunaです！
私は普段は会社員をしていてエンジニアではないのですが、趣味でプログラミングをしています！

今回はAIの力をフル活用しながら個人開発アプリの要件定義を作るまでの流れを記録しておきたいと思います。

# 今回作ろうとしているアプリケーションについて

「TikTok台本作成支援システム」というアプリケーションを作ろうとしています。ユースケース図はこんな感じになりました。
![](https://storage.googleapis.com/zenn-user-upload/7d75175d1363-20250106.png)

この図を作るときに役に立ったのがAI搭載エディターのCursorです。
CursorはAIがコードを生成してくれるので、コードを書くのが苦手な私のような人でもAIとチャットしながらコードを書くことができます。

こちらの図もCursorでmdファイルを作成して図に変換しました。
これはPlantUML（プラントユーエムエル）という図表作成用のマークアップ言語です。UML（Unified Modeling Language：統一モデリング言語）の図を簡単なテキスト記述で作成できます。

```md
@startuml
left to right direction
skinparam packageStyle rectangle

actor クリエイター
actor "TikTok API" as API

rectangle "TikTok台本作成支援システム" {
  ' 優先度高（MVP）
  package "基本機能" {
    usecase "TikTokアカウント連携" as UC1 #LightGreen
    usecase "既存動画分析" as UC2 #LightGreen
    usecase "台本生成" as UC3 #LightGreen
    usecase "台本保存/編集" as UC4 #LightGreen
  }

  ' 優先度中
  package "分析機能" {
    usecase "パフォーマンス分析" as UC5 #LightYellow
    usecase "トレンド分析" as UC6 #LightYellow
    usecase "類似動画分析" as UC7 #LightYellow
  }

  ' 優先度低
  package "拡張機能" {
    usecase "台本エクスポート" as UC8 #LightPink
    usecase "チーム共有" as UC9 #LightPink
  }
}

' 関連性
クリエイター --> UC1
クリエイター --> UC3
クリエイター --> UC4

UC1 --> API
UC2 --> API
UC6 --> API

UC1 ..> UC2 : include
UC2 ..> UC3 : extend
UC5 ..> UC3 : extend
UC6 ..> UC3 : extend
UC7 ..> UC3 : extend

note right of UC3 #LightGreen
  優先度高（MVP）
  - アカウントデータに基づく台本生成
  - トレンドを考慮した構成提案
  - テロップ・演出の具体的指示
end note

note right of UC5 #LightYellow
  優先度中
  - 視聴者層分析
  - エンゲージメント分析
  - 最適投稿時間帯分析
end note

@enduml 
```


# 要件定義つくっていくぞ！って思ったらはじめになにをするの？
アプリケーションを作りたいと思ったらまずはどんなアプリケーションを作りたいのか、それはどんな問題を解決するのかを考える必要があります。
わたしは本職がマーケターなのでアプリケーションの提供価値をしっかりと考えました。

```
### 2.2 解決したい課題
- [どんな課題を解決したいか]
    - TikTokの縦動画を作るのに時間がない
- [なぜその課題に着目したか]
    - 縦動画はユーザーの認知を取るために欠かせないもので継続的に出し続ける必要がある
    - しかしエンゲージメントの高い動画を作るにはノウハウに沿った台本づくりが必要
    - バズを狙うための台本を作るのに一人では時間がかかる
    - 現在のバズ動画からノウハウを言語化し学習させ、台本をAIに作ってもらいたい
### 2.2 想定ユーザー
- [どんな人に使ってもらいたいか]
    - すでにTikTokをやっている人もしくはこれからやりたい人
    - 縦動画を作るのに時間がない人
    - バズ動画を簡単に作りたい人
- [その人たちがどんな状況で使うか]
    - TikTokで投稿するために台本を作るとき
### 2.3 提供したい価値
- [このアプリで実現したいこと]
    - クオリティを担保した台本が作れる
- [ユーザーにとってのメリット]
    - 誰でも一定以上バズが狙える縦動画を作成することができるようになる
- [既存の解決方法との違い]
    - 既存の解決方法は本を読んだり情報を得て自分で考える工数がかかっている。ノウハウを言語化してAIに学習させることができない
```

意外と課題について深堀りせずにアプリケーションを作り始めてしまいがちですが、これだけでもアプリケーションの提供価値が整理できるのでおすすめです！

これだけ決まったらあとは「要件定義を作ってください」とプロンプトで指示を出せばば～っとAIが書いてくれます。
そこから画面遷移図を作ってみました。

![](https://storage.googleapis.com/zenn-user-upload/ca88d7b4bb94-20250106.png)

実はこれもAIにmdファイルを書いてもらって画面遷移図に変換しています。
こちらはmermaidという記法でかかれた図表定義です。

```
graph TD
Login[ログイン画面] --> Dashboard[ダッシュボード]
Dashboard --> Analysis[動画分析画面]
Dashboard --> Create[台本作成画面]
Dashboard --> List[台本一覧画面]
Create --> Preview[プレビュー画面]
Create --> Save[保存確認画面]
Analysis --> Create
List --> Edit[台本編集画面]
Edit --> Preview
Edit --> Save
classDef primary fill:#93c5fd,stroke:#1d4ed8,stroke-width:2px;
classDef secondary fill:#e2e8f0,stroke:#64748b,stroke-width:2px;
class Login,Dashboard,Create primary;
class Analysis,List,Preview,Edit,Save secondary;

graph TD
subgraph ダッシュボード
A[ヘッダー<br>- アカウント情報<br>- メニュー] --> B[メイン統計<br>- パフォーマンス<br>- トレンド]
B --> C[クイックアクション<br>- 新規作成<br>- 分析開始]
C --> D[最近の台本<br>- リスト表示<br>- 編集リンク]
end
style A fill:#f3f4f6,stroke:#d1d5db
style B fill:#f3f4f6,stroke:#d1d5db
style C fill:#f3f4f6,stroke:#d1d5db
style D fill:#f3f4f6,stroke:#d1d5db
```

![](https://storage.googleapis.com/zenn-user-upload/ab385015663b-20250106.png)

このコードを左のタブに貼り付けるとなんと画面遷移図に変換してくれます！！！感動的！
Mermaid記法は以下のURLで試せます。
https://mermaid.live/

