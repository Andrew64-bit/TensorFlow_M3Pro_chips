# TensorFlow_M3Pro_chips
This guide helps you setting up your environment in order to get full potential from your Apple Silicon M3 Pro chip 

## Steps
1. Install Homebrew from https://brew.sh.
2. Download Miniforge3 for macOS arm64 chips. Miniforge3 is a distribution of Conda, a package and environment manager for Python.
3. Install Miniforge3 into the home directory of your Macbook Pro, use the following commands:
  - Installation:
```bash
sh ~/Downloads/Miniforge3-MacOSX-arm64.sh
```
  - Activation of the Conda environment for the current Terminal session:
```bash
source ~/miniforge3/bin/activate
```
4. Create a new Directory for you project and access to it.
5. Initialize and activate the Conda environment for your project ( be sure to have activated miniforge3 Conda env for your current session before ):
```bash
conda create --prefix ./env python=3.8
```
```bash
conda activate ./env
```
7. Install TensorFlow dependencies from Apple Conda:
```bash
conda install -c apple tensorflow-deps
```
8. Install base TensorFlow:
```bash
python -m pip install tensorflow-macos
```
9. Install Apple’s tensorflow-metal to utilize the Apple Metal (Apple's GPU framework) for M3, M3 Pro, and M3 Max GPU access:
```bash
python -m pip install tensorflow-metal
```
10. Install data science packages:
```bash
conda install jupyter pandas numpy matplotlib scikit-learn
```
11. Start Jupyter Notebook:
```bash
jupyter notebook
```

12. Type the following code to check TensorFlow version/GPU access:
```python
import numpy as np
import pandas as pd
import sklearn
import tensorflow as tf
import matplotlib.pyplot as plt

# Check for TensorFlow GPU access
print(f"TensorFlow has access to the following devices:\n{tf.config.list_physical_devices()}")

# See TensorFlow version
print(f"TensorFlow version: {tf.__version__}")
```




