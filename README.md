
---

# BERT-Based Text Classification for Fake News Detection

This project implements a BERT-based model using the Hugging Face Transformers library for binary text classification. The model is trained on a dataset containing real and fake news tweets and is evaluated using common classification metrics.

## 📁 Dataset

The dataset should be in CSV format and must contain at least:
- `tweet`: The text data.
- `label`: The class label (`real` or `fake`).
https://github.com/diptamath/covid_fake_news/tree/main/data
The default file path used is `/content/Constraint_Train.csv`.

---

## 🛠️ Installation

Install the required libraries using the following command:

```bash
pip install transformers datasets scikit-learn
```

---

## 🚀 How to Run

1. **Load Dataset**  
   Update the `file_path` variable in the script to point to your dataset.

2. **Preprocessing**  
   - Encode text using `BertTokenizer`.
   - Encode labels using `LabelEncoder`.

3. **Dataset Splitting**  
   - Uses `train_test_split` to create training and validation sets.

4. **Model**  
   Loads `bert-base-uncased` from Hugging Face and fine-tunes it on the dataset.

5. **Training**  
   Utilizes Hugging Face’s `Trainer` API with:
   - Early stopping
   - Evaluation strategy per epoch
   - Logging metrics (`accuracy`, `f1_score`)

6. **Evaluation**  
   After training, the model:
   - Prints evaluation metrics
   - Displays a confusion matrix and classification report

---

## 📊 Metrics Used

- Accuracy
- Weighted F1 Score
- Confusion Matrix
- Classification Report

---

## 🧠 Model Architecture

- **Model**: BERT (`bert-base-uncased`)
- **Task**: Binary classification (`real` vs `fake`)
- **Training**: 5 epochs, early stopping if no improvement in 2 consecutive epochs
- **Token Length**: Max 128 tokens per input

---

## 📂 File Structure

```
.
├── Constraint_Train.csv     # Dataset file
├── train_script.ipynb       # Main training script (your current code)
├── README.md                # Project documentation
```

---

## 📌 Notes

- You can adjust the number of epochs, batch size, and max token length in the `TrainingArguments`.
- Make sure your dataset column names match the expected `tweet` and `label`.

---

## 🤝 Acknowledgements

- [Hugging Face Transformers](https://huggingface.co/transformers/)
- [scikit-learn](https://scikit-learn.org/)
- [PyTorch](https://pytorch.org/)

---

