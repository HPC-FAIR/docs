# API Reference
## Pipelines for inference
The pipeline() makes it simple to use any model from the Hub for inference on various PLP. Even if you don’t have experience with a specific modality or aren’t familiar with the underlying code behind the models, you can still use them for inference with the pipeline().

### Pipeline() usuage in general
While each task has an associated pipeline(), it is simpler to use the general pipeline() abstraction which contains all the task-specific pipelines. The pipeline() automatically loads a default model and a preprocessing class capable of inference for your task.
1. Start by creating a pipeline() and specify an inference task:
```python
from transformers import pipeline

similarity_checker = pipeline(task="code-similarity")
```

2. Pass your input text to the pipeline():
```python
similarity_checker(code1, code2)
```

### HPCFAIR Pipelines

```{toctree}
:maxdepth: 0
:hidden:
../pipelines/similarity_checking.md
../pipelines/parallelism.md
```

- code summarization 
- code-to-code translation
- defect detection
- [parallelism detection](../pipelines/parallelism.md)
- [similarity checking](../pipelines/similarity_checking.md)
- text-to-code generation
- OpenAI

