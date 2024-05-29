# ワイン品質分析

ポルトガル北部産の赤と白のヴィーニョヴェルデワインのサンプルに関連する 2 つのデータセットが含まれています。

このリポジトリには、赤ワインと白ワインの品質データセットに関する分析とグラフ化を行っています。本プロジェクトの目標は、ワインの品質に影響を与える要因を理解し、機械学習技術を用いて予測モデルを構築することです。

## データセット

このプロジェクトで使用されているデータセットは、[UCI機械学習リポジトリ](https://archive.ics.uci.edu/ml/datasets/Wine+Quality)から取得したものです。データには、赤ワインと白ワインのさまざまな理化学的特性とその品質評価が含まれています。

- `WineQuality-RedWine.csv`: 赤ワインのサンプル数　1599
- `WineQuality-WhiteWine.csv`: 白ワインのサンプル数　4898

## 分析と結果

### データの分布

#### 赤ワインの品質分布
![Red Wine Quality Distribution](./images/red_wine_quality_distribution.png)

- 品質評価は3から8の6段階評価
- 大多数の赤ワインは5から6の間で評価されているため、データの偏りがある。

![Red Wine scatter](./images/red_wine_scatter_plot.png)

#### 白ワインの品質分布
![White Wine Quality Distribution](./images/white_wine_quality_distribution.png)

- 品質評価は3から9までの範囲です。
- 大多数の白ワインは5から6の間で評価されており、特に6の評価が多いです。

![Red Wine scatter](./images/white_wine_scatter_plot.png)

### 機械学習モデル

ワインの品質を予測するために、赤ワインと白ワインの線形回帰モデルとランダムフォレストモデルをそれぞれ2つ機械学習モデルを構築.
線形回帰モデルでは、各特徴量の回帰係数による比較、PFI、PD、ICEによる分析を行った。

#### モデル評価

線形回帰モデルの精度
- 赤ワインモデルのMSE: 0.3900
- 赤ワインモデルのRMSE: 0.6245
- 赤ワインモデルのR^2: 0.4032
- 白ワインモデルのMSE: 0.5690
- 白ワインモデルのRMSE: 0.7543
- 白ワインモデルのR^2: 0.2653

ランダムフォレストの精度



### 特徴量の重要度

ここでは、線形回帰による予測モデルの回帰係数を比較し、重要度の比較を行う。

#### 赤ワインの特徴量重要度
![Red Wine Feature Importance](./result/red_wine_regression_coefficients.png)

- `アルコール`と`揮発性酸度`が赤ワインの品質に最も影響を与える重要な特徴です。

#### 白ワインの特徴量重要度
![White Wine Feature Importance](./result/white_wine_regression_coefficients.png)

- `アルコール`と`密度`が白ワインの品質に最も影響を与える重要な特徴です。

## 結論

分析の結果、アルコール含有量と酸度レベルがワインの品質に大きな影響を与えることが判明しました。
ランダムフォレストモデルは、赤ワインと白ワインの両方で強力な予測性能を示しました。

## 必要なパッケージ

分析を実行するには、以下のパッケージをインストールしてください。

```bash
pip install -r requirements.txt
```

## 参考文献
<img src="./images/book1.png" alt="no image" width="300"/>
- 出版社　技術評論社
- 著者　森下光之助

