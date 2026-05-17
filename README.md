# 🎓 Student Grade Classification using Neural Networks

A Deep Learning project that predicts students' **grade class** based on academic and demographic features, using a fully connected **Artificial Neural Network (ANN)**. The project compares two model configurations — **ReLU** vs **Tanh** activation — to find the best-performing setup.

---

## 📌 Project Overview

| Property        | Details                                      |
|-----------------|----------------------------------------------|
| **Task**        | Multi-class Classification                   |
| **Dataset**     | Students Performance Dataset (Kaggle)        |
| **Target**      | `GradeClass` (student grade category)        |
| **Model**       | Fully Connected Neural Network (ANN)         |
| **Framework**   | TensorFlow / Keras                           |
| **Optimizer**   | Adam                                         |

---

## 📁 Project Structure

```
FinalProjectNN.ipynb   ← Main Jupyter Notebook (all steps included)
README.md              ← Project documentation
```

---

## 🧠 Model Architecture

A flexible model builder is used to run multiple experiments. Each hidden layer includes **BatchNormalization** and **Dropout** for regularization.

```
Input (num_features,)
    │
    ▼
Dense(N) → BatchNorm → Dropout
    │
    ▼
Dense(N) → BatchNorm → Dropout
    │
    ▼
Dense(N) → BatchNorm → Dropout
    │
    ▼
Dense(num_classes, softmax)  ← Output
```

---

## 🧪 Experiments

| Experiment | Hidden Layers   | Activation | Learning Rate | Dropout |
|------------|-----------------|------------|---------------|---------|
| Exp 1      | 128 → 64 → 32   | ReLU       | 0.001         | 0.25    |
| Exp 2      | 256 → 128 → 64  | Tanh       | 0.0005        | 0.20    |

---

## ⚙️ Training Details

- **Loss Function:** Categorical Crossentropy  
- **Epochs:** Up to 85 (with Early Stopping, patience=15)  
- **Batch Size:** 32  
- **Validation Split:** 20% of training data  
- **Callbacks:** EarlyStopping + ReduceLROnPlateau  
- **Train/Test Split:** 80% / 20% (stratified)  
- **Preprocessing:** StandardScaler normalization  

---

## 📊 Results

Both experiments are evaluated on the held-out test set. The best model is selected automatically based on test accuracy and used for:

- Loss & Accuracy curves (Train vs Validation)
- Confusion Matrix
- Full Classification Report (Precision, Recall, F1-Score per class)

---

## 🚀 How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2. Install Dependencies

```bash
pip install tensorflow numpy pandas matplotlib scikit-learn kagglehub
```

### 3. Run the Notebook

```bash
jupyter notebook FinalProjectNN.ipynb
```

Or open it directly in [Google Colab](https://colab.research.google.com/).

> **Note:** The dataset is downloaded automatically from Kaggle via `kagglehub`. Make sure you have a Kaggle account and your API credentials configured.

---

## 📦 Requirements

```
tensorflow >= 2.x
numpy
pandas
matplotlib
scikit-learn
kagglehub
```

---

## 📚 Dataset

**Students Performance Dataset** — downloaded automatically from Kaggle:
- Source: [`rabieelkharoua/students-performance-dataset`](https://www.kaggle.com/datasets/rabieelkharoua/students-performance-dataset)
- Target column: `GradeClass`
- Dropped columns: `StudentID` (non-informative)

---

## 🤝 Contributing

Pull requests are welcome! Feel free to open an issue for suggestions or improvements.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
