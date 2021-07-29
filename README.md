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
|キースイッチ|18|Kailh Choc V2|[遊舎工房様販売ページ](https://shop.yushakobo.jp/collections/all-switches/products/kailh-choc-v2)|
|キーキャップ|18|CherryMX互換|1Uが16個、2Uが2個です。|
|Micro USB ケーブル|1|データ通信対応でUSB2.0 Micro-Bのもの。|

※Kailh choc V1も使えますがキーキャップにご注意ください。  
  
## オプション
|部品名|数|||
|-|-|-|-|
|表面実装タイプのダイオード|17||[遊舎工房様販売ページ](https://shop.yushakobo.jp/products/a0800di-02-100)|
|SK6812MINI-E|17|[取り付け方](led.md)|[遊舎工房様販売ページ](https://shop.yushakobo.jp/products/sk6812mini-e-10)|
|WS2812B|3|無くてもバックライトだけ光ります。|[遊舎工房様販売ページ](https://shop.yushakobo.jp/products/a0800ws-01-10)|
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
|小皿||
|斜めに切ったタイプのこて先||
|温度調節可能なはんだごて|300度-350度前後|
|ピンセット|LEDには必須|
|フラックス|LEDには必須|
|テスター||
|フラックスリムーバー||
|マスキングテープ||
|はんだ吸い取り線||
|リードベンダー||
|ラジオペンチ||

## 組み立て方（はんだ付け）
はんだ付けのやり方は動画で見るとわかりやすいです。  
パーツは思ったより壊れないので落ち着いて作業すると失敗しにくいです。  
 - ホームセンターのDCMさんの解説動画(58秒～) https://www.youtube.com/watch?v=JFQg_ObITYE&t=58s
  
ダイオードをD1からD18まで取り付けます。  
足を曲げて裏から差し込みます。  
ダイオードには向きがあります。三角形の先の棒と黒線を合わせましょう。  
![向きに注意](img/diode1.jpeg)  

表で更に足を曲げて抜けないようにします。  
ダイオードと並行に曲げるとあとでキースイッチに干渉しにくいです。
![足を曲げてはんだ付け](img/diode2.jpeg)  

はんだ付けをして足を切ります。  
マスキングテープでダイオードを固定して足を先に切ると綺麗に仕上がります。  
表面実装型を使うと表からは穴しか見えなくなります。  
![実装方法による差](img/diode3.jpeg)  

リセットスイッチを裏から差し込み表ではんだ付けします。  
![](img/reset.png)  

キースイッチを表から差し込み裏ではんだ付けします。  
![穴が小さいので押し込む必要があります。](img/keyswitch.jpeg)  

メインボードの裏にコンスルーを挿します。  
コンスルーの窓が高くて両方とも同じ向きになるように設置します。  
挿すだけではんだ付けはしません。  
![](img/conn.jpeg)   
※画像は違うキットなので場所が違いますが基盤、パーツの裏表は同じです。  


コンスルーにPro Microを挿します。TX0, RAW, USBの位置をシルク印刷と合わせましょう。  
そして、Pro Micro側のコンスルーの足を半田付けします。  
![四隅を先に固定すると安定します。](img/promicro.jpeg)   
※画像は違うキットなので場所が違いますが基盤、パーツの裏表は同じです。  

## 動作テスト
Pro Microに動作ソフト（ファームウェア）を書き込んで動作確認をしましょう。  
キットとPCをUSBケーブルでつないでください。   

ファームウェアをダウンロードしてPro Micro Web Updaterにアクセスしてください。
- テスト用ファームウェア [popntop_test.hex](https://github.com/Taro-Hayashi/Pop-n-Top/releases/download/untagged-6f31185aea07d10a6589/popntop_test.hex)
- Pro Micro Web Updater https://sekigon-gonnoc.github.io/promicro-web-updater/index.html

ファイルの選択ボタンを押してダウンロードしたファームウェアを指定したら、flashボタンを押しましょう。  
![](img/promicrowebupdater1.jpg)  

ブラウザのアドレスバーからメッセージが出てきたら、キットのリセットスイッチを押します。      
すると選択欄にArduino Microが出てきてクリックできるようになります。  
![](img/promicrowebupdater2.jpg)  

選択して接続を押すと書き込みが終わります。  
![](img/promicrowebupdater3.jpg)  
ファームウェアを更新する時もこの手順で行います。  

タイプすると1-17の数字が打てるはずです。  
反応しないキーが一箇所の場合スイッチ、同じ行で複数個の場合ダイオードのはんだが原因だと思います。   

お疲れ様でした。問題がなければはんだ付けは終了です。

## 組み立て方（後半）
USBケーブルを抜いてプレートを組付けます。  
アクリルからは保護フィルムを剥がしてください。割れやすいので気をつけましょう。  

ボトムプレート（黒・中）にスペーサー（短）をネジ（短）で取り付けます。  
スペーサーが隠れるようにミドルプレートを嵌めます。  
![](img/bottom1.jpeg)  

組み合わせたものをメインボードの裏からPro Microに重ならないようにネジ（短）で止めます。   
![](img/bottom2.jpeg)  
アクリルの左右が合っているとぴったり入ります。
間違ったまま押し込もうとすると故障の原因になるのでご注意下さい。

ボトムプレート（透明・小）にスペーサー（長）をネジ（長）で取り付けます。  
Pro Microを覆うようにネジ（長）で止めます。  
![](img/bottom3.jpeg)  

キーキャップを取り付けたら本番用のファームウェアに更新しましょう。
- [armors_via.hex](https://github.com/Taro-Hayashi/Pop-n-Top/releases/download/untagged-6f31185aea07d10a6589/popntop_via.hex)

ゴム足を貼ったら完成です。
![](img/done.jpeg)  

## キーマップの確認、変更方法
このキットはレイヤー機能を使っています。
![](img/3.png)
[Keyboard Layout Editor で見る](http://www.keyboard-layout-editor.com/##@_backcolor=#ffffff&name=Layout%20-%20Shotgun%20NUMPAD;&@_c=#aaaaaa&a:7&fa@:4;;&=//&_c=#cccccc;&=7&=8&=9&_c=#aaaaaa;&=back%20space&_x:0.5;&=&_c=#8792d6;&=home&=%E2%86%91&=page%20up&_c=#aaaaaa;&=&_x:0.5;&=&_c=#cf7e7e;&=/&&=*&=(&_c=#aaaaaa;&=&_x:0.5&c=#e0cb58;&=%E8%89%B2%E7%9B%B8+&=%E5%BD%A9%E5%BA%A6+&=%E6%98%8E%E5%BA%A6+&_fa@:1;;&=%E3%82%B9%E3%83%94%E3%83%BC%E3%83%89+&_fa@:2;;&=ON//OFF;&@_c=#aaaaaa&fa@:4;;&=*&_c=#cccccc;&=4&=5&=6&_c=#aaaaaa;&=tab&_x:0.5;&=&_c=#8792d6;&=%E2%86%90&_c=#cccccc;&=&_c=#8792d6;&=%E2%86%92&_c=#aaaaaa;&=&_x:0.5;&=&_c=#cf7e7e;&=$&=%25&=%5E&_c=#aaaaaa;&=&_x:0.5&c=#e0cb58&fa@:2;;&=%E5%89%8D%E3%81%AE%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3&_c=#cccccc;&=&=&=&_c=#e0cb58;&=%E6%AC%A1%E3%81%AE%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3;&@_c=#aaaaaa&fa@:4;;&=-&_c=#cccccc;&=1&=2&=3&_c=#aaaaaa&t=#000000%0A#c91818&a:5&fa@:4&:1;&h:2;&=%0A%E9%95%B7%E6%8A%BC%E3%81%97UPPER%0A%0A%0A%0A%0Aenter&_x:0.5&t=#000000&a:7;&=&_c=#8792d6;&=end&=%E2%86%93&=page%20down&_t=#dbbc1f&h:2;&=RGB&_x:0.5&c=#aaaaaa&t=#000000;&=&_c=#cf7e7e;&=!&=/@&=#&_c=#e69a9a&h:2;&=&_x:0.5&c=#e0cb58;&=%E8%89%B2%E7%9B%B8-&=%E5%BD%A9%E5%BA%A6-&=%E6%98%8E%E5%BA%A6-&_fa@:1;;&=%E3%82%B9%E3%83%94%E3%83%BC%E3%83%89-&_c=#e0d084&h:2;&=;&@_c=#aaaaaa&t=#000000%0A#152bab&a:5&fa@:1&:1;;&=+%0A%E9%95%B7%E6%8A%BC%E3%81%97LOWER&_c=#cccccc&t=#000000&a:7&fa@:4;&w:2;&=0&=.&_x:1.5&c=#a2abe8;&=&_c=#8792d6&w:2;&=insert&=del&_x:1.5&c=#cf7e7e&t=#dbbc1f;&=RGB&_t=#000000&w:2;&=)&_c=#ccccccc;&=&_x:1.5&c=#dbcb79;&=&_c=#cccccc&w:2;&=&=;&@_x:5.5&t=#152bab&f:3&w:5&h:0.5&d:true;&=LOWER%20LAYER&_x:0.5&t=#c91818&f:3&w:5&h:0.5&d:true;&=UPPER%20LAYER&_x:0.5&t=#a18806&f:3&w:5&h:0.5&d:true;&=RGB%20LAYER)  

使わないキーを削除したり使用頻度の高いキーを押しやすい位置に変更してみましょう。  
  
JSONファイルをダウンロードしたらChromeかEdgeでRemapにアクセスしてください。  
- [shotgun.json]()
- [Remap](https://remap-keys.app/)
  
![](img/remap1.png)  
左を選んで進んでいくとJSONファイルを求められるのでダウンロードしたものを指定します。  
![](img/remap2.png)   
  
変更が終わったら右上のflashボタンを押すと反映されます。  
![](img/remap3.png)  
  
上手くいかなくなったときはいったんリセットすると直ることがあります。  
![](img/remap4.png)  
  
## 液晶タブレットに乗せる場合
1番上の行を引っ掛ける事で液タブに乗せる事ができます。
![](img/tab.jpeg)　　
ゴム足を外して両面テープで固定すると安定します。  
跡が残るといけないので画面には保護フィルムを貼ってください。  

## おまけ
寸法です。ダンボールで作れるペーパークラフトもあります。
![](img/size.png)　　
![](img/danbo.jpg)　　
- [realsizeA4.pdf]()  
- ネットプリント番号  日まで　　

A4サイズです。定規があればプリントしなくても作れます。

ファームウェアのフォルダ  
https://github.com/Taro-Hayashi/qmk_firmware/tree/master/keyboards/shotgun
  
ミドル、ボトムプレートのデザインデータ  
[popntop_plates.zip]()  
発注先のルールに沿ってデータを修正してください。  

ご不明な点があればBOOTHのメッセージかtwitterのリプライでいつでも聞いてください。  
  
foostan様のフットプリントを流用、改変して使わせていただきました。  
https://github.com/foostan/kbd/  
https://github.com/foostan/kbd/blob/master/LICENSE  
