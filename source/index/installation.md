# Installation
## HPCFAIR Transformers editable installation
```bash
git clone git@github.com:HPC-FAIR/transformers.git
cd transformers
pip install -e .
```

## Software dependencies installation

HPC-FAIR API is built on top of HuggingFace libraries. These libraries provide models, datasets and so on that should be used with PyTorch or Tensorflow. You should install either of these two packages or both to use our API. 

### Pytorch

PyTorch is a Python package for deep learning using GPUs and CPUs. It provides two high-level features: Tensor computation with strong GPU acceleration and deep neural networks built on a tape-based autograd system.

Installation for Linux
```bash
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
```
Installation for MacOS
```bash
## MacOS: MPS acceleration is available on MacOS 12.3+
pip3 install torch torchvision torchaudio
```
verify Pytorch install:
```bash
python3 -c "import torch; print(torch.__version__)"
```

### Tensorflow

TensorFlow is an end-to-end open-source platform for machine learning that provides a comprehensive, flexible ecosystem of tools, libraries, and community resources.

Installation for Linux
```bash
conda install -c conda-forge cudatoolkit=11.8.0
python3 -m pip install nvidia-cudnn-cu11==8.6.0.163 tensorflow==2.12.*
mkdir -p $CONDA_PREFIX/etc/conda/activate.d
echo 'CUDNN_PATH=$(dirname $(python -c "import nvidia.cudnn;print(nvidia.cudnn.__file__)"))' >> $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CONDA_PREFIX/lib/:$CUDNN_PATH/lib' >> $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
source $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
```
Installation for MacOS
```bash
## MacOS: There is currently no official GPU support for MacOS.
python3 -m pip install tensorflow
```

verify tensorflow install:
```bash
python3 -c "import tensorflow as tf; print(tf.reduce_sum(tf.random.normal([1000, 1000])))"
```

