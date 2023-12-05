---
title: "AITuberのためのOBS環境構築(WSL2編)"
emoji: "⛵"
type: "tech" # Wech: 技術記事 / idea: アイデア
topics: [obs,chatgpt,wsl2,初心者]
published: true
---
# はじめに
最近発売された「AITuberを作ってみたら生成AIプログラミングがよくわかった件」という本を買いました！
https://bookplus.nikkei.com/atcl/catalog/23/10/31/01079/
今回はAIキャラクターのYoutube配信の準備としてプログラムとOBS Studioというアプリケーションをつないでいく章をやってみました。
私は**WSL2からOBSのWebsocketサーバーへつなぐ方法**をやってみたかったので自分で調べてみました。WSL2という環境の特徴をつかめずにWindows上のWebsocketサーバーとの接続につまづき、GPT-4に聞いてなんとか解決できました。

**今回の開発環境**
:::message
WSL2
Ubuntu 22.04.3
Python 3.11.5
:::
WSL2にPythonをインストールする方法はこちら
https://zenn.dev/yasuna/articles/b3eae0ed00e665
WSL2にvenvで仮想環境を整える方法はこちら
https://zenn.dev/yasuna/articles/a02113a90e2b39

# WSL2からWindows上のOBSへ接続したい
今回はYoutube配信準備として**WSL2でPythonを実行してOBSのWebsoketサーバーに接続できるか**どうか試してみます。
ちなみにOBS Studio(OBS)は配信ができるソフトウェアです。
https://obsproject.com/ja/download

AITuber本に書かれていた手順はWindowsのPowerShellなどのシェルから実行される前提で書かれていますが、WSL2から実行してみました。
以下のようなエラーが出てきました。

```
# WSL2からPythonを実行しOBSに接続するコードを実行
$ python3 obs_adapter.py
ConnectionRefusedError: [Errno 111] Connection refused
Traceback (most recent call last):
  File "/home/yasuna/projects/aituber/.venv/lib/python3.11/site-packages/obsws_python/baseclient.py", line 41, in __init__
    self.ws.connect(f"ws://{self.host}:{self.port}", timeout=self.timeout)
#以下省略
```
`ConnectionRefusedError: [Errno 111] Connection refused`
というエラーが出ていますね。
ではせっかくなのでCursorに聞いて解決してもらいましょう！
前回書いたCusor記事はこちら
https://zenn.dev/yasuna/articles/15ab406c334997

# Cursorでエラーを解決してみよう
このエラーをAI搭載エディターCursorのGPT-4のチャットに投げてみました。
Pythonの実行ファイルはエディタで開いてあります。
```
#プロンプト
このファイルを実行したらエラーがでてきました。解決してください。
(エラー文をペーストする)
```
```
# Curor Chatの回答
エラーメッセージから見ると、ConnectionRefusedError: [Errno 111] Connection refusedというエラーが発生しています。これは、OBS (Open Broadcaster Software) の WebSocket サーバーへの接続が拒否されたことを示しています。

この問題は主に以下の理由で発生する可能性があります：

1. OBS が起動していない、または WebSocket プラグインがインストールされていない。
2. 環境変数 OBS_WS_HOST、OBS_WS_PORT、OBS_WS_PASSWORD が正しく設定されていない。
3. ネットワークの問題で OBS に接続できない。

解決策：

1. OBS を起動し、WebSocket プラグインがインストールされていることを確認してください。
2. 環境変数が正しく設定されていることを確認してください。特に OBS_WS_HOST と OBS_WS_PORT が OBS の WebSocket サーバーの正しいホスト名とポート番号を指しているか確認してください。
3. ネットワーク接続を確認し、必要であれば修正してください。

これらの手順を試してみて、それでも問題が解決しない場合は、さらに詳しい情報が必要になるかもしれません。
```
1,2は正しいことが確認できたので3のネットワークの接続を試してみようと考えました。
```
# プロンプト
 ネットワーク接続を確認する方法を教えてください
```
```
# Curor Chatの回答
 ネットワーク接続を確認する一般的な方法は以下の通りです：

1. Pingコマンドを使用する：Pingコマンドは、ネットワーク接続の問題を診断するための基本的なツールです。ターミナルを開き、pingコマンドを使用してOBSが実行されているホストに接続できるかどうかを確認します。例えば、OBS_WS_HOSTがlocalhostであれば、以下のコマンドを実行します：

ping localhost

応答があれば、ネットワーク接続は正常です。応答がなければ、ネットワークに問題がある可能性があります。

2. Telnetコマンドを使用する：Telnetは、特定のポートでリモートホストに接続できるかどうかを確認するのに役立ちます。例えば、OBS_WS_HOSTがlocalhostで、OBS_WS_PORTが4444であれば、以下のコマンドを実行します：

telnet localhost 4444

接続が成功すれば、ネットワーク接続は正常です。接続が拒否された場合、そのポートが開いていないか、ネットワークに問題がある可能性があります。

これらのコマンドを使用してネットワーク接続を確認してみてください。それでも問題が解決しない場合は、さらに詳しい情報が必要になるかもしれません。
```
1.から試してみました。pingは返答が返ってきたのでネットワークは正常に接続できています。
```
(.venv) yasuna:~/projects/aituber $ ping localhost
PING localhost (127.0.0.1) 56(84) bytes of data.
```
2.のポートを指定してリモートホストに接続してみたら、できていなさそう。
Pythonを実行したときと同じConnection refusedでした。ここが**エビデンス(エラー原因を裏付ける事実)**ですね。
```
(.venv) yasuna:~/projects/aituber $ telnet localhost 4444
Trying 127.0.0.1...
telnet: Unable to connect to remote host: Connection refused
```

# エビデンスをもとに仮説を立てる
エラー原因を裏付ける事実のエビデンスを発見することができたので、これをもとに仮説を立ててみます。
:::message
**エビデンス：**
ポートを指定してリモートホストに接続できない

**仮説：**
1. ポートが開いていないかも → 開いていることを確認した
2. WSL2はWindowsの仮想環境上のUbuntuで動いているのでWindows上で動いているOBSにlocalhostで接続できない？→ ChatGPTに聞いてみよう
:::
# 原因から深ぼり質問をChatGPTへ投げる
エラーの原因がポートに接続できていないことだったので、さらに深掘って質問してみました。CursorだとGPT-4の使用が月500回上限があるので、この深掘り質問はChatGPTで行いました。
```
# プロンプト
WSL2からWindowsOSのOBSアプリケーションで起動したwebsoketのポートにアクセスするにはどうしたらいいですか？
```
```
# Chat-GPTの回答
WSL2 から Windows のアプリケーションにアクセスするには、Windows の IP アドレスを指定して接続を行います。

1）Windows の IP アドレスを調べるには、以下のコマンドを WSL2 端末で実行します。

cat /etc/resolv.conf
この結果、以下のような表示が出ます：

nameserver 172.19.240.1
この nameserver の後ろに書かれている IP アドレス（この例では 172.19.240.1）が、Windows の IP アドレスです。

2）使用しているウェブソケットのクライアントの設定で、接続先としてこの IP アドレスとポート番号を指定します。

例えば、Node.js の websocket ライブラリを使用する場合、以下のようなコードになります：

const WebSocket = require('ws');
const ws = new WebSocket('ws://172.19.240.1:ポート番号');
上記の方法により、WSL2からWindowsOSのOBSアプリケーションで起動したウェブソケットのポートにアクセスすることが可能です。
```
素晴らしい解決策が返ってきました。結果、これで解決できました。

# 解決策
ChatGPTの回答の通り、**localhostの部分をWindowsのIPアドレスに変更したら解決しました。**
ここまでたどりつくのに２時間くらいかかってしまいましたが、なんとか自分とGPT-4の力で解決することができました。
WSL2からWindowsOS上で動いているアプリケーションのWebsocketに接続するときには注意が必要ですね。

# まとめ
エラーが起きたときは成長のチャンス！と解決したあとはポジティブにとらえられるのですが、やはりエラーを解いている時間はハラハラしてしまいますね。

そこで、GPTの頭脳が入ったCursorとChatGPTをうまく使って今回はなんとか解決の糸口をつかむことができました。

またエラーと出会ったらこんな形でAIに助けてもらいながら進んでいきたいです！
ここまで読んでいただきありがとうございました。

