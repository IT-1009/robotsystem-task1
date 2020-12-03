# 2020年　ロボットシステム学課題1
## 目的
授業で作成したデバイスドライバをベースに改造を行い、そのデバイスを動かす。

コードをGITに上げてしっかりと管理する。

ライセンスや著作権の記述を理解しているかを確認する。

## プログラム内容
‘0’ーLEDが消灯。

‘1’ーLEDが点灯。

‘2’ーLEDが点滅を繰り返す。

‘3’ーモールス信号で「キヨウノゴハンハカレー」となるようにLEDが点滅する。
>LEDが晩御飯の内容を教えてくれますが、どうやら Raspberry Pi君の家ではカレーしか出ないようです。

## 手順
1．LEDのアノードをGIPO25：22番ピンにLEDのカソードをGND：39ピンに接続する。

2．programディレクトリ内でmakeを実行する。

3．sudo insmod myled.koを実行する。

4．tail /var/log/messagesで***major番号***を確認する。

5．sudo mknod　/dev/myled0 c ***major番号*** cを実行する。

6．sudo chmod 666 /dev/myled0を実行する。

7．echo ***上記のプログラム内容のうち実行したいプログラム番号*** > /dev/myled0を実行する。

8．満足したらsudo rmmod myledを実行し、modをアンインストールしておく。
