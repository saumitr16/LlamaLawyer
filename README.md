# Fine-Tuning Llama 3.1 8B with QLoRA for Legal Chatbot Development

This repository contains a Google Colab notebook for fine-tuning the Llama 3.1 8B model on a law-based dataset using QLoRA (Quantized Low-Rank Adaptation). The project also includes a chatbot implementation and a PDF reader for document-based legal queries.

---

## Features

### Fine-Tuning with QLoRA:
- Fine-tunes the Llama 3.1 8B model using a law-specific dataset.
- Implements parameter-efficient training for faster and memory-efficient adaptation.
- Optimized for legal document understanding and context-specific responses.

### Chatbot Integration:
- A conversational chatbot trained for legal queries.
- Provides responses based on the fine-tuned Llama 3.1 model.

### PDF Reader:
- Reads and processes legal documents in PDF format.
- Extracts key content and allows chatbot queries directly from the document.

---

## Prerequisites

### Hardware:
- **Recommended:** A high-performance GPU (NVIDIA A100 or higher) for training.
- **Minimum:** GPUs with 24GB memory for QLoRA optimization.

### Software:
- Python 3.8 or later
- Google Colab or equivalent Jupyter notebook environment

### Required Python Libraries:
- `transformers`
- `peft`
- `datasets`
- `accelerate`
- `PyPDF2`
- `langchain`
- `gradio`

---

## Default QLoRA Parameters

The notebook uses the following default parameters for QLoRA-based fine-tuning:
- **Learning Rate:** 0.0002  
- **Batch Size:** 16  
- **Num Training Steps:** 1000  
- **Rank:** 8  
- **Alpha:** 16  
- **Dropout:** 0.05  
- **Quantization Bits:** 4-bit  
- **Optimizer:** AdamW with weight decay  
- **Evaluation Steps:** 50  
- **Warmup Ratio:** 0.1  

---

## Usage

### 1. Fine-Tuning the Model
1. Open the Colab notebook in your Google Drive.
2. Upload your law-based dataset in JSON format. Ensure the structure includes the fields:
    - `instruction`: The task instruction.
    - `input`: Contextual input text.
    - `output`: Expected response or output.
3. Run the notebook cells to:
    - Load the base Llama 3.1 8B model.
    - Apply QLoRA for fine-tuning.
    - Save the fine-tuned model.

### 2. Chatbot Implementation
- Deploy the chatbot using Gradio.
- Use the fine-tuned model for legal Q&A.
- Interact with the chatbot by typing queries related to legal topics.

### 3. PDF Reader Integration
- Upload PDF legal documents for analysis.
- Extract text using `PyPDF2`.
- Query extracted content through the chatbot for detailed insights.

---

## Dataset Preparation

Ensure your dataset follows the Llama 3.1 fine-tuning structure:

```json
[
  {
    "instruction": "Explain the significance of habeas corpus.",
    "input": "Consider its application in a recent case.",
    "output": "Habeas corpus is a legal principle ensuring..."
  },
  ...
]
