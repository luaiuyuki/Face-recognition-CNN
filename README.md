Face-recognition-CNN

💻 プロジェクト概要：CNN、FaceNet、OpenCV(LBPH)を用いた顔認識システム

🧠 紹介
本プロジェクトでは、以下の3つの主要手法を用いて顔認識システムを構築しています：

CNN（畳み込みニューラルネットワーク）：スクラッチから学習

FaceNet：顔の特徴ベクトル（embedding）を作成し、距離を比較

OpenCV LBPH：従来手法で、二値化された画像のヒストグラムを使用

システムは以下の入力から人物を認識可能です：

保存された動画

ライブウェブカメラ映像

📁 ディレクトリ構成

├── data/
│   ├── train/            # 学習用の元動画（人物ごとにフォルダ分け）
│   └── video/            # テスト用動画
│
├── dataset/
│   ├── train/            # 動画から抽出した顔画像（学習用）
│   └── val/              # 検証用データ
│
├── notebook/
│   ├── face_recognition_face_net.ipynb     # FaceNetによる顔認識
│   ├── face_recognition_cnn.ipynb          # CNNによる学習・認識
│   └── face_recognition_LBPH.ipynb         # OpenCV LBPHによる認識
│
├── output/
│   ├── output_facenet.mp4
│   ├── output_video_cnn.mp4
│   └── webcam.mp4         # 認識結果を含む出力動画
│
├── face_cnn_model.keras                # 学習済みCNNモデル
├── haarcascade_frontalface_default.xml # OpenCV顔検出モデル
├── label_map.pkl                        # ラベルと名前のマッピングファイル
├── trainer.yml                           # LBPH学習設定（使用する場合）
├── Trump_test.mp4                        # テスト用入力動画
├── README.md                             # 本README


⚙️ システムの動作手順

1. データ抽出

data/train/ に動画を配置（人物ごとにフォルダを分ける）

自動で顔画像を抽出し、dataset/train/ と dataset/val/ に保存

2. モデル学習

CNN：顔分類モデルを学習

FaceNet：事前学習済みモデルを使用し、embeddingベクトルを生成し、コサイン距離またはユークリッド距離で比較

LBPH：OpenCVで顔画像のヒストグラムを用いて学習

3. 顔認識

ウェブカメラまたは既存動画で実行

認識結果付き動画を output/ に保存

🧩 必要ライブラリ

pip install -r requirements.txt


主なライブラリ

opencv-python

numpy

tensorflow, keras

scikit-learn

mtcnn または dlib

pickle（label map保存用）

📌 ノートブック使用方法

face_recognition_face_net.ipynb：FaceNetモデルによる認識

face_recognition_cnn.ipynb：CNNによる学習とテスト

face_recognition_LBPH.ipynb：OpenCV LBPHによる認識

⚠️ dataset/ フォルダと label_map.pkl が正しい形式で準備されていることを確認してください。

📽️ 出力結果

実行後、出力結果は output/ フォルダに保存されます
