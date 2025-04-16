# Analysis_Transformer_ComputationalCost_Optimization
Experimental Analysis of the Impact of Transformer Model’s Size on Performance and Computational Cost in Conversational Text Generation

## Introduction

This experimental analysis aims to evaluate the impact of Transformer model size on both performance and computational cost, focusing specifically on the **T5 models**.

The primary objectives are:

1.  Examine how scaling the model, from **T5 Small** to **T5 Baseline**, affects **dialogue generation quality**.
2.  Assess how **optimization techniques** can enhance the performance of a **smaller model** to potentially rival larger ones.

---

##  Experimental Setup

- **Models Used**: `T5-Small (60.4M parameteres)`, `T5-Baseline (224M parameteres)`
- **Task**: Persona-based conversational generation
- **Computaional cost Metrics**: FLOPs, training time, energy consumption, memory usage
- **Performance Metrics**: ROUGE score, average consistency score, inference time
- **Tools**: PyTorch, Transformers (HuggingFace), Colab

---

##  Results Visualization

###  Prediction from a new critic

**User 1:**  
_"I love hiking and nature walks. I also enjoy photography."_

**User 2:**  
_"I prefer staying indoors and reading books. I love mystery novels."_

| Model Variant              | Generated Dialogue |
|---------------------------|--------------------|
| **T5 Baseline**           |<pre>User 1: Hi, I'm [user 1's name].<br>User 2: Hi, I'm [user 2's name].<br>User 1: Nice to meet you, [user 2's name]. What do you like to do for fun?<br>User 2: I like to stay indoors and read books.<br>User 1: That's cool! I love hiking and nature walks. I also enjoy photography.<br>User 2: That's cool! I love hiking too. What kind of books do you like to read?<br>User 1: I like to read all kinds of books, but I especially like mystery novels.<br>User 2: Oh, that's cool! I like to read all kinds of books, but...</pre> |
| **T5 Baseline Optimized** | _"Hiking and nature walks. I enjoy hiking and nature walks."_ |
| **T5 Small**              |<pre>User 1: Hi, I'm [user 1's name].<br>User 2: Hi, I'm [user 2's name].<br>User 2: Hi, I'm [user 2's name].<br>User 2: Hi, I'm [user 2's name].<br>User 1: What do you like to do for fun?</pre> |
| **T5 Small Optimized**    |<pre>User 1: Hi, I'm [user 1's name].<br>User 2: Hi, I'm [user 2's name].<br>User 2: Hi, I'm [user 2's name].<br>User 1: What do you like to do for fun?<br>User 2: I like to go hiking and nature walks.</pre> |


### Metrics plots (WIP)

---
## Aknowledgments 

- 🤗 Dataset used  [google/Synthetic-Persona-Chat]([url](https://huggingface.co/datasets/google/Synthetic-Persona-Chat))
- 🤗 Pretrained model [T5]([url](https://huggingface.co/docs/transformers/model_doc/t5))


