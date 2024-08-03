# Barcoderの作り方
## 概要
バーコードリーダーをバーコーダーに改造する方法

## 部品
* バーコードリーダー　[BEVA バーコードリーダー](https://www.amazon.co.jp/BEVA-%E3%83%90%E3%83%BC%E3%82%B3%E3%83%BC%E3%83%89%E3%83%AA%E3%83%BC%E3%83%80%E3%83%BC-%E3%83%90%E3%83%BC%E3%82%B3%E3%83%BC%E3%83%89%E3%82%B9%E3%82%AD%E3%83%A3%E3%83%8A%E3%83%BC-%E3%83%8F%E3%83%B3%E3%83%89%E3%83%98%E3%83%AB%E3%83%89-%E5%BA%97%E8%88%97%E3%83%BB%E3%82%AA%E3%83%95%E3%82%A3%E3%82%B9%E3%83%BB%E7%89%A9%E6%B5%81%E3%83%BB%E5%80%89%E5%BA%AB%E3%83%BB%E5%9B%B3%E6%9B%B8%E9%A4%A8%E3%81%AA%E3%81%A9%E3%81%AB%E9%81%A9%E7%94%A8/dp/B077GRDQGP/ref=sr_1_4_pp?__mk_ja_JP=%E3%82%AB%E3%82%BF%E3%82%AB%E3%83%8A&crid=3GCNNLBRQEA4H&dib=eyJ2IjoiMSJ9.VrSsFDy3ZuOzJwdikeNgpZNLOdTY5yHvvlJs-igeNWXz6dwSsK5KDGNNJul3LV7rg3CX9hmQbNoYVu9j9SXFXXArC255ksk2aJMWPKIdG8cHKvO25laymux6D4aeblFqqW3IJgwSXZbhvEPpQLRDR2kHumAxz8QoZ5AeihpZe3LxrB0kB2Lok77Y2kgkMD8k3TAI9CKkoNVJL97aY3vG6LcuLcDQZ2z3zCxx4GtidFObpkmwLznyhLcPY8XfmpO-PAWJ91nzMSR3jwCZImjT7-S1evlbvwyuWo2fwENCJUk.Z2NFLG5r80as46m6_Katn0euS7iMAADjR2ZEKYzrxLY&dib_tag=se&keywords=BEVA%2B%E3%83%90%E3%83%BC%E3%82%B3%E3%83%BC%E3%83%89%E3%83%AA%E3%83%BC%E3%83%80%E3%83%BC&qid=1722152331&s=electronics&sprefix=beva%2B%E3%83%90%E3%83%BC%E3%82%B3%E3%83%BC%E3%83%89%E3%83%AA%E3%83%BC%E3%83%80%E3%83%BC%2B%2Celectronics%2C424&sr=1-4&th=1)<br>
他の機種でも可　例えば [Tera バーコードリーダー](https://www.amazon.co.jp/gp/product/B081W1VBHJ/ref=ppx_yo_dt_b_asin_title_o08_s00?ie=UTF8&th=1)<br>
⇒レーザー光学式（ミラーでスキャンするタイプ）で、走査速度が25Hz程度の低速のもの　

* アンプ　[HT82V73A](https://akizukidenshi.com/catalog/g/gI-17849/)
* スピーカー [マイクロスピーカー](https://akizukidenshi.com/catalog/g/gP-12494/)
* コンデンサ　[0.1μF](https://akizukidenshi.com/catalog/g/gP-17818/)  
* コンデンサ　[1.0μF](https://akizukidenshi.com/catalog/g/gP-07549/)
* オーディオ延長ケーブル　[3.5mmステレオミニ](https://akizukidenshi.com/catalog/g/gC-13084/)
* スライドスイッチ　[スライドスイッチ](https://akizukidenshi.com/catalog/g/gP-15370/)
* バーコーダ用基板<br>
  <details><summary>基板</summary>
  <img src="img/0_BarcoderAmp.png" width="600" alt="BarcoderAmp.png"></details>

  あるいは
  
  アンプ実装済み基板 [HT82V739使用アンプ基板](https://akizukidenshi.com/catalog/g/g103234/)<br>
  (上記基板使用の際はアンプとコンデンサは不要、配線方法は回路図を参考にしてください。）

## 回路図
<details><summary>回路図</summary>
<img src="img/schematic.png">
</details>

## 作製手順
1. 配線の準備<br>
<img src="img/11_WireAndParts.jpg" width="600"><br>

1. バーコードリーダ分解<br>
<img src="img/20_Barcoder.jpg" width="600"><br>
<img src="img/30_BarcodR_Disassemble.jpg" width="600"><br>

1. 配線接続<br>
基板裏側シールドを外す<br>
<img src="img/40_Board.jpg" width="600"><br>
アナログ(黄)、トリガ(白)、ブザー(灰)、スイング(青・緑)を接続<br>
<img src="img/51_Wire_SW_Buzzer_Analog_Swing.jpg" width="600"><br>
アナログ(黄) 8pinICの1番ピン<br>
<img src="img/52_Analog.jpg" width="600"><br>
トリガ(白)Q8,R46,R21、ブザー(灰)スイッチ足<br>
<img src="img/53_Wire_SW_Buzzer.jpg" width="600"><br>
スイング(青・緑) コイル端子4本のうち外側2本<br>
<img src="img/54_Swing.jpg" width="600"><br> 

1. 筐体穴あけ(Φ3.2)<br>
AudioOUT用(筐体内に貫通する位置注意)、スピーカー用<br>
<img src="img/60_Drill.jpg" width="600"><br>

1. スピーカ取り付け<br>
スピーカーに配線(橙、紫)取り付け、両面テープで貼る<br>
ホットメルトで固定<br>
<img src="img/71_SPEAKER.jpg" width="600"><br>

1. 基板に部品実装<br>
AMP,C1,C3,C4,C5<br>
 <img src="img/75_Barcoder_Amp.jpg" width="600"><br>

1. 基板に配線接続<br>
GND(黒)G2、5V(赤)V5<br>
アナログ(黄)A1、トリガ(白)T1、ブザー(灰)BZ1<br>
<img src="img/80_GND_5V.jpg" width="600"><br>

1. スイング停止用スイッチ取り付け<br>
スイングするミラーに当たらない位置にホットボンドで固定する。<br>
<img src="img/81_SwingSW.jpg" width="600"><br>
スイング停止する場合は、スイッチを短絡側に切り替え<br>
ミラーをテープで固定する<br>
<img src="img/82_SwingStop.jpg" width="600"><br>

1. 動作確認<br>
スピーカー(橙、紫)　P1,N1 どちらでもいい<br>
USBコネクタを取り付け<br>
基板反対面のスイッチを押して、ブザーから音が出ればOK<br>
音がでない場合は接続、基板上のICのはんだ付け状況を確認<br>
<img src="img/90_SP.jpg" width="600"><br>

1. AudioOut接続<br>
AudioOutケーブルを筐体にあけた穴から通して基板に接続する<br>
<img src="img/100_AudioOut.jpg" width="600"><br>
AudioOut(白)OUT1、AudioOut(赤)BZ2、AudioOut(黒)G1<br>
<img src="img/101_AudioOut.jpg" width="600"><br>
スペーサを基板の下に入れて固定する<br>
<img src="img/102_Fix.jpg" width="600"><br>

1. 動作確認2<br>
トリガボタンが押せるか(ケーブルが挟まっている場合あり)<br>
USBコネクタから給電して縞模様とバーコードを読み込ませる<br>
Lchから縞模様の音がでるか<br>
Rchからバーコード認識音がでるか<br>
（ヘッドホンを接続して確認するとわかりやすい）<br>

1. 組み立て<br>
筐体を元に戻して完成<br>
<img src="img/110_Assemble.jpg" width="600"><br>