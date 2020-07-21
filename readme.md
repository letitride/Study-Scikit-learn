# データセット

## 規則性のあるデータセット

```sklearn.datasets```

クラスタデータ:```make_blobs```，三日月形:```make_moons```，円形:```make_circles```

## 乳がんデータセット

```sklearn.datasets```

```load_breast_cancer```

## メモリ価格の時系列推移

```
import os
os.path.join(mglearn.datasets.DATA_PATH, "ram_price.csv"))
```


# 回帰

## 線形回帰

```LinearRegression```

重回帰も同じモデルとなる。

## リッジ回帰

線形回帰のオーバーフィットに対して正則化するモデル

```Ridge```

alpha値で正則化の強度を変更できる

## ロッソ回帰

特徴量を削減して正則化するモデル

```Lasso```

# 分類

## ロジスティック回帰

回帰とつくが分類アルゴリズム

```LogisticRegression```

C値で正則化の強度を変更できる

## サポートベクタマシン

```LinearSVC```

回帰もある。

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

