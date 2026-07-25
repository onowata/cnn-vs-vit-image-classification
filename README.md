# cnn-vs-vit-image-classification

## 概要

CNN（Convolutional Neural Network）とVision Transformer（ViT）を用いて画像分類モデルを構築し、画像分類性能の比較を行いました。

CNNでは画像の局所的な特徴を利用した分類、ViTではTransformerを用いた画像全体の特徴を考慮した分類を行い、分類精度や学習時間の違いについて比較・考察しました。:contentReference[oaicite:1]{index=1}

## 使用技術

- Python
- PyTorch
- NumPy
- Matplotlib
- Jupyter Notebook

## 実験条件

|項目|CNN|ViT|
|---|---|---|
|データセット|CIFAR-10|CIFAR-10|
|Epoch|20|20|
|Optimizer|Adam|Adam|
|Loss|CrossEntropy|CrossEntropy|
|入力画像サイズ|32×32|224×224|
|事前学習|-|ImageNet（pretrained=True）| :contentReference[oaicite:2]{index=2}

## 結果

|項目|CNN|ViT|
|---|---:|---:|
|Accuracy|63.9%|97.29%|
|Loss|1.8223|0.1502|
|学習時間|97秒|8247秒| :contentReference[oaicite:3]{index=3}

## 工夫した点

- CNNとViTを同一データセット・同一Epoch数で学習させ、性能比較を行った。
- Accuracy、Loss、混同行列を用いて、それぞれのモデルの分類性能を多角的に評価した。
- 学習時間も比較対象に含め、精度だけでなく実用面も考慮した評価を行った。:contentReference[oaicite:4]{index=4}

## 考察

- 分類精度ではViTがCNNを大きく上回った。
- 一方で、ViTは学習時間が約2時間と非常に長く、用途によって使い分けが必要であることが分かった。
- 今回はImageNetによる事前学習済みモデルを利用したため、高い精度につながったと考えられる。:contentReference[oaicite:5]{index=5}

## 今後の改善点

- pretrained=Falseでの比較を実施する。
- 他の画像分類モデル（ResNet、EfficientNetなど）との性能比較を行う。
- ハイパーパラメータ（学習率・エポック数・バッチサイズ・ネットワーク構造：CNNの層の深さなど）の調整による性能改善を検討する。
