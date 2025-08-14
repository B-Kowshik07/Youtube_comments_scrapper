
---

# 📢 YouTube Comment Extractor & Sentiment Analyzer

A **Streamlit** app that can:

* Pull comments from YouTube videos 📥
* Automatically tag them as **Good** or **Bad** using **Google Gemini AI (1.5 Pro)** 🤖
* Save the labeled data as a CSV 📄

---

## 🌟 What It Does

* Fetches **top 3 comments** from any YouTube video (via **Selenium**)
* Uses Gemini AI to label each as:

  * **Good** → Positive or neutral
  * **Bad** → Offensive, negative, or abusive
* Displays results in a clean **Streamlit interface**
* Lets you download the final dataset as CSV

---

## 📋 Prerequisites

* **Python** 3.7 or newer
* **Google Gemini API Key** → [Get one here](https://makersuite.google.com/app)
* Google Chrome + compatible [ChromeDriver](https://chromedriver.chromium.org/downloads)

---

## ⚙️ Installation

1️⃣ Install dependencies:

```bash
pip install streamlit selenium pandas google-generativeai
```

2️⃣ Project file layout:

```
.
├── app.py                   # Streamlit application
├── chromedriver.exe         # Needed for Selenium
├── sample.csv               # Example scraped comments
├── labeled_comments.csv     # Output after classification
└── README.md
```

---

## 🔑 Configuration

* Open `app.py` and replace the placeholder API key with yours:

```python
genai.configure(api_key="YOUR_ACTUAL_API_KEY")
```

* Place the correct `chromedriver.exe` in the root folder (matching your Chrome version).

---

## ▶️ Run the App

```bash
streamlit run app.py
```

---

## 🖼 Example Dashboard

| Author     | Comment                     | Sentiment |
| ---------- | --------------------------- | --------- |
| John Doe   | This video is amazing!      | Good      |
| Jane Smith | Waste of time. Don’t watch. | Bad       |

---

## 🧠 How It Classifies

For each comment, Gemini AI receives this instruction:

> "Classify this comment as either Good (positive/neutral) or Bad (negative/offensive/abusive). Only return 'Good' or 'Bad'."

---

## 📂 Output

After processing, `labeled_comments.csv` contains:

| Author     | Comment                     | Sentiment |
| ---------- | --------------------------- | --------- |
| John Doe   | This video is amazing!      | Good      |
| Jane Smith | Waste of time. Don’t watch. | Bad       |

---

## ⚠️ Important Notice

This app uses automated scraping, which could breach YouTube’s Terms of Service. Use it only for **learning and research** purposes.

---

## 🙏 Credits

* [Streamlit](https://streamlit.io/)
* [Google Gemini AI](https://ai.google.dev/)
* [Selenium](https://www.selenium.dev/)

---

