# LLaMA3-8B Finetuning with Unsloth for Materials Composition Classification

[![Author](https://img.shields.io/badge/Author-harshu0117-blue)](https://github.com/harshu0117)
[![Model](https://img.shields.io/badge/Model-LLaMA3--8B-green)](https://huggingface.co/meta-llama)
[![Framework](https://img.shields.io/badge/Unsloth-Finetuning%20Made%20Easy-orange)](https://github.com/unslothai/unsloth)

> **Repo Link**: [github.com/harshu0117/llama3_8B_finetune_unsloth](https://github.com/harshu0117/llama3_8B_finetune_unsloth)

---

## 📌 Project Objective

This project demonstrates **instruction-tuned fine-tuning** of **Meta-LLaMA 3.1 8B** using the **Unsloth** framework, applied to a **materials informatics task**:  
> **Predict whether a given chemical composition is a metal.**

The goal is to explore the **capability of LLMs in materials property prediction** by fine-tuning on structured instruction-response data and benchmarking against the raw base model.

---

## 🛠️ Methodology

- Used `train.json` and `test.json` files with instruction-input-output triples.
- Formatted data using **Alpaca-style prompt templates**.
- Finetuned using `SFTTrainer` from `trl` with 4-bit quantized weights.
- Performed inference with both:
  - 🔹 Base raw LLaMA-3.1 8B model
  - 🔸 Finetuned LLaMA-3.1 8B model
- Evaluated using accuracy, precision, recall, and F1-score.
- Visualized predictions using pie charts.

---

## 🔍 Prompt Format (Alpaca Style)

```txt
Below is an instruction that describes a task, paired with an input that provides further context. Write a response that appropriately completes the request.

### Instruction:
Given composition, is it metal? ->

### Input:
Ba5Sb3

### Response:
Yes, Ba5Sb3 is metal.
````

---

## 📊 Evaluation Results

| Model        | Accuracy   | Precision  | Recall     | F1 Score   |
| ------------ | ---------- | ---------- | ---------- | ---------- |
| 🔹 Raw Model | 0.5294     | 0.5294     | 1.0000     | 0.6923     |
| 🔸 Finetuned | **0.9020** | **0.9231** | **0.8889** | **0.9057** |

### 📈 Finetuned Accuracy Pie Chart

![Finetuned Accuracy](llma_raw_accuracy_pie.png)

### 📈 Raw Model Accuracy Pie Chart

![Raw Accuracy](accuracy_pie_chart.png)

---

## 🧪 Significance in Materials Domain

Large Language Models (LLMs) like LLaMA3 can be fine-tuned to act as **domain-specific property predictors** for materials science. This can enable:

* 🚀 **Rapid screening** of novel compositions.
* 🔍 **Text-to-property inference** without DFT or experiments.
* 🤖 **Foundations for Materials Copilots** — LLMs assisting scientists with structure-property insights.

**Use Cases**:

* Predictive pre-screening for alloys, oxides, semiconductors.
* Integration into materials design pipelines.
* Enhancing materials databases with natural language querying.

---

## 📂 Repo Structure

```
llama3_8B_finetune_unsloth/
│
├── train.json               # Training data
├── test.json                # Evaluation data
├── llma_finetuned.json      # Output from fine-tuned model
├── llma_raw.json            # Output from base model
├── accuracy_pie_chart.png   # Finetuned accuracy plot
├── llma_raw_accuracy_pie.png # Raw model accuracy plot
├── finetune_script.py       # Script to train using SFTTrainer
├── inference_script.py      # Script to run inference
└── README.md                # This file
```

---

## 🚀 Future Work

* Fine-tune on more detailed tasks: phase prediction, band gap estimation, formation energy.
* Add multi-modal support (composition + structure).
* Integrate with materials graph neural networks (e.g., MatDeepLearn, CGCNN).
* Create web demo for real-time inference.

---

## 🤝 Acknowledgements

* [Unsloth](https://github.com/unslothai/unsloth)
* [Meta AI](https://ai.meta.com/)
* [HuggingFace Transformers](https://huggingface.co/docs/transformers)
* Community contributors in materials AI.

---

📬 For questions or contributions, feel free to open an issue or reach out at:
👉 [github.com/harshu0117](https://github.com/harshu0117)

```

---

Let me know if you'd like:
- Badge-style metrics from Hugging Face Spaces.
- GitHub Actions CI/CD for auto-training.
- Colab notebook version of training/inference.
```
