# AJANTA Chatbot 🤖

## 📌 Introduction
**AJANTA** is an AI-powered chatbot built using **PyTorch** and **Natural Language Processing (NLP)** techniques.  
It is designed to answer customer queries such as:  

- Delivery availability (based on pin code)  
- Available products  
- Accepted payment methods  
- General FAQs and small talk (jokes, greetings, etc.)  

The chatbot uses a trained **Neural Network model** for intent classification and responds dynamically using a JSON-based intent dataset.  

---

## 🎯 Project Objectives
- Preprocess text data (intents, patterns, and responses)  
- Implement NLP techniques (tokenization, stemming, bag-of-words)  
- Train a feed-forward neural network for intent recognition  
- Handle real-time conversations with contextual responses  
- Validate delivery availability by checking **postal codes**  
- Deploy the chatbot for end-user interaction  

---

## 🛠️ Tools and Technologies
- **Language:** Python  
- **Libraries:**  
  - [PyTorch](https://pytorch.org/) (Neural Network implementation)  
  - [NLTK](https://www.nltk.org/) (tokenization, stemming)  
  - NumPy, Pandas (data handling)  
  - JSON (intents dataset)  
- **Environment:** Google Colab / Jupyter Notebook  

---

## 📂 Dataset
- **Intents File (`intents.json`)**  
  Contains tags, patterns, and responses for training the chatbot.  
- **Postal Data (Pin Code dataset)**  
  Used to verify delivery availability based on user input.  

---

## ⚠️ Challenges Faced
- Handling **unknown queries** with fallback responses  
- Tokenization & preprocessing issues with punctuation/special symbols  
- Ensuring correct mapping of pin codes to delivery availability  
- Maintaining balanced training across different intent classes  

---

## 🧠 Model Approach
### 1. **Data Preprocessing**
- Tokenization with NLTK  
- Stemming using PorterStemmer  
- Bag-of-Words representation  

### 2. **Neural Network Architecture**
```text
Input Layer → Hidden Layer (ReLU) → Hidden Layer (ReLU) → Output Layer
```
- Loss Function: CrossEntropyLoss  
- Optimizer: Adam  
- Training: 1000 epochs (batch size = 8, learning rate = 0.001)  

### 3. **Training Results**
- Final Loss ≈ **0.0002**  
- Model saved as `data.pth`  

### 4. **Conversation Flow**
- Intent classification using softmax probability (>0.75 threshold)  
- Response retrieval from `intents.json`  
- Special **pincode handling** to check delivery availability  

---

## 📊 Example Conversation
```bash
You: hi
AJ : Hi there, what can I do for you?

You: Tell me joke
AJ : I can’t believe I got fired from the calendar factory. All I did was take a day off!

You: What's on the menu
AJ : We have Cakes, Flowers and Gifts are on the menu!

You: Do you take credit card?
AJ : We accept most major Credit cards, Master Card, Paypal, American Express and Discover.

You: 560001   # (Postal Code)
AJ : Select your near Post Office
     0: Bangalore GPO
     1: Richmond Town PO
```

---

## ✅ Conclusion
- AJANTA chatbot provides **real-time intelligent responses** using a neural network.  
- Supports **dynamic delivery availability checks** via pin codes.  
- Can be scaled for **e-commerce, logistics, and postal service applications**.  

---

## 📖 References
- [PyTorch Documentation](https://pytorch.org/)  
- [NLTK Documentation](https://www.nltk.org/)  
- Custom JSON intents dataset  
- Postal Delivery Dataset  

---

### 🚀 How to Run Locally
1. Clone this repo:
   ```bash
   git clone https://github.com/your-username/AJANTA-Chatbot.git
   cd AJANTA-Chatbot
   ```
2. Install dependencies:
   ```bash
   pip install torch nltk numpy pandas
   ```
3. Run training:
   ```bash
   python train.py
   ```
4. Start chatbot:
   ```bash
   python chat.py
   ```
