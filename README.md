
# 📄 PDF Q&A Bot with Quantized Open-Source LLMs

This Google Colab notebook implements a complete workflow for building an AI-powered document assistant. It leverages the Hugging Face ecosystem to load large language models (LLMs) in 4-bit quantization, allowing them to run efficiently on a single T4 GPU.

## 🚀 Key Features

*   **PDF Text Extraction:** Uses `pypdf` to parse and extract text from research papers or documents.
*   **Quantized Inference:** Employs `bitsandbytes` (4-bit quantization) to fit high-parameter models (like Llama 3.2 or Phi-4) into limited VRAM.
*   **Dynamic Model Switching:** A custom memory management system that clears VRAM and swaps models without restarting the runtime.
*   **Gradio Interface:** A user-friendly UI for selecting models, asking questions, and viewing generated answers.

## 🛠️ Setup Instructions

1.  **Select a GPU Runtime:** Go to `Runtime > Change runtime type` and ensure 'T4 GPU' (or higher) is selected.
2.  **Hugging Face Login:** You will need a Hugging Face token. Some models (like Llama) require you to accept their license terms on the Hugging Face Hub first.
3.  **Run All Cells:** The notebook is structured sequentially. Ensure Section 1 (Installations) and Section 2 (Setup) are completed before launching the UI.

## 📂 Project Structure

*   **Setup & Libraries:** Installation of `transformers`, `accelerate`, and `bitsandbytes`.
*   **Inference Logic:** Demonstration of `.generate()` vs. `pipeline()` methods.
*   **PDF Processing:** Downloading and reading PDF content.
*   **Q&A Engine:** Prompt engineering for RAG (Retrieval-Augmented Generation) style responses.
*   **UI Layer:** Gradio Blocks implementation for an interactive web-app experience.

## ⚠️ Limitations

*   **Context Window:** Currently limited to ~6000 characters to prevent memory overflow.
*   **VRAM:** Switching between large models frequently can sometimes lead to fragmentation; if a 'CUDA Out of Memory' occurs, please restart the runtime.
