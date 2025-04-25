# 🧠 Parameter-Efficient-Supervised-Fine-Tuning-of-LLaMA-3.2-3B-on-Medical-Chain-of-Thought-Dataset

LLaMA Medical CoT LoRA Medical License

![medical-llm-thumbnail-alt](https://github.com/user-attachments/assets/cdb96d17-e977-4ec7-a45d-4c28f8dd8345)

The goal of this project was to fine-tune the LLaMA 3.2 (3B) model on a Medical Chain-of-Thought (CoT) dataset using Low-Rank Adaptation (LoRA) for parameter-efficient training. The model was trained to generate structured medical reasoning and responses, improving its ability to assist in clinical decision-making.

## 🧪 Project Highlights

-  🏥 Medical Reasoning: Generates step-by-step clinical reasoning followed by concise answers
-  ⚡ Efficient Training: Uses 4-bit quantization and LoRA adapters (24M trainable params)
-  📊 Performance Tracking: Monitors loss and ROUGE-L scores via Weights & Biases
-  🚀 Deployment Ready: Available on Hugging Face Hub as LoRA adapters

## Model Example

**Model Input**

What are the first-line treatments for migraine?

**Model Output**

<think>
1. Migraine treatment involves acute and preventive strategies
2. First-line acute treatments include NSAIDs and triptans
3. Consider antiemetics if nausea is present
4. Preventive options include beta-blockers for frequent migraines
</think>

<response>
First-line treatments for migraine:
1. Acute: Ibuprofen (NSAID) or sumatriptan (triptan)
2. Add antiemetics like metoclopramide if nausea
3. Preventive: Propranolol if ≥4 attacks/month
</response>

## Getting Started

**Prerequisites**

- Python 3.9 or later
- NVIDIA GPU with at least 8GB VRAM (T4 or better recommended)
- CUDA 11.7/11.8 installed
- Hugging Face account (for model access)

**Installation**

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/medical-lora-llama3.2.git
   cd medical-lora-llama3.2
2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate    # Windows
3. Install dependencies:
   ```bash
   pip install -r requirements.txt

**Downloading the Model**

1. Request access to LLaMA 3.2 on Hugging Face
2. Configure your Hugging Face token:
   ```bash
   huggingface-cli login
3. The LoRA adapters will be automatically downloaded when running the inference snippet from kaggle notebook

## Notebook Access

The complete implementation is available in one Kaggle notebook:

[![Open in Kaggle]()

## How to Use

### Running the Notebook

1. **Kaggle Setup**:
   - Ensure you have a Kaggle account
   - Request access to LLaMA 3.2B from Hugging Face
   - Add your Hugging Face token to Kaggle secrets

2. **Notebook Execution**:
   - Open the notebook in Kaggle
   - Select a GPU accelerator (T4 or P100 recommended)
   - Run all cells sequentially

## Training Details

**Dataset**
- Source: FreedomIntelligence/medical-cot (Hugging Face)
- Data: 19,704 rows
- Format: Structured with <think> and <response> tags
- Split: 90% training, 10% validation

**Training Configuration**
| Parameter | Value | Description |
|-----------|-------|-------------|
| `lora_r` | 16 | LoRA rank |
| `batch_size` | 4 | Training batch size |
| `learning_rate` | 2e-5 | Initial learning rate |
| `max_seq_length` | 1024 | Maximum sequence length |

**Results**
| Metric | Value |
|--------|-------|
| Training Loss | 1.303 |
| Validation Loss | 1.653 |
| ROUGE-L | 0.67 |
| GPU Memory Usage | ~7.5GB |

**WANDB Logs for GPU Usage, Training, and Validation Loss**

## Resources

- [Hugging Face Model](https://huggingface.co/Hums003/llama3.2B-lora-medical-cot)
- [W&B Dashboard](https://wandb.ai/Hums003/medical-lora-llama3.2)
- [Medical CoT Dataset](https://huggingface.co/datasets/FreedomIntelligence/medical-cot)

## License

Apache 2.0 - See [LICENSE](LICENSE) for details.






