# 🧠 Setting Up TensorFlow 2.10 GPU on Windows with Anaconda (Tested on RTX 4070 SUPER)

> ⚠️ **Important Note:**  
> TensorFlow 2.10 is the **last version** that supports **native GPU acceleration on Windows (without WSL)**.  
> For TensorFlow versions **above 2.10**, you must use **Windows Subsystem for Linux (WSL2)** for GPU support.

This guide walks you through installing **TensorFlow 2.10 with GPU support** using **Anaconda** on **Windows**, tested with an **NVIDIA RTX 4070 SUPER**.

---

## ✅ Prerequisites

- Windows 10 or 11 (64-bit)
- An NVIDIA GPU with CUDA support:
  - ✅ RTX 30 series (Ampere)
  - ✅ RTX 40 series (Ada Lovelace)
  - ⚠️ RTX 50 series: Use WSL2 + TensorFlow ≥ 2.15 instead
- Latest NVIDIA GPU drivers installed
- [Anaconda](https://www.anaconda.com/products/distribution) installed

---

## 🧪 Step 1: Create an Anaconda Environment

1. Open **Anaconda Navigator**.
2. Go to the **Environments** tab.
3. Click **Create**:
   - **Name:** `tf210` (Name it whatever you want)
   - **Python version:** `3.8.20` (or any `3.8.x`)
4. Click **Create** to confirm.

---

## 📦 Step 2: Install Basic Packages (Optional if you have Jupyter Notebookn already installed)

1. In the **`tf210` environment**, switch the filter dropdown to **Not Installed**.
2. Search for and check the following package:
   - `notebook`
3. Click **Apply** to install.

---

## ⚙️ Step 3: Install CUDA Toolkit and cuDNN

1. In Anaconda Navigator, click the ▶️ next to `tf210` and select **Open Terminal**.
2. Run the following command:

```bash
conda install -c conda-forge cudatoolkit=11.2 cudnn=8.1
```

---

## 🎯 Step 4: Installing TensorFlow

Run in terminal

```bash
pip install tensorflow==2.10
```

---

## 🧪 Step 5: Test GPU & Run Benchmark (Jupyter Notebook)

To verify that everything is working, you can run the included notebook or copy the code from it:  
**`Tests & Benchmark.ipynb`**

### 🧾 What's Inside

- **Code Cell 1–2:** Checks if TensorFlow detects your GPU correctly  
- **Code Cell 3-4:** Benchmarks matrix multiplication performance on CPU vs GPU

> 💡 The uploaded notebook includes sample output so you can preview what to expect.

---

## 🔌 Optional Step: Install Common ML & NLP Packages to Expand Workflow

### TensorFlow (already installed in Step 4)
```bash
pip install tensorflow==2.10
```

### Common ML & data visualization libraries
```bash
pip install pandas scikit-learn seaborn matplotlib tqdm
```

### Image handling
```bash
pip install pillow opencv-python
```

### NLP and Transformers
```bash
pip install nltk transformers
```

### spaCy (use binary wheels to avoid compilation errors)
```bash
pip install spacy --prefer-binary
```

---

## 🎉 You're All Set!

You now have **TensorFlow 2.10 with native GPU support** running on Windows — no WSL required.

If the benchmark ran successfully and your GPU was detected, congratulations! 🎉  
You're ready to start building and accelerating deep learning models.

---
