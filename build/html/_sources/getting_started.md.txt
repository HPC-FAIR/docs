# Getting Started


## editable install Hugging Face Transformers from source 
Before you begin, make sure you have all the necessary libraries installed:
```bash
git clone https://github.com/huggingface/transformers.git
cd transformers
pip install -e .
```

# Pipeline
The pipeline() is the easiest and fastest way to use a pretrained model for inference. You can use the pipeline() out-of-the-box for many tasks across different modalities, some of which are shown in the table below:

| Task      | Description | Pipeline identifier|       
| ----------- | ----------- | -----------               |
| defect detection      | identify whether a given code is an insecure code that may attack software systems       | 	pipeline(task=“defect-detection”) |
| code summarization   | automatically generating a concise and comprehensive description of a given code snippet or function        |	pipeline(task=“code-summarization”) |
| code-to-code translation   | WIP        |	pipeline(task=“”) |
| text-to-code generation   | WIP        |	pipeline(task=“”) |
| parallelism detection   | predict parallelism within a given loop        |	pipeline(task=“loop-parallelism”) |
| similarity checking    | check if two codes have semantic similarity       |	pipeline(task=“code-similarity”) |
| code summarization   | WIP        |	pipeline(task=“”) |
| question answer   | answering question with ChatGPT 3.5        | pipeline(task=“chatgpt”) |
| code summarization   | Text        |
| code summarization   | Text        |
| code summarization   | Text        |


# Tokenizer
| Tokenizer      | Description | Pipeline identifier|       
| ----------- | ----------- | -----------               |
| ast-token    | token-based ast tokenizer      | 	pipeline(tokenizer=“ast-token”) |
| ast-graph   | graph-based ast tokenizer; works with GNNs only (WIP) |	pipeline(tokenizer=“ast-graph”) |
| programl | comprehensive graph tokenizer (WIP)        |	pipeline(tokenizer=“programl”) |