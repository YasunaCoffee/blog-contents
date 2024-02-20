---
title: "音声生成ソフトで音声ファイルを作ろう"
---
# はじめに
![](https://storage.googleapis.com/zenn-user-upload/dc3065981791-20240219.png)
この章ではテキストから音声を生成することができる「[VOICEVOX](https://voicevox.hiroshiba.jp/
)」というText to Speechソフトウェアを紹介していきます。

多くのAITuberには、このソフトウェアで作られた音声が使われていますので「この声聞いたことある！」とピンと来る方もいるかもしれません。

早速「[VOICEVOX](https://voicevox.hiroshiba.jp/
)」をダウンロードしていきましょう。


基本的に無料で使うことができます。それぞれの音声キャラクターごとに利用規定がありますので使うときには規定を読んで使ってみてください。
https://voicevox.hiroshiba.jp/term/

# VOICEVOXで音声ファイルを作って保存しよう
VOICEVOXの初期設定や使い方は以下の公式ドキュメントをご覧ください。
https://voicevox.hiroshiba.jp/how_to_use/

ここでは、**AITuber用の音声を保存するための作業**を簡単に紹介していきます。

VOICEVOXのダウンロードが完了すると、このような画面が立ち上がります。

あらかじめ作成した台本のテキストをテキストボックスにペーストします。
そして左下の**再生ボタン**を押すと生成された音声を聞くことができます。

右側のサイドバーから細かい調整も可能ですので色々試してみてくださいね。
![](https://storage.googleapis.com/zenn-user-upload/ceac1f2d5cb7-20240218.png)

音声が再生できたら、左上の「ファイル」から「**音声を繋げて書き出し**」を選んで保存することができます。
![](https://storage.googleapis.com/zenn-user-upload/91d377b7e3ce-20240218.png)

これで台本から音声を作って保存することができました！本当に簡単ですね。

## 仮想オーディオデバイスの導入
次に、今作った音声ファイルをもとに３Dキャラクターの口を動かす準備をしていきます。
そのためには**仮想オーディオデバイス**を導入する必要があります。

今回は無料で使えて有名な[VoiceMeeter Banana](https://vb-audio.com/Voicemeeter/banana.htm)を導入していきいましょう。
![](https://storage.googleapis.com/zenn-user-upload/9bbabaaeec99-20240218.png)
以下からダウンロードしておきます。
https://vb-audio.com/Voicemeeter/banana.htm

この時点ではダウンロードするだけで準備OKです。

# おまけ
今回は音声生成ソフトにVOICEVOXを紹介しましたが、私がAITuberで使っている「Rinne」という音声生成AIのリンクを以下にご紹介しておきます。
NVIDIAのビデオカード推奨とのことですので持っている方は試してみてくださいね。
https://huggingface.co/RinneAi/RinneVoiceSet

# まとめ
次回は作った音声ファイルをもとに、３Dキャラクターが口を動かすためのソフトウェアを導入していきます。
