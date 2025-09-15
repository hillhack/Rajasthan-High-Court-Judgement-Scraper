# 🧑‍⚖️ Rajasthan High Court Judgement Scraper

Automates extraction of judgments from [Rajasthan HC Filters](https://hcraj.nic.in/cishcraj-jdp/JudgementFilters/) using **Selenium + OCR (Tesseract + OpenCV)** to bypass captchas.

---

## ⚙️ Setup

### Requirements

* **Google Chrome + ChromeDriver**
* **Tesseract OCR** ([install guide](https://github.com/tesseract-ocr/tesseract))

### Install Dependencies

```bash
git clone https://github.com/hillhack/Rajasthan-High-Court-Judgement-Scraper.git
cd Rajasthan-High-Court-Judgement-Scraper
pip install -r requirements.txt
```

(or install manually: `selenium webdriver-manager requests beautifulsoup4 pillow opencv-python pytesseract numpy`)

---

## 🚀 Workflow

1. Launch Chrome via Selenium (headless).
2. Navigate to the Judgement Filter page.
3. Capture captcha → preprocess (grayscale + threshold).
4. OCR with **Tesseract** (digits only).
5. Auto-fill form (dates, options, captcha).
6. Submit → parse results → download judgments.

