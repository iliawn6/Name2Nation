# 🌍 Name2Nation: Character-Level Name Origin Classifier

Name2Nation is a deep learning and NLP project that predicts the nationality of a name based on its characters. By learning cultural and linguistic patterns hidden in spelling, the model can distinguish between names from 18 different origins. Using character-level encoding and a GRU-based neural network, the project shows how even short text strings can carry rich cultural information.
&nbsp;  
## 📂 Dataset
- **Train:** multiple text files, each file contains names for a single origin.  
- **Test:** `test.csv` with names to classify.  
- Final training table: **Origin** (label), **Name** (string).  
&nbsp;  
## 🔄 Preprocessing
-  Lowercasing and Unicode normalization (accent folding); keep letters only.  
-  One-hot character encoding over the discovered character set.  
-  Fixed sequence length via padding to the longest name.  
-  One-hot targets across 18 origin classes.  
&nbsp;  
## 🧠 Model Structure
- Character sequence input → **GRU (128 units)** → Dense (ReLU) + Dropout → **Softmax** over 18 classes.  
- Trained with categorical cross-entropy, Adam optimizer, and early stopping.  

&nbsp;  
## 📊 Evaluation Metrics
-  **Multiclass ROC AUC** – measures probability quality.  
-  **Weighted F1 score** – balances performance across classes.  

&nbsp;  
## ✅ Results
-  **F1-Score:** 83%  
-  **Test ROC AUC:** 96%  

&nbsp;  
**🌟Name2Nation** shows how compact sequence models uncover cultural and linguistic signals from minimal text. The same recipe can be extended to tasks such as transliteration hints, entity normalization, and locale-aware name analytics—demonstrating the power of simple, character-level NLP.  
