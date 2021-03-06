# Description

このリポジトリは深層学習ベースの流体シミュレーションを取り扱います．1次元移流方程式を例に[1.数値計算](https://github.com/yutaeis/deep-learning-based-computational-fluid-dynamics/blob/master/src/cfd_1d_convectioin.ipynb)と[2.深層学習](https://github.com/yutaeis/deep-learning-based-computational-fluid-dynamics/blob/master/src/dl_1d_convectioin.ipynb)の2つに分かれたJupyter Notebookになります．

1. 数値計算
数値計算に馴染みのない方を対象としたnotebookです．簡単な計算誤差の比較を行います．
- オイラー法
- 修正オイラー法

2. 深層学習
下記の２つの手法で数値計算解を再現します．深層学習フレムワークは[Chainer](https://chainer.org/)を，データは数値計算解を利用します．
- 畳み込みニューラルネットワーク(CNN)
- バックプロパゲーション


# Needed Install Stuff
このリポリト時に必要なものは```requirements.txt```に記載されています．Ubuntu 18.04では下記の手順でインストールできます．

```
sudo pip install -r requirements.txt
```


# Results

1. 数値計算
解析解と数値計算解の比較をしました．数値計算には1次法のオイラー法と2次法の修正オイラー法で計算誤差があることを確認しました．


<div align="center">
<img src="./figs/cfd-1d-convection.gif"/>
</div>

2. 深層学習
数値計算結果を教師データとして，CNNとBackpropagationで流れ場を予測するモデルを構築しました．また，データにノイズを与え，水増しすることで予測精度が向上することを確かめました．(Backpropagationでは移流速度，時間間隔，離散点の距離を推定し，数値計算と同じ方法で求めました．)

**CNN**
<div align="center">
<img src="./figs/cnn-all-1d-convection.gif"/>
</div>


**Backpropagation**

<div align="center">
<img src="./figs/backprop-1d-convection.gif"/>
</div>
