# Tuned-GPT-2-on-FineWeb-EDU-with-PyTorch

Exploring the inner workings of transformer-based language models by creating a GPT-2 clone referencing the original GPT-2 paper, using 300M tokens from the FineWeb-EDU dataset. This repository documents my journey in building, training, and evaluating a generative language model using PyTorch.

##  Project Overview

This project demonstrates:
- Preprocessing large-scale educational text data.
- Creating a GPT-2 architecture from scratch.
- Efficient training using GPU acceleration and PyTorch.
- Logging experiments and checkpoints.

##  Dataset: FineWeb-EDU

[FineWeb-EDU](https://huggingface.co/datasets/HuggingFaceFW/fineweb-edu-small) is a filtered subset of web-crawled data focusing on high-quality, educational content. This ensures a more informative and focused language model.

## 🛠 Technologies Used

- **Python 3.10+**
- **PyTorch**
- **Hugging Face Datasets**
- **Accelerate (for training)**
- **Jupyter Notebook (for prototyping and experimentation)**

## 🧪 What I Learned

Through this project, I deepened my understanding of:
- Tokenization and text encoding using Byte-Pair Encoding (BPE).
- The architecture and inner mechanics of GPT-2:
  - GPT-2 uses a **decoder-only Transformer** (unlike the original encoder-decoder structure in *Attention Is All You Need*).
  - It **removes cross-attention** entirely, focusing solely on masked self-attention for autoregressive language modeling.
  - The model employs **causal (unidirectional) attention**, enabling it to predict the next token based only on past tokens.
  - GPT-2 applies **pre-layer normalization**, where layer normalization is moved to the input of each sub-block, improving training stability.
  - I studied the differences between GPT-style architectures and the original Transformer design, gaining insight into how simplifications in GPT favor generation tasks.
- Using Accelerator to simplify multi-GPU/CPU training.
- Generating meaningful completions using temperature sampling and top-k filtering.


##  Future Work

- Implement checkpoint saving and resume training.
- Fine-tune with different data subsets (e.g., science, math).
- Integrate evaluation metrics like perplexity or BLEU.
- Try accelerated training using **multiple GPUs** and **parallelization** techniques to improve efficiency and reduce training time.


##  Credits

This project was heavily inspired by the excellent series by **Andrej Karpathy** on building and understanding GPT models from scratch:

 [Zero to Hero - GPT Playlist](https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhRvKZ)
