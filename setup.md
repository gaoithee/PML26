# 📂 `pml26_env` setup guide (Python 3.12)

This guide will walk you through setting up a clean, isolated Python 3.12 environment to run the notebooks and scripts in the **PML26** repository.

## 📋 Prerequisites

* **Conda** (Miniconda or Anaconda) is **highly recommended** for this repo to avoid system library conflicts.
* Alternatively, a working installation of **Python 3.12**.

---

## 🛠️ Step-by-Step Installation

1. **Create the environment:**
```bash
conda create -n pml26_env python=3.12 -y

```

2. **Activate it:**
```bash
conda activate pml26_env

```

3. **Install or update dependencies:**
```bash
pip install -r requirements.txt

```

---

## 📓 Using the Environment in Jupyter

To ensure your Jupyter Notebooks use the libraries installed in your environment, you must register it as a kernel:

1. With the environment **activated**, run:
```bash
pip install ipykernel
python -m ipykernel install --user --name=pml26_env --display-name "PML26 (Python 3.12)"

```


2. Open your notebook: `jupyter notebook`
3. In the Jupyter interface, go to **Kernel > Change Kernel** and select **"PML26 (Python 3.12)"**.

---

## ⏹️ Deactivation

When you're finished working, simply type:

```bash
# For Conda
conda deactivate

# For venv
deactivate

```

---

### ⚠️ Troubleshooting

* **Broken System Python:** If you work with `venv`s and see `ModuleNotFoundError: No module named 'encodings'`, your system's Python 3.12 installation is incomplete. You can switch to `conda` installation to avoid this issue.
* **PyTorch & GPU:** If you have an NVIDIA GPU, the standard `pip install` might only install the CPU version. Visit [pytorch.org](https://pytorch.org/) for the specific CUDA-enabled command.
* **Windows C++ Tools:** If `pip install` fails on packages like `scipy`, you may need the [Microsoft Visual C++ Build Tools](https://www.google.com/search?q=https://visualstudio.microsoft.com/visual-cpp-build-tools/).

---
