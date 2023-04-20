# Pipeline: Code Similarity
## Overview
The Code Similarity API is designed to compare the semantic similarity between two code snippets. It leverages the Hugging Face Transformers library and can be easily customized to use different models. The API receives two code snippets as input and returns a similarity score between 0 and 1, where 1 indicates high semantic similarity and 0 indicates low or no similarity.

## Getting Started
To use the Code Similarity API, you will need to install the HPCFAIR Transformers library. Please refer to the [installation](../index/installation.md).

## Usage
### Importing the Library
First, you need to import the Hugging Face pipeline function:
```python
from transformers import pipeline
```

### Creating the Pipeline
Next, create a pipeline for the "code-similarity" task, specifying the desired model. In this example, we are using the "bert-base-uncased" model:
```python
pipe = pipeline(model="bert-base-uncased", task="code-similarity")
```
You can also use different models by specifying their names in the model parameter. Ensure that the model is compatible with the "code-similarity" task.

### Using the API
To use the Code Similarity API, pass the two code snippets as a tuple to the pipe function:
```python
similarity_score = pipe((code_snippet1, code_snippet2))
```
similarity_score will be a float value between 0 and 1, representing the semantic similarity between the two code snippets.


## Example
Here's a complete example of using the Code Similarity API:
```python
from transformers import pipeline

# Create the pipeline
pipe = pipeline(model="bert-base-uncased", task="code-similarity")

# Define the code snippets
code_snippet1 = """
def add(a, b):
    return a + b
"""

code_snippet2 = """
def sum(a, b):
    return a + b
"""

# Get the similarity score
similarity_score = pipe((code_snippet1, code_snippet2))
print("Similarity Score:", similarity_score)
```

## Supported Models
The Code Similarity API is designed to work with a variety of models. To find a suitable model for the "code-similarity" task, please refer to the Hugging Face docs.

