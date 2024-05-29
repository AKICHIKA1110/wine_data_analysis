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

ワインの品質を予測するために、線形回帰モデルとランダムフォレスト回帰モデルの2つの機械学習モデルを構築.
高い精度の予測モデルから特徴量の重要度を測る。

#### モデル評価

- **赤ワインの平均二乗誤差 (MSE)**:
  - ランダムフォレスト: 0.301
  - 線形回帰: (計算結果を追加)

- **白ワインの平均二乗誤差 (MSE)**:
  - ランダムフォレスト: 0.348
  - 線形回帰: (計算結果を追加)

ランダムフォレストモデルは線形回帰モデルよりも優れており、特徴量と品質の複雑な関係を捉えることができます。

### 特徴量の重要度

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

