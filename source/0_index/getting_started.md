# Getting Started


## Installation 
Please check the [installation](installation.md) section to install editable HPC-FAIR transformers

## Pipelines

```{toctree}
:maxdepth: 0
:hidden:
../1_pipelines/similarity_checking.md
./1_pipelines/parallelism.md
```


The pipeline() is the easiest and fastest way to use a pretrained model for inference. You can use the pipeline() out-of-the-box for many tasks across different modalities, some of which are shown in the table below:


| Task                  | Pipeline identifier                      | Description                                                                 |
|-----------------------|------------------------------------------|-----------------------------------------------------------------------------|
| code summarization    | pipeline(task="code-summarization")      | Automatically generating a concise and comprehensive description of a given code snippet or function |
| code-to-code translation | pipeline(task="")                      | WIP                                                                         |
| defect detection      | pipeline(task="defect-detection")        | Identify whether a given code is an insecure code that may attack software systems  |
| [parallelism detection](../1_pipelines/parallelism.md) | pipeline(task="loop-parallelism")        | Predict parallelism within a given loop                                     |
| [similarity checking](../1_pipelines/similarity_checking.md)   | pipeline(task="code-similarity")         | Check if two codes have semantic similarity                                 |
| text-to-code generation | pipeline(task="")                      | WIP                                                                         |
               |



## Tokenizer
| Tokenizer      | Description | Pipeline identifier|       
| ----------- | ----------- | -----------               |
| ast-token    | token-based ast tokenizer      | 	pipeline(tokenizer=“ast-token”) |
| ast-graph   | graph-based ast tokenizer; works with GNNs only (WIP) |	pipeline(tokenizer=“ast-graph”) |
| programl | comprehensive graph tokenizer (WIP)        |	pipeline(tokenizer=“programl”) |