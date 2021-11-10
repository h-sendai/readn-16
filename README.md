# readn-16

16ビット整数をインクリメントして送ってくるサーバー（ボード）のテストプログラム。

readn()を使って16ビット（2バイト）の整数倍バイト数を必ず読むようにしてある。
これによりデータの検証部分を単純化してかけるようになる（4バイトの整数倍
読めない場合は前回のread()とあわせてデコードする必要がでてくるので
けっこうめんどくさくなる）。

## 起動

     ./readn-16 [-b bufsize] [-d] remote_host:remote_port

-bでバッファサイズを指定可能。このプログラムの場合は4の整数倍を
指定する必要がある。シェルの機能で$(())を使うと計算できるので

    ./read-16 -b $((128*1024)) remote_host:24

とするのが楽。

-dはデバッグ用。
