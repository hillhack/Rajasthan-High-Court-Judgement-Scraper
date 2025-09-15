# 🧑‍⚖️ Rajasthan High Court Judgement Scraper

Automates extraction of judgments from the [Rajasthan HC Filters](https://hcraj.nic.in/cishcraj-jdp/JudgementFilters/) portal using **Selenium + OCR (Tesseract + OpenCV)** to handle captchas.

<img width="2258" height="1073" alt="image" src="https://github.com/user-attachments/assets/a8138317-e2f7-4a61-befa-0f8ded05321a" />

---

## ⚙️ Setup

### Prerequisites

* **Google Chrome** + **ChromeDriver**
* **Tesseract OCR** → [install guide](https://github.com/tesseract-ocr/tesseract)

### Install Dependencies

```bash
git clone https://github.com/hillhack/Rajasthan-High-Court-Judgement-Scraper.git
cd Rajasthan-High-Court-Judgement-Scraper
pip install -r requirements.txt
```

(Or install manually: `selenium webdriver-manager requests beautifulsoup4 pillow opencv-python pytesseract numpy`)

---

## 🚀 Workflow

1. **WebDriver Setup**

   * Launches **headless Chrome** with Selenium.
   * Navigates to the Judgement Filter page.

2. **Captcha Handling**

   * Captcha images are detected (works with both **base64-encoded** and normal `<img>`).
   * Saved locally (`captcha.png`).
   * Preprocessed using **OpenCV** (grayscale + thresholding).
   * OCR with **Tesseract**, restricted to **digits only**.
   * If OCR fails → script shows captcha.png for **manual input fallback**.

3. **Form Filling**

   * Dates are set using **JavaScript injection** (faster than typing).
   * Options like *Reportable Judgment = Yes* are selected automatically.
   * Captcha (OCR/manual) is inserted into the form.

4. **Submission & Parsing**

   * Form is submitted.
   * Scraper extracts judgment list, parses details, and can download judgment text.

---

## ✅ Features Implemented in This Version

* Robust captcha saving (works with both `src=base64` and normal image).
* OpenCV preprocessing before OCR → improved accuracy.
* Tesseract configured for **digits only**.
* Fallback to manual captcha entry if OCR fails.
* Error handling for missing captcha or failed load.
* Modular code → easy to extend for scraping results.

---

Do you want me to also add a **future improvements section** (like using ML-based captcha solvers, storing results in DB, CLI args for dates), or should I keep it only to what’s already done?
