# 🚀 Fine-Tuning Flan-T5 for Data Science Narrative Generation

> "Transforming complex data science results into compelling human stories."

This repository provides a Google Colab notebook for fine-tuning the Flan-T5-base language model to generate human-readable narratives from complex data science outputs.

---

## 📖 Project Overview

The goal of this project is to bridge the gap between technical data science outputs and accessible human language. By fine-tuning a powerful language model like Flan-T5, we enable the automatic translation of data analysis findings into engaging, understandable narratives.

---

## 🛠️ Fine-Tuning Workflow

The fine-tuning process is detailed in [`fine_tune_flan-t5-base.ipynb`](fine_tune_flan-t5-base.ipynb) and includes:

1. **Environment Setup**
   - Install required libraries: `unsloth`, `datasets`, `transformers`, `accelerate`.
2. **System Compatibility Check**
   - Verify CUDA availability, PyTorch, and Transformers versions.
3. **Dataset Loading & Preprocessing**
   - Load dataset from `/content/drive/MyDrive/A_Manual_Dataset/DataScience_results_with_humanly.json`.
   - Convert data for Hugging Face `datasets`.
   - Split into training and validation sets.
4. **Model & Tokenizer Loading**
   - Load pre-trained `google/flan-t5-base` model and tokenizer.
5. **Tokenization & Label Creation**
   - Tokenize data science results and target narratives.
   - Create the required `labels` column.
6. **Parameter-Efficient Fine-Tuning (PEFT) with LoRA**
   - Configure and apply LoRA for efficient fine-tuning.
7. **Training Arguments Setup**
   - Define hyperparameters and configuration using `TrainingArguments`.
8. **Training Initialization**
   - Set up Hugging Face `Trainer` with PEFT model, arguments, and datasets.
   - Start training.
9. **Model Saving**
   - Save trained LoRA adapters and tokenizer for future use.
10. **Model Loading**
    - Load base model and apply saved LoRA adapters to reconstruct the fine-tuned model.
11. **Model Testing**
    - Use the fine-tuned model to generate narratives from new data science results.

---

## 📂 Dataset

- **Format:** JSON file containing pairs of:
  - `"complex_data_science_result"`
  - `"human_storytelling_narrative"`

---

## ▶️ How to Run

1. Open the notebook in Google Colab.
2. Click on "Runtime" in the menu and select "Change runtime type".
3. Add path of your own dataset
4. Run the cells sequentially to:
   - Install dependencies
   - Process data
   - Configure and train the model
   - Test the results

---

## ⚠️ Limitations & Future Work

> "The current model's performance is limited by the small size and potential lack of diversity in the dataset."

**Planned Improvements:**
- Acquire a larger, more diverse dataset
- Experiment with different LoRA configurations and other PEFT methods
- Explore advanced text generation strategies to improve narrative quality and fluency

---

*Feel free to open issues or contribute to this project!*


