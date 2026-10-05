# 🧠 LSTM RNN — Next Word Prediction

<p align="center">
  <b>Deep Learning • NLP • RNN • LSTM • Sequence Modeling • Streamlit</b>
</p>

<p align="center">
  An end-to-end Deep Learning project that predicts the next word in a text sequence using an LSTM-based Recurrent Neural Network.
</p>

<p align="center">
  <a href="https://lstmrnn-8cm8qrcrfixexh3q45cqh6.streamlit.app/">🚀 Live Demo</a>
  &nbsp; | &nbsp;
  <a href="https://github.com/tusharaitechie/LSTM_RNN">💻 GitHub Repository</a>
</p>

---

## 📌 Project Overview

**LSTM RNN — Next Word Prediction** is a Natural Language Processing project built using Python, TensorFlow/Keras and Streamlit.

The objective is to train a recurrent neural network that learns patterns from a text corpus and predicts the **next most probable word** based on the sequence provided by the user.

Example:

```text
Input:
To be or not to

Prediction:
be
```

### End-to-End Workflow

```text
Text Corpus
    ↓
Text Preprocessing
    ↓
Tokenization
    ↓
Sequence Generation
    ↓
Padding
    ↓
LSTM Model
    ↓
Model Training
    ↓
Model Saving
    ↓
Next Word Prediction
    ↓
Streamlit Deployment
```

---

## 🎯 Problem Statement

Predicting the next word in a sentence is a fundamental NLP problem.

Given a sequence such as:

```text
To be or not to
```

the model learns language patterns from the training corpus and predicts the most probable next word.

Traditional feed-forward neural networks do not naturally preserve sequential context. RNNs address this limitation, while **LSTM networks** improve the ability to retain useful information across longer sequences.

---

## 💡 Solution

This project uses an **LSTM-based Recurrent Neural Network** trained on a text corpus.

Training examples are created in the form:

```text
Input Sequence → Target Word
```

For example:

```text
To                 → be
To be              → or
To be or           → not
To be or not       → to
To be or not to    → be
```

The LSTM learns these sequential relationships and uses them during inference to predict the next word.

---

## 🏗️ Project Architecture

```text
                    ┌────────────────────┐
                    │    hamlet.txt     │
                    │    Text Corpus    │
                    └─────────┬──────────┘
                              │
                              ▼
                    ┌────────────────────┐
                    │   Preprocessing    │
                    │  & Tokenization   │
                    └─────────┬──────────┘
                              │
                              ▼
                    ┌────────────────────┐
                    │ Sequence Generation│
                    │  Input → Target    │
                    └─────────┬──────────┘
                              │
                              ▼
                    ┌────────────────────┐
                    │ Sequence Padding   │
                    └─────────┬──────────┘
                              │
                              ▼
                  ┌────────────────────────┐
                  │      LSTM Network      │
                  │                        │
                  │  Sequential Learning   │
                  │          ↓             │
                  │         LSTM           │
                  │          ↓             │
                  │        Dense           │
                  │          ↓             │
                  │  Word Probabilities    │
                  └───────────┬────────────┘
                              │
                              ▼
                    ┌────────────────────┐
                    │ Trained LSTM Model │
                    │ next_word_lstm.h5  │
                    └─────────┬──────────┘
                              │
                              ▼
                    ┌────────────────────┐
                    │   Streamlit App    │
                    │      app.py        │
                    └─────────┬──────────┘
                              │
                              ▼
                    ┌────────────────────┐
                    │ Predicted Next     │
                    │       Word         │
                    └────────────────────┘
```

---

## 🧠 Why LSTM?

A standard RNN can suffer from the **vanishing gradient problem**, making it difficult to learn long-term dependencies.

LSTM addresses this using a gated memory mechanism:

- **Forget Gate**
- **Input Gate**
- **Cell State**
- **Output Gate**

Conceptually:

```text
Previous Hidden State
          │
          ▼
     ┌───────────┐
     │   LSTM    │
     │           │
     │ Forget    │
     │ Input     │
     │ Output    │
     │ Gates     │
     └─────┬─────┘
           │
           ▼
    Updated Hidden State
           │
           ▼
      Next Prediction
```

---

## 🔤 NLP Pipeline

### 1. Text Corpus

The project uses:

```text
hamlet.txt
```

as the training corpus.

### 2. Tokenization

Text is converted into numerical token IDs.

Example:

```text
To be or not to be
```

becomes a numerical sequence such as:

```text
[12, 45, 87, 21, 34, 45]
```

The tokenizer is saved as:

```text
tokenizer.pickle
```

### 3. Sequence Generation

The corpus is transformed into training sequences:

```text
To
To be
To be or
To be or not
To be or not to
To be or not to be
```

The model learns to predict the next token from previous tokens.

### 4. Padding

Sequences have different lengths, so padding is used to create consistent input dimensions.

```text
[0, 0, 12, 45]
[0, 12, 45, 87]
[12, 45, 87, 21]
```

---

## 🤖 Model Workflow

```text
Input Text
    ↓
Tokenizer
    ↓
Integer Sequence
    ↓
Padding
    ↓
LSTM
    ↓
Dense Layer
    ↓
Probability Distribution
    ↓
Highest Probability Token
    ↓
Predicted Word
```

---

## 🔮 Prediction Example

Suppose the user enters:

```text
To be or not to
```

The application:

1. Tokenizes the input.
2. Converts words into integer IDs.
3. Applies sequence padding.
4. Passes the sequence to the trained LSTM.
5. Generates probabilities for the vocabulary.
6. Selects the most probable token.
7. Converts the token back into a word.

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| 🐍 Python | Programming Language |
| 🧠 TensorFlow | Deep Learning Framework |
| 🔥 Keras | Neural Network API |
| 🔄 LSTM | Sequence Modeling |
| 🔤 NLP | Text Processing |
| 🔢 NumPy | Numerical Computing |
| 🐼 Pandas | Data Processing |
| 📊 Matplotlib | Visualization |
| 🧪 Scikit-learn | ML Utilities |
| 📈 TensorBoard | Training Monitoring |
| 🖥️ Streamlit | Web Application & Deployment |

---

## 📂 Repository Structure

```text
LSTM_RNN/
│
├── 📄 app.py
│   └── Streamlit application for next-word prediction
│
├── 📓 experiemnts.ipynb
│   └── Model development and experimentation notebook
│
├── 📚 hamlet.txt
│   └── Text corpus used for training
│
├── 🧠 next_word_lstm.h5
│   └── Trained LSTM model
│
├── 🔤 tokenizer.pickle
│   └── Saved tokenizer for inference
│
├── 📦 requirements.txt
│   └── Required Python dependencies
│
└── 📖 README.md
    └── Project documentation
```

---

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/tusharaitechie/LSTM_RNN.git
```

### 2. Navigate to the Project

```bash
cd LSTM_RNN
```

### 3. Create Virtual Environment

#### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

#### macOS / Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Run the Application

Start Streamlit:

```bash
streamlit run app.py
```

The application will normally be available at:

```text
http://localhost:8501
```

---

## 🌐 Live Demo

### 🚀 [Launch LSTM RNN Live Demo](https://lstmrnn-8cm8qrcrfixexh3q45cqh6.streamlit.app/)

The application provides an interactive interface where users can enter text and receive a predicted next word.

---

## 💾 Model Serialization

The trained model is stored as:

```text
next_word_lstm.h5
```

The tokenizer is stored separately:

```text
tokenizer.pickle
```

This allows the Streamlit application to load the trained artifacts without retraining the model every time the application starts.

---

## 🛑 Early Stopping

Early Stopping can be used during training to stop the training process when the monitored performance stops improving.

Benefits:

- Prevents unnecessary training
- Reduces training time
- Helps reduce overfitting
- Improves training efficiency

---

## 🧪 Skills Demonstrated

### Deep Learning

- Neural Networks
- RNN
- LSTM
- Sequence Modeling
- Model Training
- Model Serialization

### NLP

- Text Preprocessing
- Tokenization
- Vocabulary Mapping
- Sequence Generation
- Padding
- Next Word Prediction

### Python

- Data Processing
- File Handling
- Serialization
- Virtual Environments
- Dependency Management

### Deployment

- Streamlit
- Model Loading
- Real-time Inference
- Web Application Deployment

---

## 📊 Project Highlights

| Category | Implementation |
|---|---|
| Problem | Next Word Prediction |
| Domain | Natural Language Processing |
| Model | LSTM |
| Architecture | Recurrent Neural Network |
| Learning Type | Supervised Learning |
| Input | Text Sequence |
| Output | Next Word |
| Corpus | Hamlet Text |
| Tokenizer | Keras Tokenizer |
| Sequence Handling | Padding |
| Saved Model | `next_word_lstm.h5` |
| Saved Tokenizer | `tokenizer.pickle` |
| Interface | Streamlit |
| Deployment | Streamlit Cloud |

---

## 🎓 Key Learning Outcomes

This project demonstrates the complete journey from raw text data to a deployed Deep Learning application:

```text
Raw Text
   ↓
Preprocessing
   ↓
Tokenization
   ↓
Sequence Engineering
   ↓
LSTM Training
   ↓
Model Serialization
   ↓
Inference
   ↓
Deployment
```

It provides practical understanding of how recurrent neural networks learn sequential patterns from text.

---

## 🔮 Future Improvements

- [ ] Top-K word predictions
- [ ] Top-P / nucleus sampling
- [ ] Temperature-based text generation
- [ ] Multi-word text generation
- [ ] Beam Search
- [ ] Bidirectional LSTM
- [ ] GRU model comparison
- [ ] Transformer-based language model
- [ ] Better model evaluation metrics
- [ ] Prediction confidence visualization
- [ ] Larger training corpus
- [ ] Docker containerization
- [ ] CI/CD pipeline
- [ ] Improved Streamlit UI

---

## ⚠️ Limitations

The quality of predictions depends heavily on the training corpus and vocabulary.

Because this is an LSTM-based language model trained on a specific corpus, it does not have the broad language understanding of modern Transformer-based Large Language Models.

This project is primarily a practical demonstration of **sequence modeling and next-word prediction using LSTM**.

---

## 💼 Why This Project Matters

This project demonstrates the complete machine learning lifecycle:

> **Data → Preprocessing → Feature Representation → Model Development → Training → Model Saving → Inference → Deployment**

It showcases practical skills in:

**Deep Learning + NLP + LSTM + Model Deployment**

---

## 👨‍💻 Author

### Tushar Nile

**Data Science | Machine Learning | Deep Learning | NLP | AI**

Passionate about building practical Machine Learning and Artificial Intelligence solutions.

---

## ⭐ Support

If you found this project useful:

⭐ Star the repository  
🍴 Fork the project  
🚀 Try the live demo  
💡 Share your feedback

---

## 🔗 Project Links

**GitHub Repository:**  
https://github.com/tusharaitechie/LSTM_RNN

**Live Demo:**  
https://lstmrnn-8cm8qrcrfixexh3q45cqh6.streamlit.app/

---

<p align="center">
  <b>Built with Python • TensorFlow • Keras • LSTM • RNN • NLP • Streamlit</b>
</p>

<p align="center">
  ⭐ If you like this project, consider giving the repository a star!
</p>
