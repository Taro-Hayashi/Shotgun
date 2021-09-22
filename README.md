# Shotgun テンキーパッド ビルドガイド
- [キット内容](#キット内容)
- [組み立て方（はんだ付け）](#組み立て方はんだ付け)
- [動作テスト](#動作テスト)
- [組み立て方（後半）](#組み立て方後半)
- [カスタマイズ](#キーマップの確認変更方法)
- [おまけ](#おまけ)

## キット内容
![パーツ一覧](img/parts.jpg)  
||部品名|数| |
|-|-|-|-|
|1|メインボード（黒・大）|1||
|2|ミドルプレート（透明・中）|1||
|3|ボトムプレート（黒・中）|1||
|4|ボトムプレート（透明・小）|1||
|5|ネジ（短）|8|3mm|
|6|ネジ（長）|8|5mm|
|7|スペーサー（短）|4|3mm|
|8|スペーサー（長）|4|8mm|
|9|ダイオード|18||
|10|リセットスイッチ|1||
|11|ゴム足|4||

## キット以外に必要なもの
|部品名|数|||
|-|-|-|-|
|Pro Micro コンスルー付き|1||[遊舎工房様販売ページ](https://shop.yushakobo.jp/products/promicro-spring-pinheader)|
|キースイッチ|18|	Kailh Choc V1 もしくは V2||
|キーキャップ|18|スイッチに対応したもの|1Uが16個、2Uが2個です。|
|Micro USB ケーブル|1|データ通信対応でUSB2.0 Micro-Bのもの。|

## オプション
|部品名|数|||
|-|-|-|-|
|SK6812MINI-E|18|[取り付け方](led.md)|[遊舎工房様販売ページ](https://shop.yushakobo.jp/products/sk6812mini-e-10)|
|WS2812B|5|無くてもバックライトだけ光ります。|[遊舎工房様販売ページ](https://shop.yushakobo.jp/products/a0800ws-01-10)|
|1N4148W|18|表面実装タイプのダイオード|[遊舎工房様販売ページ](https://shop.yushakobo.jp/products/a0800di-02-100)|
|両面テープ||ねじの頭の0.5㎜より厚いものがおすすめです。||

## 必要な工具
|工具名| |
|-|-|
|はんだごて||
|はんだごて置き場||
|鉛入りはんだ||
|細いドライバー|+の1番ドライバー。|
|ニッパー等ダイオードの足を切れるもの|金属用でない場合刃こぼれします。|
|Microsoft Edge、もしくはGoogle Chrome||

## あると便利な工具
|工具名||
|-|-|
|耐熱シリコンマット||
|斜めに切ったタイプのこて先||
|温度調節可能なはんだごて|300度-350度前後|
|ピンセット|LEDには必須|
|フラックス|LEDには必須|
|テスター||
|フラックスリムーバー||
|マスキングテープ||
|はんだ吸い取り線||
|リードベンダー||

## 組み立て方（はんだ付け）

はんだ付けのやり方は動画で見るとわかりやすいです。  
パーツは思ったより壊れないので落ち着いて作業すると失敗しにくいです。  
 - ホームセンターのDCMさんの解説動画(58秒～) https://www.youtube.com/watch?v=JFQg_ObITYE&t=58s

それではダイオードをD1からD17まで取り付けます。  
足を曲げて裏から差し込みます。  
![](img/diode1.jpeg)  
ダイオードには向きがあります。三角形の先の棒と黒線を合わせましょう。  

表で更に足を曲げて抜けないようにします。  
![](img/diode2.jpeg)   
はんだ付けをして足を切ります。  

リセットスイッチを裏から差し込み表ではんだ付けします。  
![](img/reset3.jpg)  

キースイッチを表から差し込み裏ではんだ付けします。  
![](img/keyswitch.jpg)  

メインボードの裏にコンスルーを挿します。  
コンスルーの窓が高くて両方とも同じ向きになるように設置します。  
![](img/promicro4.jpg)   
挿すだけではんだ付けはしません。  

コンスルーにPro Microを挿します。TX0, RAW, USBの位置をシルク印刷と合わせましょう。  
![](img/promicro5.jpg)   
そして、Pro Micro側のコンスルーの足を半田付けします。  
![](img/promicro6.jpg)    

## 動作テスト
Pro Microに動作ソフト（ファームウェア）を書き込んで動作確認をしましょう。  
キットとPCをUSBケーブルでつないでください。   

ファームウェアをダウンロードしてPro Micro Web Updaterにアクセスしてください。
- テスト用ファームウェア [shotgun_test.hex](https://github.com/Taro-Hayashi/Shotgun/releases/download/14.15/shotgun_test.hex)
- Pro Micro Web Updater https://sekigon-gonnoc.github.io/promicro-web-updater/index.html

ファイルの選択ボタンを押してダウンロードしたファームウェアを指定したら、flashボタンを押しましょう。  
![](img/promicrowebupdater1.jpg)  

ブラウザのアドレスバーからメッセージが出てきたら、キットのリセットスイッチを押します。      
すると選択欄にArduino Microが出てきてクリックできるようになります。  
![](img/promicrowebupdater2.jpg)  

選択して接続を押すと書き込みが終わります。  
![](img/promicrowebupdater3.jpg)  
ファームウェアを更新する時もこの手順で行います。  

タイプすると1-18の数字が打てるはずです。  

お疲れ様でした。問題がなければはんだ付けは終了です。

## 組み立て方（後半）
USBケーブルを抜いてプレートを組付けます。  
アクリルからは保護フィルムを剥がしてください。割れやすいので気をつけましょう。  

メインボード裏面の赤丸の箇所にスペーサー（短）をネジ（短）で取り付けてミドルプレート（透明・中）を嵌めます。
![](img/bottom2.jpg)  
ボトムプレート（黒・中）をネジ（短）で止めます。  

メインボードの残ったネジ穴にスペーサー（長）をネジ（長）で取り付け、ボトムプレート（透明・小）をネジ（長）で止めます。  
![](img/bottom3.jpg)   

キーキャップを取り付けたら本番用のファームウェアに更新しましょう。
- [shotgun_via.hex](https://github.com/Taro-Hayashi/Shotgun/releases/download/14.15/shotgun_via.hex)

ゴム足を貼ったら完成です。
![](img/done.jpeg)  

## キーマップの確認、変更方法
このキットはレイヤー機能を使っています。
![](img/3.png)
[Keyboard Layout Editor で見る](http://www.keyboard-layout-editor.com/#/gists/2a190f28f4e33f743adb7195d6259d90)  

使わないキーを削除したり使用頻度の高いキーを押しやすい位置に変更してみましょう。  

ChromeかEdgeでRemapにアクセスしてください。  
- Remap https://remap-keys.app/

![](img/remap1.png)  
左を選んで進んでいくとアドレスバーからメッセージが出てキーボードを選択できます。  

変更が終わったら右上のflashボタンを押すと反映されます。  
![](img/remap3.png)  

## 液晶タブレットに乗せる場合
1番上の行を引っ掛ける事で液タブに乗せる事ができます。
![](img/tab.jpeg)　　
ゴム足を外して両面テープで固定すると安定します。  
跡が残るといけないので画面には保護フィルムを貼ってください。  

## おまけ
寸法です。ダンボールで作れるペーパークラフトもあります。
![](img/size.png)　　
![](img/danbo.jpg)　　
- [realsizeA4.pdf](https://github.com/Taro-Hayashi/Shotgun/releases/download/14.15/realsizeA4.pdf)  

A4サイズです。定規があればプリントしなくても作れます。

ファームウェアのフォルダ  
https://github.com/Taro-Hayashi/qmk_firmware/tree/master/keyboards/shotgun

VIA用JSONファイル [shotgun.json](https://github.com/Taro-Hayashi/Shotgun/releases/download/14.15/shotgun.json)  

ミドル、ボトムプレートのデザインデータ  
[shotgun_plates.zip](https://github.com/Taro-Hayashi/Shotgun/releases/download/14.15/shotgun_plates.zip)  
発注先のルールに沿ってデータを修正してください。  

ご不明な点があればBOOTHのメッセージかtwitterでいつでも聞いてください。  
販売ページ: https://tarohayashi.booth.pm/items/3154474

foostan様のフットプリントを流用、改変して使わせていただきました。  
https://github.com/foostan/kbd/  
https://github.com/foostan/kbd/blob/master/LICENSE  
