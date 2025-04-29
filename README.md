# 📝 Text Summarization Using Large Language Models (LLMs)

## 🎯 Objective

This project focuses on developing and fine-tuning multiple **Large Language Models (LLMs)** for the task of **text summarization**. We evaluate the summarization abilities of:
- **BERT** (for extractive summarization),
- **GPT-2** (for abstractive summarization), and
- **LLaMA** (either extractive or abstractive, based on implementation).

The models are trained and tested on a **public summarization dataset** from Kaggle to analyze and compare their performance using both qualitative and quantitative evaluation metrics.

---

## 📚 Dataset

We utilize the text summarization dataset available at:

🔗 [Text Summarization Dataset on Kaggle](https://www.kaggle.com/code/lusfernandotorres/text-summarization-with-large-language-models/input)

The dataset contains long-form texts and their corresponding summaries, suitable for training and evaluating summarization models.

---

## 🔧 Models and Techniques

### 1️⃣ BERT – Extractive Summarization
- Model: `bert-base-uncased`
- Approach: Identifies and extracts the most relevant sentences from the source text.
- Framework: Hugging Face Transformers
- Loss Function: Binary Cross-Entropy (for sentence relevance classification)
- Highlights: Maintains original sentence structure with high factual accuracy.

### 2️⃣ GPT-2 – Abstractive Summarization
- Model: `gpt2-medium`
- Approach: Generates entirely new summaries by understanding and paraphrasing content.
- Framework: Hugging Face Transformers
- Loss Function: Causal Language Modeling (Cross-Entropy Loss)
- Highlights: Coherent and fluent summaries but may introduce minor hallucinations.

### 3️⃣ LLaMA – Extractive or Abstractive (based on choice)
- Model: `llama-7b` (or similar variant)
- Approach: Implementation depends on configuration—supports both extractive and abstractive methods.
- Framework: Hugging Face, Transformers-compatible adapters
- Loss Function: Depends on summarization method (BCE or Cross-Entropy)
- Highlights: Capable of handling long context windows with strong performance.

---

## 🧪 Evaluation Metrics

- **Training Loss**: Final loss values tracked and compared for all models.
- **ROUGE Metrics**:
  - `ROUGE-N` (N-gram overlap)
  - `ROUGE-L` (Longest common subsequence)
- **BLEU Score**: Optional use for fluency and coherence evaluation.
- **Qualitative Analysis**: Human evaluation of:
  - Relevance
  - Conciseness
  - Coherence

---

## 🧾 Example Output

### 📌 Sample Input:
> "*The global economy is facing an unprecedented crisis due to the pandemic...*"

### 📤 Summaries:

#### 🔹 BERT (Extractive)
> "*The global economy is in crisis. Governments are implementing measures to address it.*"

#### 🔹 GPT-2 (Abstractive)
> "*The pandemic has caused a global economic crisis, prompting swift government interventions.*"

#### 🔹 LLaMA
> "*Facing an economic downturn, nations respond with policies to stabilize markets.*"

---

## 📊 Comparison of Results

| Model   | Loss (Final) | ROUGE-L | Summary Style      | Strengths                 | Weaknesses              |
|---------|--------------|----------|---------------------|----------------------------|--------------------------|
| BERT    | 0.21         | 0.57     | Extractive          | Factual accuracy           | Less abstraction         |
| GPT-2   | 1.43         | 0.64     | Abstractive         | Fluency & coherence        | May generate hallucinations |
| LLaMA   | 1.10         | 0.61     | Hybrid (flexible)   | Balanced performance       | Heavier computation      |

---

## 🗂️ Project Structure

