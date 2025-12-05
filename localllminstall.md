# Run Llama Locally as a Private LLM — Full Offline Setup Guide

This guide shows you how to **install and run Meta Llama-3.2-3B-Instruct locally**, fully private, **no data uploaded** during inference.



---

## Requirements

- OS: Windows / macOS / Linux
- Python: **3.9 or newer** (3.10 recommended)
- GPU optional  
  - NVIDIA GPU 6GB+ VRAM recommended for good speed  
  - CPU also works (just slower)

> All inference happens **on your machine**.

---
## Get permission of Downloading Llama
### 1.1 Go to huggingface website, create an account and log in.
### 1.2 Go to the llama page to submit permission for access of viewing the llama repository.

https://huggingface.co/meta-llama/Llama-3.2-3B

![alt text](<截屏2025-12-04 20.10.38.png>)
![alt text](<截屏2025-12-04 20.13.28.png>)

You should be able to get a respond email a few minutes later regarding permitting your access to the model.

---
## Create a Virtual Environment (optional but recommended)

```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS / Linux
source .venv/bin/activate
```


## Install Dependencies
### 2.1 upgrade pip
```bash
pip install --upgrade pip
```
### 2.2 Install PyTorch
If you have an NVIDIA GPU:

```bash
pip install torch --index-url https://download.pytorch.org/whl/cu121
```

If you only have CPU:

```bash
pip install torch
```
### 2.3 Install Transformers and others

```bash
pip install "transformers>=4.45.0" accelerate bitsandbytes huggingface-hub
```

### 2.4 Download the huggingface mode
In cmd:
```bash
huggingface-cli login
```

Go to https://huggingface.co/settings/tokens

Create a **Read** token

Paste it in the terminal

![alt text](<截屏2025-12-04 20.49.41.png>)

![alt text](<截屏2025-12-04 20.32.56.png>)
You can go offline after download.

## Run the llama
See the codes in the .ipynb file