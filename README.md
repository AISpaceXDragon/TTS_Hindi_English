# Fine-tuning Text-to-Speech (TTS) Models for English Technical Speech and Regional Languages

## Project Overview
This repository contains the solution for fine-tuning two Text-to-Speech (TTS) models. The project focuses on improving TTS model performance in two domains:
1. English technical speech (with a focus on technical jargon commonly used in interviews).
2. A regional language of your choice.

Additionally, optimization techniques such as quantization are explored to improve inference speed and reduce model size without significantly compromising audio quality.

# NOTE: 
1.  As an attempt to solve the third task/bonus task that is optimisation of the trained models, I wish to convey that I have tried to solve the task but due to some errors, the quantised model(quantised using post training static quantisation) is not able to generate the outputs. Given below is a link to the quantised model.

Quantised model link - https://huggingface.co/srimanth-d/Quantised_XTTS_Hindi/blob/main/quantized_xtts_model.pth (size is 1.99 GB, but this is one that doesn't load properly and doesn't produce any output when inferenced.)

Trimmed model link - https://huggingface.co/srimanth-d/Quantised_XTTS_Hindi/blob/main/trimmed_model.pth (size is 5.2 GB, which is less than the fine-tuned model weight i.e., 5.6 GB, this loads properly and produces output when inferenced.)

2.  Due to resource constraints for the task 1 I have only chose to fine tune the model on words CUDA and API that is around 6000 data points.


## Objectives
The key objectives of this project are:
1. **Fine-tune a TTS model for English technical terms**: Enhance the model's pronunciation of commonly used technical terms like "API," "CUDA,".
2. **Fine-tune a TTS model for a regional language**: Improve the model's ability to synthesize high-quality, natural-sounding speech in a regional language.
3. **Optimize model for fast inference**: Apply quantization techniques to speed up inference while maintaining output quality.

## Project Structure
The repository is structured as follows:

```
.
├── data/                 # Contains datasets used for fine-tuning (English and Regional Language)
├── models/               # Pre-trained and fine-tuned models
├── scripts/              # Python scripts for fine-tuning, evaluation, and optimization
├── results/              # Evaluation metrics and generated audio samples
├── README.md             # Project overview and details (this file)
└── final_report.pdf      # Detailed report of the project, including methodology, challenges, and results
```

## Task Breakdown

### 1. English TTS Fine-Tuning
- **Model Selection**: Coqui TTS is the base model.
- **Dataset**: Custom dataset with around 6k data points containing general English sentences and technical jargon.
- **Fine-Tuning**: Improve the pronunciation of technical terms.
- **Evaluation**: Used mel loss.
### 2. Regional Language TTS Fine-Tuning
- **Model Selection**: Coqui TTS is the base model.
- **Dataset**: Common Voice v19 hindi from hugging face, a dataset with natural language sentences covering a wide range of phonemes.
- **Fine-Tuning**: Improve the pronunciation, prosody, and stress patterns for the regional language.
- **Evaluation**: Used mel loss.

### 3. Fast Inference Optimization (Optional)
- **Quantization Techniques**: Apply techniques like Post-Training Quantization (PTQ) or Quantization-Aware Training (QAT) to reduce model size.
- **Inference Speed**: Optimize model for faster inference without degrading output quality.

## Setup and Usage
### Prerequisites
- Python 3.8+
- Install required dependencies by running:
  ```bash
  git clone https://github.com/idiap/coqui-ai-TTS
  cd coqui-ai-TTS
  pip install -e .
  ```

## Deliverables
- Fine-tuned models for both English technical terms and the regional language.
- Quantized models (optional).
- Generated audio samples for both pre-trained and fine-tuned models.
- Performance reports and evaluation logs.

## Resources
- [Coqui TTS Documentation](https://github.com/coqui-ai/TTS)
- [PyTorch Quantization Techniques](https://pytorch.org/docs/stable/quantization.html)

## Final Report
The final report detailing the steps, methodology, challenges, and results is available [here](Final_report.pdf).
