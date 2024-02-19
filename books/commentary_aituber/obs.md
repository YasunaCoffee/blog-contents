---
title: "[WIP]録画用ソフトを導入しよう"
---
# はじめに
![](https://storage.googleapis.com/zenn-user-upload/3f097ccaca63-20240217.png)
この章では3Dキャラクターを動かすためのソフトを導入していきます。
録画用ソフト「[**OBS Studio**](https://obsproject.com/ja/download)」を以下からダウンロードしていきいましょう。
https://obsproject.com/ja/download

OBS Studioは動画配信において非常に有名なソフトウェアで、基本的に無料で使うことができるのでかなりおすすめです。

それでは早速OBSで3Dキャラクターを収録していきましょう。

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

同じように「ソース」のパネルの一番下の「＋」をクリックして、「画像」を選択して背景画像も配置できます。
![](https://storage.googleapis.com/zenn-user-upload/3f097ccaca63-20240217.png)

## OBSで音声の設定しよう
次にOBS側から3Dキャラクターと音声を繋げるための設定をしましょう。
OBSの「コントロール」パネルから「設定」を選びます。
![](https://storage.googleapis.com/zenn-user-upload/3f097ccaca63-20240217.png)

設定画面が表示されたら左から「音声」を選びます。
そして、以下のように「詳細設定」のモニタリングデバイスを「**VoiveMeeter Input**」にします。
![](https://storage.googleapis.com/zenn-user-upload/a5ff349e3a03-20240219.png)
:::message
この本は現在執筆中です。いいねで応援していただけると励みになります。
:::