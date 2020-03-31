# titanic_model2
Kaggleのタイタニックデータセットを、決定木、ランダムフォレスト、SVMで識別したモデル

Survivedのデータと関連が深そうな
"Pclass", "Sex", "Age", "Fare"
のデータのみを特徴量に利用し、3つの識別機でモデル作成をおこなった。
（パラメータ調整は未実施。欠損値は中央値で補間。）

モデル毎のScoreは下記の通りであった。
決定木・・・71.8%
ランダムフォレスト・・・72.2％
SVM・・・62.2％


# titanic_model3
上記のモデルに「家族の人数」「チケットの重複数」「敬称」の特徴量を追加したもの
識別器にはランダムフォレストを利用（一番汎か性能が高かったため）
Score　・・・　78.5%


# titanic_model4
上記のランダムフォレストのパラメータをGridSearchでチューニングしたもの

ベストのパラメータは
{'bootstrap': False, 'criterion': 'entropy', 'max_features': 4, 'min_samples_leaf': 2, 'min_samples_split': 2, 'n_estimators': 25}
であった。

Score　・・・　80.4%
目標としていた8割を超えたので満足しました。
