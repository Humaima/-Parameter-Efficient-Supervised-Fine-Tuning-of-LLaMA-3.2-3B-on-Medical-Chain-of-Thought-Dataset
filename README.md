# 🧠 Parameter-Efficient-Supervised-Fine-Tuning-of-LLaMA-3.2-3B-on-Medical-Chain-of-Thought-Dataset
![medical-llm-thumbnail-alt](https://github.com/user-attachments/assets/cdb96d17-e977-4ec7-a45d-4c28f8dd8345)

The goal of this project was to fine-tune the LLaMA 3.2 (3B) model on a Medical Chain-of-Thought (CoT) dataset using Low-Rank Adaptation (LoRA) for parameter-efficient training. The model was trained to generate structured medical reasoning and responses, improving its ability to assist in clinical decision-making.

## 🧪 Project Highlights

- ✅ Fine-tunes only **0.81% of the model (24M params)** using LoRA adapters
- ✅ Optimized for **Google Colab or Kaggle T4** (full training ~2h)
- ✅ Supports 4-bit quantized model loading with `unsloth`
- ✅ Generates `<think>...</think>` and `<response>...</response>` outputs
- ✅ Supports uploading LoRA adapter + tokenizer to Hugging Face

## 📦 Setup
Install dependencies:
```bash
pip install -r requirements.txt






