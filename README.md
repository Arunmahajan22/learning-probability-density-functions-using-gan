# 📊 Learning Probability Density Functions using GAN

## 📌 Overview

This project focuses on learning an **unknown probability density function (PDF)** directly from data using a **Generative Adversarial Network (GAN)**.

Instead of assuming any predefined distribution (like Gaussian or Exponential), the model **learns the distribution purely from samples**, making it a fully **data-driven approach**.

---

## 🎯 Objective

* Transform a real-world feature into a new random variable
* Learn its unknown distribution using GAN
* Estimate the probability density function from generated samples

---

## 📂 Dataset

* **Source:** Air Quality Dataset (India)
* **Feature Used:** NO₂ (Nitrogen Dioxide concentration)

The dataset contains real-world pollution measurements, making it suitable for probabilistic modeling.

---

## ⚙️ Methodology

### 1. Data Preprocessing

* Removed missing values
* Standardized the feature using `StandardScaler`

---

### 2. Transformation

Each data point ( x ) is transformed into a new variable ( z ) using:

[
z = x + a_r \sin(b_r x)
]

where:

* ( a_r = 0.5 \times (r \mod 7) )
* ( b_r = 0.3 \times (r \mod 5 + 1) )
* ( r ) = University Roll Number

---

### 3. GAN Architecture

#### 🔹 Generator

* Input: Random noise ( \sim N(0,1) )
* Fully connected neural network
* Output: Synthetic samples resembling real data

#### 🔹 Discriminator

* Binary classifier
* Distinguishes between real and generated samples

---

### 4. Training Process

* Generator tries to **fool the discriminator**
* Discriminator learns to **identify real vs fake samples**
* Both networks improve through adversarial training

---

### 5. PDF Estimation

After training:

* Generated large number of samples
* Estimated PDF using:

  * Histogram Density
  * Kernel Density Estimation (KDE)

---

## 📈 Results

* The GAN successfully learned the underlying distribution
* Generated samples closely matched real data
* KDE plots showed strong overlap between real and generated distributions

---

## 📊 Observations

### 🔹 Mode Coverage

The model captures major modes but may slightly miss minor peaks.

### 🔹 Training Stability

Training is generally stable with minor oscillations in loss.

### 🔹 Quality of Generated Distribution

Generated samples closely approximate the true distribution.

---

## 🛠️ Tech Stack

* Python
* PyTorch
* NumPy
* Pandas
* Matplotlib & Seaborn
* Scikit-learn
* SciPy

---

## 🚀 How to Run

```bash
# Clone the repository
git clone https://github.com/your-username/learning-pdf-using-gan.git

# Open in Google Colab or Jupyter Notebook
# Upload dataset to /content/
# Run all cells
```

---

## 📌 Output

* Transformed data visualization
* GAN training logs
* Estimated PDF (Histogram + KDE)
* Real vs Generated comparison

---

## 📎 Future Improvements

* Use **Wasserstein GAN (WGAN)** for better stability
* Improve mode coverage
* Extend to multi-dimensional distributions

---

## 👨‍💻 Author

**Arun Mahajan**

---

## ⭐ Acknowledgment

This project is part of a machine learning assignment on **data-driven probability density estimation using GANs**.
