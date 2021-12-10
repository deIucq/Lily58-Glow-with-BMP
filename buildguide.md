# Lily58-X ビルドガイド

## パーツ

| パーツ名                   | 個数 | 備考                                                         |
| -------------------------- | ---- | ------------------------------------------------------------ |
| Lily58-X キット            | 1    | PCB・ケース・ピンソケット・リセットスイッチ・                |
| Pro Micro or BLE Micro Pro | 2    | BLE Micro Proは複雑なので初めての方はPro Microを推奨します。<br>また，コネクタが破損したときなどにボードを交換できるようにコンスルーの使用を推奨します。 |
| キースイッチ               | 58   | ChocでもMXでも可。ただし，MXの場合はミッドプレートとトッププレートの間に隙間が空き，完全に縁が埋まりません。 |
| キーキャップ               | 58   |                                                              |
| TRRSケーブル               | 1    |                                                              |
| Micro USBケーブル          | 1    |                                                              |
| [Option] トラックパッド    | 0~1  | 秋月のRKJXY1000006 DIP化キットを使ってください。<br>https://akizukidenshi.com/catalog/g/gK-15425/ |
| [Option] OLED              | 0~2  | BLE Micro Proとはバッテリーのスペースの問題で共存できません。 |

## 工具

- ドライバー
- はんだ付けに使う道具類
  - はんだごて
  - はんだ
  - ピンセット(推奨)
  - ハンダ吸い取り線またはハンダ吸い取り器(失敗したときの修正に必要)
  - マスキングテープ(あると良い)
  - フラックス(あると良い。はんだ付けする前に金属部分に塗ります。)

## 手順

0. [基板の左右を決める](#基板の左右を決める)
1. [ダイオード・RGBLED取り付け](#ダイオード・RGBLED取り付け)
2. [インジケータ用ダイオード・LED取り付け](#インジケータ用ダイオード・LED取り付け)
3. [TRRSジャック・リセットスイッチ・ピンソケット取り付け](#TRRSジャック・リセットスイッチ・ピンソケット取り付け)
4. [ジャンパ](#ジャンパ)
5. [Pro Micro / BLE Micro Pro取り付け](#Pro Micro / BLE Micro Pro取り付け)
6. [トッププレートとキースイッチ取り付け](#トッププレートとキースイッチ取り付け)
7. [基板洗浄](#基板洗浄])
8. [トラックパッド取り付け](#トラックパッド取り付け)
9. [スペーサー取り付け](#スペーサー取り付け)
10. [OLED取り付け](#OLED取り付け)
11. [ミッドプレート・ボトムプレート・ゴム足取り付け](#ミッドプレート・ボトムプレート・ゴム足取り付け)
10. [ファームウェア書き込み](#ファームウェア書き込み)

## 基板の左右を決める

Lily58-Xの基板はリバーシブルになっています。つまり，右側の基板を二枚作ってしまったというようなミスが起こる可能性があるので，まずはどちらの基板を左/右にするか決めて，表面がどちらなのかそれぞれ覚えておきましょう。(不安な場合は，マスキングテープなどで印を付けておくことをおすすめします。)

## ダイオード・RGBLED取り付け

ダイオードとLEDは基板の**裏面**に取り付けます。

ダイオードは線が引いてあるほうがカソードです。基板上の矢印のようなダイオードの記号の向きに合わせてはんだ付けします。
表面実装の部品は先にパッドを1つだけ予備ハンダして，それを使って固定してから他のパッドをはんだ付けするとやりやすいです。

LEDはLED側は端が欠けている様な形をしているピン，基板側は黒い線で囲われているパッドがGNDになっています。それぞれ合わせてはんだ付けします。
LEDの裏表は表面の方が光るようにします。(GNDをあわせていれば間違えようがないですが)間違えないようにしましょう。

## インジケータ用ダイオード・LED取り付け

基本的にBLE Pro Micro向けなのでPro Microのみを用いる場合は飛ばしても良いです。

表面実装のダイオードとLEDを取り付けます。
極性は基板上で黒い線が引かれている側がカソードで，ダイオードは線が引かれている方，LEDは裏面を見て矢印が向いている方がカソードです。それぞれ合わせてはんだ付けします。

## TRRSジャック・リセットスイッチ・ピンソケット取り付け

TRRSジャック，リセットスイッチ，ピンヘッダは表側から挿してマスキングテープなどで仮固定し，裏面からはんだ付けします。

## ジャンパ

**表側**のパッドをジャンパさせてください。

## Pro Micro / BLE Micro Pro取り付け

取り付け位置はそれぞれ表面から見て黒い枠で囲まれている部分に表面から取り付けます。

Pro Micro，BLE Micro Pro共に，**マイコンなどの部品が載っている側が下になるように**取り付けます。
Arduino Nanoなどとは違う方向なので注意してください。

### コンスルーを使う場合

Helixの[ビルドガイド](https://github.com/MakotoKurauchi/helix/blob/master/Doc/buildguide_jp.md#pro-micro)を参考にしてはんだ付けを行います。

Pro Microの場合はPro Micro側のみはんだ付けを行い、PCB側ははんだ付けしません。
BLE Micro Proの場合はどちらもはんだ付けの必要はありません。

はんだ付けが終わった後は浮きが無いようにしっかりと差し込みます。

### 通常のピンヘッダを使う場合

先にピンヘッダを差し込み，その上にPro Microを載せてはんだ付けします。
その後，マスキングテープなどで仮固定し，裏面からピンヘッダをはんだ付けします。

## トッププレートとキースイッチ取り付け

トッププレートはジョイスティックが使えるものと使えないものがあります。**どちらにジョイスティックを取り付けるか確認**した後，

トッププレートの4つ角にキースイッチを取り付けて

- キースイッチがPCBから浮いていないこと
- ピンが曲がっていないこと
をよく確認してはんだ付けします。

その後，トッププレートに残りのスイッチを取り付けてピンがしっかり通っていることを確認してはんだ付けします。
スイッチのピンの足が曲がってしまった際は，手でもとに戻してください。

## 基板洗浄

ここではんだ付けは終了です。お疲れさまでした。
はんだ付けをした後，基板にフラックスによる茶色っぽい色の汚れが付着していると思います。放置しても基本的には問題ないと思いますが，見栄えがよろしくないので可能であればエタノールやIPAといったアルコール系の溶剤と綿棒などを使ってフラックスの洗浄をしましょう。

## トラックパッド取り付け

トラックパッドを取り付ける場合はこの段階で取り付けます。
トラックパッドと基板のネジ穴を合わせてネジで固定します。

## スペーサー取り付け

保護パネル用のスペーサーを取り付けます

## OLED取り付け

OLEDを取り付ける場合はこの段階で取り付けます。

## ミッドプレート・ボトムプレート・ゴム足取り付け

ミッドプレートとボトムプレートの位置を合わせてネジ止めして裏面にゴム足を取り付けます。

## ファームウェア書き込み

### Pro Microの場合

- VIAを使う

  1. Githubにあるhexファイルとjsonファイルをダウンロード
  2. Pro Micro Web UpdaterもしくはQMK ToolBoxを使ってhexファイルを書き込む
     参考：
     [（初心者編）自作キーボードにファームウェアを書き込む](https://salicylic-acid3.hatenablog.com/entry/qmk-toolbox)
  3. [VIA](https://github.com/the-via/releases/releases/tag/v1.3.1)もしくは[Remap](https://remap-keys.app/)を使ってキーマップを変更
     参考：[（初心者編）VIAを使ってキーマップを書き換えよう](https://salicylic-acid3.hatenablog.com/entry/via-manual)，[（初心者編）Remapを使ってキーマップを書き換えよう](https://salicylic-acid3.hatenablog.com/entry/remap-manual)

- 自分でファームウェアをビルドする(上級者向け)

  QMKの環境構築やビルド方法などは省略します。

### BLE Pro Microの場合

- デフォルトのuf2を使う
  0. Bootloaderをアップデートする
     参考：
  1. Githubにあるuf2ファイルとconfigファイルをダウンロード
  2. リセットボタン長押しでdfuを呼び出してuf2ファイルをインストール
  3. configファイルをインストール
- 自分でファームウェアをビルドする(かなり上級者向け)
  Github



完成です。お疲れ様でした。



## 開発者向け情報

- ピンアサイン

  | PIN  | AVR(Pro Micro) | nrf52(BLE Micro Pro) | 内容(Pro Micro/BLE Micro Pro)   |
  | ---- | -------------- | -------------------- | ------------------------------- |
  | 1    | D3             | P0.8                 | LED (SK6812MINI-E)              |
  | 2    | D2             | P0.11                | DATA (左右間の独自シリアル通信) |
  | 3    | -              | -                    | GND                             |
  | 4    | -              | -                    | GND                             |
  | 5    | D1             | P0.18                | I2C(SDA)                        |
  | 6    | D0             | P0.16                | I2C(SCL)                        |
  | 7    | D4             | P0.19                | LED(インジケータ)               |
  | 8    | C6             | P0.20                | row0                            |
  | 9    | D7             | P0.22                | row1                            |
  | 10   | E6             | P0.23                | row2                            |
  | 11   | B4             | P1.0                 | row3                            |
  | 12   | B5             | P1.3                 | row4                            |
  | 13   | B6             | P0.9                 | col5                            |
  | 14   | B2             | P0.10                | col4                            |
  | 15   | B3             | P1.15                | col3                            |
  | 16   | B1             | P1.14                | col2                            |
  | 17   | F7             | P0.3                 | col1                            |
  | 18   | F6             | P0.30                | **A2**                          |
  | 19   | F5             | P0.0                 | **col0**                        |
  | 20   | F4             | P0.5                 | **A3**                          |
  | 21   | -              | -                    | VCC/+4.3V                       |
  | 22   | -              | -                    | BOOT/RESET                      |
  | 23   | -              | -                    | GND                             |
  | 24   | -              | -                    | RAW/+5V                         |

  特に，BLE Pro MicroでのADCを使うためにcol0が18ピンから19ピンに移されていることに注意してください。Lily58のファームウェアなどを使う際には，ピンアサインを変更する必要があります。