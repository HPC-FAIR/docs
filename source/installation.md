# Installation
## editable Hugging Face Transformers installation
```bash
git clone https://github.com/huggingface/transformers.git
cd transformers
pip install -e .
```

## dependencies installation

```bash
# tensorflow for linux
conda install -c conda-forge cudatoolkit=11.8.0
python3 -m pip install nvidia-cudnn-cu11==8.6.0.163 tensorflow==2.12.*
mkdir -p $CONDA_PREFIX/etc/conda/activate.d
echo 'CUDNN_PATH=$(dirname $(python -c "import nvidia.cudnn;print(nvidia.cudnn.__file__)"))' >> $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CONDA_PREFIX/lib/:$CUDNN_PATH/lib' >> $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
source $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
# Verify install:
python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"

# tensorflow for MacOS
# There is currently no official GPU support for MacOS.
python3 -m pip install tensorflow
# Verify install:
python3 -c "import tensorflow as tf; print(tf.reduce_sum(tf.random.normal([1000, 1000])))"


# Pytorch for Linux
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118

# Pytorch for MacOS
# MPS acceleration is available on MacOS 12.3+
pip3 install torch torchvision torchaudio
```