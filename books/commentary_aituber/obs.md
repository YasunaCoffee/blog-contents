---
title: "3Dキャラクターを録画しよう"
---
# はじめに
![](https://storage.googleapis.com/zenn-user-upload/3f097ccaca63-20240217.png)
この章では動画を収録するためのソフトウェアを導入していきます。
無料で使えて有名な動画配信用ソフトウェア「[**OBS Studio**](https://obsproject.com/ja/download)」を以下からダウンロードしていきいましょう。
https://obsproject.com/ja/download

# OBSで3Dキャラクターを録画しよう
それではOBSで3Dキャラクターが動く様子を録画するための準備をしていきましょう。
OBSのダウンロードが完了したところからスタートします。


## OBSで3Dキャラクターを表示しよう
![](https://storage.googleapis.com/zenn-user-upload/e475fc66b586-20240218.png)
OBSをダウンロードして立ち上げるとこのような画面になります。

OBSを立ち上げたら、3Dキャラクターを動かすためのソフトウェアの「[**VMagicMirror**](https://booth.pm/ja/items/1272298)」も立ち上げて３Dキャラクターを表示しておきましょう。
![](https://storage.googleapis.com/zenn-user-upload/815e0a0e6a55-20240217.png)

それでは再びOBSに戻ります。

次に、OBS画面の「ソース」のパネルの一番下の「＋」をクリックします。
![](https://storage.googleapis.com/zenn-user-upload/f3501c0c19ed-20240217.png)
そして、「ゲームキャプチャ」を選択します。
以下のように選択します。
:::message
- モード：特定のウィンドウをキャプチャ
- ウィンドウ：[VMagivMirror.exe]VmagicMirror
- 透過を許可にチェック
:::
![](https://storage.googleapis.com/zenn-user-upload/a9e4320b7cd0-20240217.png)

また、必須ではありませんが背景を入れたいときには、
同じように「ソース」のパネルの一番下の「＋」をクリックして、「画像」を選択して背景画像も配置できます。
![](https://storage.googleapis.com/zenn-user-upload/3f097ccaca63-20240217.png)
OBSに3Dキャラクターと背景画像が表示されたら準備OKです。

## OBSで音声の設定しよう
次にOBS側から3Dキャラクターと音声を繋げるための設定をしましょう。
OBSの「コントロール」パネルから「設定」を選びます。
![](https://storage.googleapis.com/zenn-user-upload/3f097ccaca63-20240217.png)

設定画面が表示されたら左から「音声」を選びます。
そして、以下のように「詳細設定」のモニタリングデバイスを「**VoiceMeeter Input**」にします。
![](https://storage.googleapis.com/zenn-user-upload/a5ff349e3a03-20240219.png)
設定が選択できたら「適用」→「OK」を押して設定ウィンドウを閉じます。


再びOBSの画面に戻ります。

以下の動画のように、停止の■の左横にある、**ぐるっと矢印になっている再生ボタン**を押します。
音声を再生して3Dキャラクターが以下のように動いたら設定は完了です。
![AITUBER2 (1)](https://github.com/YasunaCoffee/blog-contents/assets/74343879/1cef72b3-5df0-4aed-b5ad-036e74f7bf4c)

## キャラクターが話す様子を録画してみよう
音声を再生してキャラクターが動くのが確認できたら、その様子を録画しておきましょう。
「コントロール」パネルにある「**録画開始**」を押すと
以下のように「**録画終了**」にボタンが切り替わり、録画が始まります。
![](https://storage.googleapis.com/zenn-user-upload/2125bd88d0c4-20240219.png)
録画のポイントとしては、「録画開始」を押してから
OBS内でメディアソースにある音声を再生すると動く様子が収録できます。

「録画終了」押すと、録画が終了して動画ファイルがPCへと保存されます。

# まとめ
以上で3Dキャラクターが話す様子を録画することができました。これでAITuberのための動画作りは完了です！
次はYoutubeに公開するのを想定して、直感的で使いやすい動画編集ソフトウェアを紹介します。

:::message
この本は現在執筆中です。いいねで応援していただけると励みになります。
:::