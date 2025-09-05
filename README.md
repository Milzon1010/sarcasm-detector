
# 🧐 Sarcasm Detector

> Baseline NLP project for sarcasm & irony detection using **TensorFlow/Keras** with BiLSTM + handcrafted features.  
> Developed and tested in **Google Colab + WSL2 Linux**.

---

## 📂 Project Structure

sarcasm-detector/
├── data/
│ ├── raw/ # original dataset (sarcasm.csv: text,label)
│ └── processed/ # vocab, models, meta after training
│
├── src/ # core source code
│ ├── data.py # load & split dataset
│ ├── features.py # handcrafted features (emoji, caps, punctuation)
│ ├── model_baseline.py # BiLSTM + embedding model builder
│ ├── train.py # training script
│ ├── evaluate.py # evaluation (classification report, confusion matrix)
│ └── infer.py # inference on new text samples
│
├── configs/
│ └── default.yaml # training/eval configuration
│
├── Sarcasm_Detector_Colab_WSL.ipynb # Colab notebook workflow
└── README.md

## 🚀 Quickstart

### 1. Clone the repo
```bash
git clone https://github.com/Milzon1010/sarcasm-detector.git
cd sarcasm-detector

Create environment
python3 -m venv .venv
source .venv/bin/activate
pip install -U pip
pip install -r requirements.txt

Prepare dataset

text,label
"Great, another Monday morning. Perfect!",1
"Terima kasih banyak atas bantuannya",0

Train
python -m src.train

Evaluate
python -m src.evaluate

Inference
python -m src.infer "Great, exactly what I needed... another delay." "Terima kasih banyak"

🔍 Features

TextVectorization with max tokens & sequence length config
BiLSTM embedding model
Handcrafted features: emoji usage, caps ratio, punctuation bursts
Class-weight balancing for imbalanced dataset
Evaluation metrics: precision, recall, F1, confusion matrix
Threshold tuning for better F1 score
Inference CLI for quick sarcasm detection on text

📊 Example Output
SARCASM      p=0.873 | Great, exactly what I needed... another delay.
NOT SARCASM  p=0.102 | Terima kasih banyak atas bantuannya

🛠️ Tech Stack

Python 3.12+
TensorFlow 2.19
Keras 3
scikit-learn
pandas / numpy / matplotlib

👨‍💻 Author

Milzon (@milzon1010)
23+ years in Telecom → Pivoting into AI/ML & Data Analytics
