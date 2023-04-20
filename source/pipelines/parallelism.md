# Pipeline: Parallelism Detection
## Overview
The Parallelism Detection API is built on top of the Hugging Face Transformers library and utilizes a custom pre-trained model to predict whether parallelism exists within a given code snippet. The API provides a simple and efficient way to detect parallelism in code without manual inspection or using complex code analysis tools.

## Getting Started
To use the Parallelism Detection API, you will need to install the HPCFAIR Transformers library. Please refer to the [installation](../index/installation.md).

## Usage
### Importing the Library
First, you need to import the Hugging Face pipeline function:
```python
from transformers import pipeline
```
### Creating the Pipeline
Next, create an instance of the pipeline by providing the local path to the pre-trained model and specifying the task as "loop-paralelism"::
```python
pipe = pipeline(model="path/to/local/model", task="loop-paralelism")
```
You can also use different models by specifying their names in the model parameter. Ensure that the model is compatible with the "code-similarity" task.

### Using the API
To detect parallelism in a code snippet, pass the code as a string to the pipe instance:

```python
code = """
for (int i = 0; i < n; i++) {
    a[i] = b[i] + c[i];
}
"""

result = pipe(code)
```
The pipe instance will return a number, either 0 or 1, representing the prediction:

0: No parallelism detected
1: Parallelism detected
For example, given the code snippet above, the result variable might be 1 if parallelism is detected.

## Customizing the Pipeline
The Parallelism Detection API allows you to use different pre-trained models for the task. To use a different model, provide the path to the model directory when creating the pipeline instance:
```python
pipe = pipeline(model="path/to/another/local/model", task="loop-paralelism")
```
