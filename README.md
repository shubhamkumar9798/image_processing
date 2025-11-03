# 🧠 Digital Image Processing and Analysis Pipeline

**Author:** Shubham Kumar  
**Reg. No:** 3122235001127  
**Department:** Computer Science and Engineering, CSE-C  
**Institution:** SSN College of Engineering, Tamil Nadu, India  

---

## 📘 Overview

This project presents a **complete digital image processing pipeline** — from image acquisition to preprocessing, noise simulation, and denoising — with quantitative and qualitative analysis using **PSNR** and **SSIM** metrics.

It demonstrates how different filtering techniques perform under various noise conditions, emphasizing practical trade-offs in real-world image enhancement tasks.

---

## 🧩 Pipeline Stages

### 1. **Image Acquisition**
- Captured a natural indoor image (study desk) using a smartphone.  
- Selected scene provides:
  - Balanced lighting conditions  
  - Diverse textures (smooth laptop surface, rough notebook, fine text)  
  - Real-world relevance for evaluating noise and filtering techniques  

---

### 2. **Noise Simulation**
Simulated two types of noise to evaluate robustness of denoising filters:
- **Gaussian Noise:** Models random sensor noise.  
  Formula:  
  \[
  I'(x, y) = I(x, y) + n(x, y), \quad n \sim N(0, σ^2)
  \]
- **Salt-and-Pepper Noise:** Simulates impulse errors (0 or 255 pixel corruption).  
  \[
  I'(x, y) =
  \begin{cases}
  0 & \text{with prob. } p/2 \\
  255 & \text{with prob. } p/2 \\
  I(x, y) & \text{with prob. } 1-p
  \end{cases}
  \]

---

### 3. **Preprocessing and Enhancement**
Steps performed before applying filters:
- **Grayscale Conversion:**  
  \[
  I_{gray} = 0.299R + 0.587G + 0.114B
  \]
- **Resizing:** Standardized to **256 × 256** pixels.
- **Histogram Equalization:** Enhanced contrast for better visibility.  
  \[
  s_k = (L - 1)\sum_{j=0}^{k}p_r(r_j)
  \]

---

### 4. **Noise Filtering and Denoising**
Applied and compared three filters:

| Filter Type | Description | Key Advantage |
|--------------|--------------|----------------|
| **Median Filter** | Replaces each pixel with median of its neighborhood | Excellent for impulse (Salt & Pepper) noise |
| **Gaussian Filter** | Weighted averaging with Gaussian kernel | Smooths noise but may blur edges |
| **Bilateral Filter** | Combines spatial & intensity similarity | Preserves edges while smoothing |

**Gaussian Kernel Formula:**
\[
G(x, y) = \frac{1}{2πσ^2}e^{-\frac{x^2 + y^2}{2σ^2}}
\]

---

### 5. **Evaluation Metrics**
Quantitative comparison using **PSNR** and **SSIM**.

\[
PSNR = 10 \log_{10} \left( \frac{MAX_I^2}{MSE} \right)
\]
\[
SSIM(x, y) = \frac{(2μ_xμ_y + c_1)(2σ_{xy} + c_2)}{(μ_x^2 + μ_y^2 + c_1)(σ_x^2 + σ_y^2 + c_2)}
\]

| Filter | PSNR (dB) | SSIM |
|:-------|:----------:|:----:|
| Median | **28.5** | **0.82** |
| Gaussian | 26.9 | 0.79 |
| Bilateral | **30.1** | **0.85** |

---

## 📊 Results and Analysis
- **Median filter** performed best for **Salt-and-Pepper noise**.  
- **Bilateral filter** balanced smoothing and edge preservation well for **Gaussian noise**.  
- **Gaussian filter** improved visual smoothness but blurred edges slightly.

Visual results matched numerical evaluation, proving **no single filter works best for all noise types**.

---

## 🧠 Conclusion
The project successfully demonstrates:
- Image acquisition and preprocessing techniques  
- Noise modeling and removal  
- Quantitative evaluation using PSNR and SSIM  

In future, advanced denoising methods such as **Non-Local Means** and **Deep Learning-based** approaches can be integrated for improved results.

---

## 📚 References
1. R. C. Gonzalez and R. E. Woods, *Digital Image Processing*, 4th Edition, Pearson, 2018.  
2. J. Mukhopadhyay and A. Chanda, *Medical Image Processing and Analysis*, Springer, 2018.

---

## ⚙️ Tools Used
- Python (NumPy, OpenCV, Matplotlib)
- Jupyter Notebook / Google Colab
- Smartphone camera for image acquisition

---

## 🧾 Author
**Name:** Shubham Kumar  
**Reg No:** 3122235001127  
**Course:** B.E. – Computer Science and Engineering (CSE-C)  
**Institution:** SSN College of Engineering

