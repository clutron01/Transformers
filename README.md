# 🤗 Hugging Face Transformers Assignment

This repository contains the implementation and theoretical answers for three Hugging Face Transformer scenarios. Each scenario demonstrates a different aspect of Natural Language Processing (NLP), ranging from simple sentiment analysis using the Pipeline API to manual text generation using `AutoTokenizer` and `AutoModelForCausalLM`.

---

# 📚 Scenario 1: Sentiment Analysis using Pipeline API

### Question 1: Which Hugging Face pipeline would you use?

**Answer:**

I used the **`sentiment-analysis`** pipeline because it is specifically designed to classify text into sentiment categories such as Positive, Negative, or Neutral. It automatically handles tokenization, model loading, inference, and prediction.

---

### Question 2: What output do you expect?

**Answer:**

For the review:

> *"The storyline was amazing, but the ending was disappointing."*

the model is expected to predict either **Neutral** (because the review contains both positive and negative opinions) or one of the sentiment classes with an associated confidence score, depending on the pretrained model used.

Example Output:

```python
{
    "label": "neutral",
    "score": 0.92
}
```

---

### Question 3: Why is the `pipeline()` abstraction useful for beginners compared to manually loading models and tokenizers?

**Answer:**

The `pipeline()` API is beginner-friendly because it performs most of the complex tasks automatically. It loads the tokenizer and model, preprocesses the input text, runs inference, and returns the prediction with only a few lines of code. This allows beginners to focus on learning NLP concepts instead of worrying about implementation details.

---

# 🌍 Scenario 2: Multilingual Sentiment Analysis

### Question 1: Why would this model be more suitable than the default sentiment analysis pipeline?

**Answer:**

The multilingual sentiment analysis model is trained on multiple languages, making it capable of understanding and predicting sentiment for English, Hindi, Spanish, and other supported languages. In contrast, the default sentiment analysis pipeline is primarily optimized for English and may produce less accurate results for non-English text.

---

### Question 2: Write the steps required to load and use this model.

**Answer:**

The basic steps are:

1. Install the Transformers library.
2. Import the `pipeline` function.
3. Load the multilingual sentiment analysis model.
4. Provide input text in any supported language.
5. Run inference and display the predicted sentiment.

This process enables sentiment analysis across multiple languages using a single pretrained model.

---

### Question 3: What factors would you consider before deploying it in production?

**Answer:**

Before deployment, I would consider:

- Model accuracy
- Inference latency
- Model size
- GPU/CPU memory requirements
- Supported languages
- Scalability for multiple users
- Cost of deployment
- Reliability and consistency of predictions

These factors help ensure that the application performs efficiently in real-world environments.

---

# 🤖 Scenario 3: Manual Workflow using AutoTokenizer and AutoModelForCausalLM

### Question 1: Compare the architecture of the Pipeline API and Manual Workflow.

**Answer:**

The Pipeline API provides a high-level interface where tokenization, preprocessing, model execution, and decoding are handled automatically. The manual workflow separates each step, requiring the developer to explicitly load the tokenizer and model, tokenize the input, generate the output, and decode the generated tokens. Although the manual approach requires more code, it provides greater flexibility and customization.

---

### Question 2: Explain the role of tokenization and token IDs in text generation.

**Answer:**

Tokenization converts human-readable text into smaller units called tokens. Each token is assigned a unique numerical identifier known as a token ID. Since transformer models understand only numerical data, these token IDs are passed to the model during inference. After the model generates new token IDs, the tokenizer converts them back into readable text.

---

### Question 3: Describe how the text **"Explain Linear Regression"** flows through the tokenizer and model before the final output is generated.

**Answer:**

The workflow is as follows:

```
Input Prompt
        │
        ▼
"Explain Linear Regression"
        │
        ▼
AutoTokenizer
        │
        ▼
Token IDs (PyTorch Tensor)
        │
        ▼
AutoModelForCausalLM
        │
        ▼
Generated Token IDs
        │
        ▼
Tokenizer.decode()
        │
        ▼
Final Generated Response
```

The tokenizer first converts the prompt into token IDs. These token IDs are processed by the language model, which predicts the next sequence of tokens. Finally, the tokenizer decodes the generated token IDs back into natural language.

---

### Question 4: Discuss the trade-offs between ease of use and flexibility.

**Answer:**

The Pipeline API is easy to use and ideal for beginners because it requires very little code and handles most operations automatically. However, it offers limited customization.

The manual workflow requires more programming effort but provides complete control over tokenization, generation parameters, prompt formatting, and model outputs. This makes it more suitable for advanced applications and production environments.

---

# 🛠 Technologies Used

- Python 3
- Google Colab
- Hugging Face Transformers
- PyTorch
- Hugging Face Model Hub

---

# 📖 Conclusion

This assignment helped me understand both the high-level and low-level approaches to working with Hugging Face Transformers. I learned how to perform sentiment analysis using the Pipeline API, how multilingual models improve performance across different languages, and how the manual workflow using `AutoTokenizer` and `AutoModelForCausalLM` provides greater flexibility and control over text generation.
