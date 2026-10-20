# シリアル通信：加速度データを送ってみよう

## 1. 加速度データをPCに送ってみよう（シリアル通信）  @unplugged

シリアル通信は、micro:bit とコンピューターの間で、データを送受信する方法です。
このチュートリアルでは、microの加速度センサーで測定したデータを、
シリアル通信でコンピューターに送ってチェックする方法を紹介します。




## 2. データを送信する @unplugged

micro:bitの加速度を取得し、
一定の間隔でシリアル通信で次の３つの情報を送信します。


```text
- X方向の加速度
- Y方向の加速度
- Z方向の加速度
````

## 2-1 プログラム 1
メニューの``||loops:ループ||`` グループから ``||loops:500ミリ秒ごとに||`` をだして配置して、
メニューの``||Advanced:高度なブロック||`` を開き、``||serial:シリアル通信||`` グループから 
``||serial:シリアル通信 複数の数値をカンマ区切りで書き出す||`` をだしてセットします。

```blocks
loops.everyInterval(500, function () {
    serial.writeNumbers([
    0,
    1
    ])
})
```

## 2-2プログラム 2
``||serial:複数の数値をカンマ区切りで書き出す||`` にセットしてある ``||array:配列||`` の右側にある
プラス（+）の記号をクリックして、要素をふやします。

```blocks
loops.everyInterval(500, function () {
    serial.writeNumbers([
    0,
    1,
    0
    ])
})

```


## 2-3プログラム 3
``||serial:複数の数値をカンマ区切りで書き出す||`` の ``||array:配列||``に 
``||input:入力||``グループにある ``||input:加速度 x||`` をそれぞれあてはめ、上から（左から） x,y,z になるようにします。

```blocks
loops.everyInterval(500, function () {
    serial.writeNumbers([
    input.acceleration(Dimension.X),
    input.acceleration(Dimension.Y),
    input.acceleration(Dimension.Z)
    ])
})

```

## 2-4 ダウンロード
プログラムをmicro:bit に書き込みます。

## 3. データを見てみよう @unplugged

PCに表示された加速度データを確認します。

micro:bit シミュレータの下にある [ データを表示 デバイス ] をクリックしてデータをチェックします。

micro:bitを、

- 傾ける
- 動かす
- 振る

などして、値の変化を確認して、動かし方によって、表示される数値が変化することを確認します。

### やってみよう

micro:bitをいろいろな方向に動かして、
X・Y・Zの値がどのように変化するか観察してみましょう。

## 3-1 データの確認
実際にデータの確認をしてみましょう。

![文字列の表示](https://raw.githubusercontent.com/NBSTT/pxt-my-an/refs/heads/master/image/microbit-hello.gif)



## Finish: @unplugged

シリアル通信の紹介はここで終わりです。
お疲れ様でした。