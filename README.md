# 🧑‍⚖️ High Court Judgement Scraper (with Captcha OCR)

This project automates data extraction from the **Rajasthan High Court Judgement Filters** website (`https://hcraj.nic.in/cishcraj-jdp/JudgementFilters/`).

Since the site is protected with captchas, the script combines **Selenium** (for form automation) with **OCR (Tesseract + OpenCV)** to detect and read captcha images automatically.

---

## ⚙️ Requirements

Make sure you have the following installed:

* Google Chrome + [ChromeDriver](https://chromedriver.chromium.org/)
* Tesseract OCR engine ([Installation guide](https://github.com/tesseract-ocr/tesseract))

### Python Libraries

Install required dependencies:

```bash
pip install selenium webdriver-manager requests beautifulsoup4 pillow opencv-python pytesseract numpy
```

---

## 🚀 How It Works

The workflow is divided into steps:

### 1. **Setup WebDriver**

We use Selenium to launch Chrome in **headless mode** (no visible browser window).

### 2. **Navigate to Target Page**

### 3. **Locate & Save Captcha**

Captchas may be loaded as **Base64 images** or normal images.

### 4. **Preprocess Captcha with OpenCV**

To improve OCR accuracy, we apply **grayscale + thresholding**.

### 5. **OCR with Tesseract**

We configure Tesseract to only recognize **digits (0-9)** since this captcha is numeric.

### 6. **Fill the Form**

Dates and options are filled using JavaScript + Selenium.

### 7. **Submit the Form**
