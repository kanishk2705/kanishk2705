<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0F172A,100:2563EB&height=220&section=header&text=KANISHK&fontSize=70&fontColor=ffffff&fontAlignY=38&desc=AI%2FML%20%E2%80%A2%20Data%20Science%20%E2%80%A2%20Reliable%20Evaluation&descAlignY=60&descSize=20" width="100%"/>

<br>

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=21&duration=2800&pause=900&color=2563EB&center=true&vCenter=true&width=850&lines=Computer+Science+and+Engineering+Undergraduate;Honours+in+Data+Science;Building+ML+systems+that+are+honestly+evaluated;Leakage-safe+%E2%80%A2+Pre-registered+%E2%80%A2+Reproducible" alt="Typing SVG" />

<br><br>

<a href="https://kanishk2705.github.io/Portfolio/"><img src="https://img.shields.io/badge/Portfolio-111827?style=for-the-badge&logo=googlechrome&logoColor=white"/></a> <a href="https://www.linkedin.com/in/kanishk27"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/></a> <a href="mailto:kanishk.ac.official@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white"/></a> <a href="#-featured-projects"><img src="https://img.shields.io/badge/Projects-2563EB?style=for-the-badge&logo=github&logoColor=white"/></a>

</div>

<br>

---

# 👋 About Me

I'm **Kanishk**, a final-year **B.E. Computer Science and Engineering (Hons. in Data Science)** student at **Government College of Engineering, Tirunelveli**.

The part of computing that interests me most is the **mathematical and analytical side**: probability, statistics, and problems where there is something to understand beneath the surface rather than simply something to implement.

That interest led me to **Machine Learning and Data Science**, and to one question I keep coming back to:

> **Does this result actually hold up?**

So my projects follow a consistent pattern: write the evaluation protocol down before looking at the test data, check for leakage, compare against honest baselines, report confidence intervals, and publish the negative results along with the positive ones.

`Problem → Data → Leakage audit → Protocol → Model → Evaluation → Limitations`

---

# 🚀 Featured Projects

Five completed projects across NLP, computer vision, forecasting, data engineering and generative AI, each with a public repository, automated tests and a live demo or project page.

---

## 01 · Smart Resume Analyzer

**NLP · Sentence Embeddings · Explainable Scoring · Leakage Detection**

An explainable resume–job matching service (FastAPI backend + Streamlit client) that embeds both documents sentence by sentence with SBERT and scores them on four weighted, self-explaining components, with skill-gap analysis, ATS checks and an LLM coach.

Benchmarking on 8,000 labelled pairs revealed that **476 of 477 test resumes also appear in the training split**, so I added a leakage-safe unseen-resume protocol before comparing models.

- Fine-tuned SBERT (triplet loss) reaches **0.698** within-job AUC on unseen resumes, +0.093 over TF-IDF
- The same model scores **0.808** when resumes repeat; the gap is the size of the leakage
- 185 automated tests, CI on every push, public demo

`SBERT` `PyTorch` `FastAPI` `Streamlit` `Docker` `GitHub Actions`

[Repository](https://github.com/kanishk2705/Smart-Resume-Analyzer) · [Live Demo](https://smart-resume-analyzer-v2.streamlit.app)

---

## 02 · Plant Disease Classifier Reliability Study

**Computer Vision · Distribution Shift · Calibration · Selective Prediction**

A pre-registered study of what happens when classifiers trained on lab photos (PlantVillage) meet field photos (PlantDoc). It compares a scratch CNN with a pretrained ResNet-18 across 3 seeds, using leaf-group-aware splits and perceptual-hash de-duplication.

- Accuracy falls by about **83 percentage points** for both models
- The pretrained advantage was **not demonstrated** under the pre-set decision rule
- Temperature scaling **did not help** under shift; confidence separated right from wrong answers only weakly (AUROC 0.59–0.63)

`PyTorch` `torchvision` `Cluster Bootstrap` `229 tests`

[Repository](https://github.com/kanishk2705/plant-disease-reliability) · [Project Page](https://kanishk2705.github.io/plant-disease-reliability/)

---

## 03 · Residential Energy Forecasting Under Changing Conditions

**Time Series · Drift · Retraining Policies · Conformal Intervals**

A pre-registered evaluation of household electricity forecasts as conditions drift from winter into spring. I reformulated the UCI Appliances Energy data into true 10-minute, 1-hour and 1-day-ahead forecasting, and found and fixed a leakage source in the interpolated weather columns.

- LightGBM beats the best baseline by **15% / 11% / 3%** at the three horizons
- Weather inputs made day-ahead forecasts **34% worse** once temperatures left the training range
- Retraining helped only at 10 minutes; raw 80% intervals were already calibrated

`LightGBM` `scikit-learn` `Day-Block Bootstrap` `43 tests`

[Repository](https://github.com/kanishk2705/Residential-Energy-Forecasting) · [Project Page](https://kanishk2705.github.io/Residential-Energy-Forecasting/)

---

## 04 · Market Sentinel: Stock Market News Sentiment Analysis

**Data Engineering · Financial NLP · Walk-Forward Backtesting · App Security**

A multi-user market-intelligence app: a nightly pipeline collects prices and headlines, scores news with FinBERT and sends alerts; a Streamlit app shows technical charts and an LLM briefing, with Supabase Row-Level Security keeping each watchlist private.

A walk-forward backtest of **3,214 predictions** tested whether the forecast has real skill:

- **0 of 13** stocks beat a naive "tomorrow = today" forecast; direction accuracy 49.3–49.8% (coin flip)
- Switching from Random Forest on prices to Ridge on returns closed about **98%** of the error gap
- The app labels its forecast as experimental; 9/9 live RLS security checks pass

`FinBERT` `Supabase` `Streamlit` `Plotly` `GitHub Actions`

[Repository](https://github.com/kanishk2705/Stock-Market-News-Sentiment-Analysis) · [Live Demo](https://market-sentinel-news.streamlit.app/)

---

## 05 · AI Multi-Condition Patient Journey Assistant

**Generative AI · RAG · Grounded Generation · AI Safety**

A source-grounded assistant for people living with both asthma and type 2 diabetes. It answers only from 373 public health passages, cites a passage for every sentence, declines when the sources don't cover a question, and routes emergencies to fixed safety messages.

- Correct passage ranked first for **87%** of held-out questions, top five for **97%**
- Condition-aware retrieval did **not** beat plain semantic search; the gain came from the re-ranker
- Abstention gate AUROC **0.97**; 78% of answer sentences confirmed by an independent NLI checker

`Hybrid Search` `Cross-Encoder` `ONNX Runtime` `FastAPI` `Render`

[Repository](https://github.com/kanishk2705/AI-Multi-Condition-Patient-Journey-Assistant) · [Live Assistant](https://kanishk2705.github.io/AI-Multi-Condition-Patient-Journey-Assistant/app/)

---

# 🧰 Technology Stack

Only tools used in the projects above or in my internship.

<div align="center">

<img src="https://skillicons.dev/icons?i=python,javascript,postgres,pytorch,sklearn,fastapi,docker,git,github&theme=light" />

<br><br>

<img src="https://img.shields.io/badge/Sentence_Transformers-111827?style=flat-square"/>
<img src="https://img.shields.io/badge/Hugging_Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black"/>
<img src="https://img.shields.io/badge/LightGBM-111827?style=flat-square"/>
<img src="https://img.shields.io/badge/XGBoost-337AB7?style=flat-square"/>
<img src="https://img.shields.io/badge/ONNX_Runtime-005CED?style=flat-square&logo=onnx&logoColor=white"/>
<img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white"/>
<img src="https://img.shields.io/badge/Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white"/>
<img src="https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white"/>
<img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white"/>

</div>

---

# ⚙️ How I Approach Projects

| 📝 Pre-register | 🔍 Audit | 📊 Evaluate | 🧾 Report |
| :---: | :---: | :---: | :---: |
| Freeze the protocol and model choices before touching the test set | Look for leakage before trusting a number | Honest baselines, confidence intervals, negative controls | Publish what didn't work, with limitations stated |

> **Understanding over complexity.**
> **Credibility over buzzwords.**
> **Evaluation over demonstration.**

---

# 💼 Experience

### Machine Learning Intern · Pratinik Infotech, Pune (Remote)
`April 2026 – June 2026`

Selected through an online assessment. Built three end-to-end ML systems, each with a data pipeline, model, FastAPI service and Streamlit dashboard:

- **Predictive Maintenance:** 28 rolling-window sensor features, XGBoost 24-hour failure warning
- **Credit Card Fraud Detection:** SMOTE + LightGBM with tiered actions; traced a missed target to label noise in the data generator
- **NLP Support Ticket Triage:** NLTK + TF-IDF + LinearSVC with confidence-based routing and interpretable keyword drivers

---

# 🎓 Education

### B.E. Computer Science and Engineering (Hons. in Data Science)
**Government College of Engineering, Tirunelveli** (Autonomous, affiliated to Anna University) · `2023 – 2027`

**CGPA 8.31 / 10**

Relevant coursework: Statistics and Numerical Methods · Discrete Mathematics · Algorithms · Database Management Systems · Artificial Intelligence and Machine Learning · Exploratory Data Analysis · Big Data Analytics · Recommender Systems · Neural Networks and Deep Learning (ongoing)

---

# 🏆 Recognition

- **First Prize**, Techno Spark, NEC TECH FEST 2K25, National Engineering College (Mar 2025)
- **Second Prize**, Incognito Code, NEC TECH FEST 2K25, National Engineering College (Mar 2025)
- **Second Prize**, Code Debugging Master, Einsteinium 2K24, Einstein College of Engineering (Nov 2024)
- **Third Prize**, Tech Expo project showcase, Government College of Engineering, Tirunelveli (Oct 2025)
- Designed and hosted **Prompt Paradox**, a technical event with ~100 participants, at my college symposium in 2025 and 2026

---

# 🤝 Let's Connect

<div align="center">

<a href="https://kanishk2705.github.io/Portfolio/"><img src="https://img.shields.io/badge/Portfolio-111827?style=for-the-badge&logo=googlechrome&logoColor=white"/></a>
<a href="https://www.linkedin.com/in/kanishk27"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/></a>
<a href="mailto:kanishk.ac.official@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white"/></a>

<br><br>

### Building toward a deeper understanding of mathematics, data, and machine learning, one honestly evaluated project at a time.

</div>

<br>

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:2563EB,100:0F172A&height=120&section=footer"/>

</div>
