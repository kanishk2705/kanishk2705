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

That interest led me to **Machine Learning and Data Science**, and specifically to one question I keep coming back to:

> **Does this result actually hold up?**

So my projects follow a consistent pattern. I write the evaluation protocol down before I look at the test data, check for leakage, compare against honest baselines, report confidence intervals, and publish the negative results along with the positive ones.

`Problem → Data → Leakage audit → Protocol → Model → Evaluation → Limitations`

---

# 🚀 Featured Projects

Four completed studies, each in a different area, each with a public repository, automated tests and a project page.

---

## 01 · Smart Resume Analyzer

**NLP · Sentence Embeddings · Explainable Scoring · Leakage Detection**

An explainable resume–job matching service (FastAPI backend + Streamlit client) that embeds resumes sentence by sentence with SBERT and scores them on four self-explaining components.

Benchmarking it on 8,000 labelled pairs revealed that **476 of 477 test resumes also appear in the training split**. I added a leakage-safe unseen-resume protocol before comparing keyword, embedding, feature-based and fine-tuned models.

- Fine-tuned SBERT (triplet loss) reaches **0.698** within-job AUC on unseen resumes, vs **0.606** for TF-IDF
- The same model scores **0.808** under the leaky protocol; the gap is the size of the leakage
- 223 automated tests, CI on every push, public demo with per-visitor rate limits

`SBERT` `PyTorch` `FastAPI` `Streamlit` `Docker` `GitHub Actions`

[Repository](https://github.com/kanishk2705/Smart-Resume-Analyzer) · [Live Demo](https://smart-resume-analyzer-v2.streamlit.app)

---

## 02 · Plant Disease Classifier Reliability Study

**Computer Vision · Distribution Shift · Calibration · Selective Prediction**

A pre-registered study of what happens when plant-disease classifiers trained on lab photos (PlantVillage) meet field photos (PlantDoc). It compares a scratch CNN with a pretrained ResNet-18 across 3 seeds, with leaf-level splits so the same leaf never appears in two splits.

- Accuracy falls by about **83 percentage points** for both models (≈0.99 → ≈0.15)
- The pretrained advantage was **not demonstrated** under the pre-set decision rule
- Temperature scaling **did not help** under shift; confidence-based abstention separated right from wrong answers only weakly

`PyTorch` `torchvision` `Cluster Bootstrap` `229 tests`

[Repository](https://github.com/kanishk2705/plant-disease-reliability) · [Project Page](https://kanishk2705.github.io/plant-disease-reliability/)

---

## 03 · Residential Energy Forecasting Under Changing Conditions

**Time Series · Drift · Retraining Policies · Conformal Intervals**

A pre-registered evaluation of household electricity forecasts as conditions drift from winter into spring. I reformulated the UCI Appliances Energy data into true 10-minute, 1-hour and 1-day-ahead forecasting, and found and fixed a leakage source in the interpolated weather columns.

- LightGBM beats the best baseline by **15% / 11% / 3%** at the three horizons
- Extra sensor and weather inputs **hurt** at 1 day ahead
- Retraining helped only at 10 minutes; 80% prediction intervals covered **78–82%**

`LightGBM` `scikit-learn` `Day-Block Bootstrap` `43 tests`

[Repository](https://github.com/kanishk2705/Residential-Energy-Forecasting-Under-Changing-Conditions) · [Project Page](https://kanishk2705.github.io/Residential-Energy-Forecasting-Under-Changing-Conditions/)

---

## 04 · Constraint-Aware Examination Timetable Optimizer

**Combinatorial Optimization · Constraint Programming · Metaheuristics**

A pre-registered study of when exact solving pays off for exam timetabling. Exams are vertices of a conflict graph. The study compares greedy constructions, tuned simulated annealing, OR-Tools CP-SAT and a local-search-then-CP-SAT hybrid on 108 held-out instances.

- All 1,072 stored timetables were re-checked by an independent validator: **0 hard-constraint violations**
- Mean excess cost: hybrid **0.05**, CP-SAT 0.24, local search 1.20, best greedy 1.78
- A measured **size crossover**: CP-SAT wins at medium size, local search at large size
- A one-feature rule (graph edges ≤ 505 → CP-SAT) beat both fixed policies

`OR-Tools CP-SAT` `Simulated Annealing` `Graph Colouring` `NumPy`

[Repository](https://github.com/kanishk2705/Constraint-Aware-Examination-Timetable-Optimizer) · [Project Page](https://kanishk2705.github.io/Constraint-Aware-Examination-Timetable-Optimizer/)

---

## 🔧 Currently Building

| Project | Area | Status |
| --- | --- | --- |
| [Stock Market News Sentiment Analysis](https://github.com/kanishk2705/Stock-Market-News-Sentiment-Analysis) | Financial NLP · Data pipelines | 🟡 Being reworked |
| [AI Multi-Condition Patient Journey Assistant](https://github.com/kanishk2705/AI-Multi-Condition-Patient-Journey-Assistant) | RAG · Grounded generation | 🟡 Spec frozen, build next |

---

# 🧰 Technology Stack

Only tools used in the projects above or in my internship.

<div align="center">

<img src="https://skillicons.dev/icons?i=python,c,postgres,pytorch,sklearn,fastapi,docker,git,github&theme=light" />

<br><br>

<img src="https://img.shields.io/badge/LightGBM-111827?style=flat-square"/>
<img src="https://img.shields.io/badge/XGBoost-337AB7?style=flat-square"/>
<img src="https://img.shields.io/badge/Sentence_Transformers-111827?style=flat-square"/>
<img src="https://img.shields.io/badge/OR--Tools_CP--SAT-4285F4?style=flat-square"/>
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

### Machine Learning Intern · Pratinik Infotech
`April 2026 – June 2026`

Completed all three internship projects (one was required), each taken from data preparation through to a FastAPI service and a Streamlit dashboard:

- **Predictive Maintenance:** rolling-window sensor features, XGBoost failure prediction over a 24-hour horizon
- **Credit Card Fraud Detection:** imbalanced classification with SMOTE and LightGBM, low-latency scoring API
- **NLP for Customer Support:** TF-IDF + LinearSVC ticket triage with interpretable keyword drivers

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
