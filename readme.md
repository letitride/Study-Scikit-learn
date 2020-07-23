# データセット

## 規則性のあるデータセット

```sklearn.datasets```

クラスタデータ:```make_blobs```，三日月形:```make_moons```，円形:```make_circles```

## iris アヤメ

```sklearn.datasets```

```load_iris```

## 乳がんデータセット

```sklearn.datasets```

```load_breast_cancer```

## mglearn (Pythonではじめる機会学習library)

### メモリ価格の時系列推移

```
import os
os.path.join(mglearn.datasets.DATA_PATH, "ram_price.csv"))
```


# 回帰

## 線形回帰

```LinearRegression```

重回帰も同じモデルとなる。

大きいデータセットや高次元のデータに適する。

## リッジ回帰

線形回帰のオーバーフィットに対して正則化するモデル

```Ridge```

alpha値で正則化の強度を変更できる

## ロッソ回帰

特徴量を削減して正則化するモデル

```Lasso```

# 分類

## 最近傍法

回帰もある。

小さいデータに関しては良いベースラインになる。

## ロジスティック回帰

回帰とつくが分類アルゴリズム

```LogisticRegression```

C値で正則化の強度を変更できる


## ナイーブベイズ

クラス分類にしか使えない。線形モデルより高速。大きいデータセット、高次元のデータに適する.

## サポートベクタマシン

```LinearSVC```,```SVC```

回帰もある。

分類線とデータ間にマージンをとるアルゴリズム。ソフトマージン（マージン内にデータが入ることを許可する）とハードマージン(許可しない)がある。

非線形なデータセットに対して、カーネル法を用いて次元追加を行ったデータを分類できる。

データのスケールを調整する必要がある。

## 決定木

```DecisionTreeClassifier```

回帰も可能。```DecisionTreeRegressor```

決定木は決定アルゴリズムが分かり易いが、過剰適合しやすく汎化性能が低くなる傾向がある。

### ランダムフォレスト

複数の異なる(汎化性能)決定木を用いて、各決定木が予測した値の平均値をとることで決定木の過剰適合を解決する手法。

```RandomForestClassifier```

回帰も可能。```RandomForestRegressor```


### 勾配ブースティング

```GradientBoostingClassifier```

回帰もある。```GradientBoostingRegressor```

複数の決定木を用いて、前回の決定木の予測結果を別の決定木で補正する。多くの決定木を用いることで、補正機会が多くなり精度があがる。

デフォルトでは深さ3、100個の決定木が作成される。

過学習には、木の深さを```max_depth```制限するか、学習強度```learning_rate```を下げることで対応できる。

## ニューラルネットワーク

```sklearn.neural_network```

```MLPClassifier```

# スケール処理

## StandardScaler

標準化

```StandardScaler```

## RobustScaler

中央値と四分位数

```RobustScaler```

極端に他の値と異なるようなハズレ値を無視する。

## MinMaxScaler

データセットを0〜1の値に変換する。

```sklearn.preprocessing.MinMaxScaler```

## Normalizer

データポイントを半径1の円(高次元なら球面)に投射する。ベクトルの長さではなく角度を問題とする時に用いる。

```Normalizer```