# Getting Started

## Requirements 
Please check the [installation](installation.md) section to install editable HPC-FAIR transformers. This repository is tested on Python 3.6+, Flax 0.3.2+, PyTorch 1.3.1+ and TensorFlow 2.3+.

## Pipelines

The pipeline() is the easiest and fastest way to use a pretrained model for inference. You can use the pipeline() out-of-the-box for many tasks across different modalities, some of which are shown in the table below:


| Task                  | Pipeline identifier                      | Description                                                                 |
|-----------------------|------------------------------------------|-----------------------------------------------------------------------------|
| code summarization    | pipeline(task="code-summarization")      | Automatically generating a concise and comprehensive description of a given code snippet or function |
| code-to-code translation | pipeline(task="")                      | WIP                                                                         |
| defect detection      | pipeline(task="defect-detection")        | Identify whether a given code is an insecure code that may attack software systems  |
| [parallelism detection](../pipelines/parallelism.md) | pipeline(task="loop-parallelism")        | Predict parallelism within a given loop                                     |
| [similarity checking](../pipelines/similarity_checking.md)   | pipeline(task="code-similarity")         | Check if two codes have semantic similarity                                 |
| text-to-code generation | pipeline(task="")                      | WIP                                                                         |



## Tokenizer
| Tokenizer      | Description | Pipeline identifier|       
| ----------- | ----------- | -----------               |
| ast-token    | token-based ast tokenizer      | 	pipeline(tokenizer=“ast-token”) |
| ast-graph   | graph-based ast tokenizer; works with GNNs only (WIP) |	pipeline(tokenizer=“ast-graph”) |
| programl | comprehensive graph tokenizer (WIP)        |	pipeline(tokenizer=“programl”) |