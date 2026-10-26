# Hi, I'm Aviraj

**Pune, India** | **Data Science and AI Engineer** | **B.E. AI & Data Science '27 (CGPA 9.28)** | **Ex-Founder, MahaGuru AI (COEP I2I)**

![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/-Scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![MySQL](https://img.shields.io/badge/-MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![NumPy](https://img.shields.io/badge/-NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/-Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![Streamlit](https://img.shields.io/badge/-Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)
![FastAPI](https://img.shields.io/badge/-FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Google Gemini](https://img.shields.io/badge/-Gemini%20%7C%20Gemma-8E75B2?style=flat-square&logo=googlegemini&logoColor=white)
![Supabase](https://img.shields.io/badge/-Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white)
![Next.js](https://img.shields.io/badge/-Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/-React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/-GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)

> Building AI systems that reason, verify, and know when to stop.

---

## Featured: Fix with Me

**An AI repair assistant for Indian households, in English, Hindi and Hinglish.** Describe what is broken by typing, talking or taking a photo. Fixy asks a few targeted questions, names the likely fault with a confidence score, walks through a safe and sourced fix, and stops the session when the job needs a professional.

<a href="https://fixwithme.avirajvirape601.workers.dev">
  <img src="assets/fixwithme-screens.jpg" alt="Fix with Me screens: home, diagnosis chat, repair guide, guided step and safety stop" width="100%" />
</a>

![Top-1 diagnosis](https://img.shields.io/badge/Top--1%20diagnosis-90.7%25-0F766E?style=flat-square)
![Unsupported claims](https://img.shields.io/badge/Unsupported%20claims-0%25-0F766E?style=flat-square)
![Retrieval recall@5](https://img.shields.io/badge/Retrieval%20recall%405-100%25-0F766E?style=flat-square)
![Safety-stop recall](https://img.shields.io/badge/Safety--stop%20recall-100%25-0F766E?style=flat-square)
![Tests](https://img.shields.io/badge/pytest-118%20tests-0F766E?style=flat-square&logo=pytest&logoColor=white)

| | |
|---|---|
| **Diagnosis engine** | A Bayesian engine over a curated knowledge base (ceiling fans, extension boards, headphones, battery toys) picks the most informative next question. **90.7% top-1 and 96.0% top-3** on the 94-case FixBench-IN benchmark, versus 81.3% top-1 for plain Gemini. It keeps working when the LLM quota runs out. |
| **Verified answers (RAG)** | Hybrid retrieval on Supabase (pgvector + PGroonga full-text, Reciprocal Rank Fusion) over curated guides and Wikipedia, **100% recall@5**. Gemini drafts with citations and Gemma checks every claim: **92.5% correct answers and 0% unsupported claims**, versus 87.5% and 34% for plain Gemini. Says "not sure" when the sources do not cover a question. |
| **Safety gate** | Rules in three languages plus a TF-IDF + logistic regression classifier trained on 3.8K examples and exported to a **0.68 MB pure-Python runtime (about 0.2 ms per message)**. Hazard recall rose from 67.2% to 89.1%; safety-stop recall is **100% versus 84.6%** for plain Gemini, with 0% false stops. |
| **Product** | Fixy, an animated robot guide; photo identification with location data removed on the device; voice input and spoken replies; step-by-step guides with tools, time, a rupee estimate, cited sources and part search links. |
| **Engineering** | FastAPI and Pydantic with an LLM provider chain and model fallbacks, per-IP rate limits, Docker on Render, a Next.js PWA on Cloudflare Workers, and CI with ruff, 118 pytest tests and a benchmark gate that fails the build if any safety case does not stop. |

```mermaid
flowchart LR
    U["Text, voice or photo"] --> W["Next.js PWA<br/>Cloudflare Workers"]
    W --> A["FastAPI on Render"]
    A --> S{"Safety gate<br/>rules + classifier"}
    S -- "hazard" --> X["Stop screen<br/>112 and electrician"]
    S -- "safe" --> D["Bayesian diagnosis<br/>curated knowledge base"]
    D --> G["Repair guide<br/>tools, cost, parts, sources"]
    A --> R["Hybrid retrieval<br/>pgvector + PGroonga, RRF"]
    R --> L["Gemini draft<br/>with citations"]
    L --> V["Gemma claim check"]
    V --> W
```

[![Live demo](https://img.shields.io/badge/Live%20demo-Fix%20with%20Me-0F766E?style=for-the-badge)](https://fixwithme.avirajvirape601.workers.dev)
[![Source](https://img.shields.io/badge/Source-FixWithMe-181717?style=for-the-badge&logo=github)](https://github.com/aviraj1805/FixWithMe)

[Benchmark report](https://github.com/aviraj1805/FixWithMe/blob/main/eval/reports/fixbench-v1-2026-10-24.md) · [QA report](https://github.com/aviraj1805/FixWithMe/blob/main/eval/reports/qa-v1-2026-10-24.md) · [Safety model card](https://github.com/aviraj1805/FixWithMe/blob/main/ml/safety_classifier/README.md) · [Design](https://github.com/aviraj1805/FixWithMe/blob/main/docs/design.md)

<sub>The API runs on Render's free tier, so the first answer can take about a minute while it wakes up. Benchmarks are small, author-written sets; the reports list their limits.</sub>

---

## MahaGuru AI

**An open-source AI mentor and personalised classroom for college students.** Rebuilt from my COEP I2I startup; live, tested and deployed.

<a href="https://mahaguru-ai.onrender.com">
  <img src="https://raw.githubusercontent.com/aviraj1805/MahaGuru-V1/main/docs/screenshots/home.png" alt="MahaGuru AI homepage" width="100%" />
</a>

| | |
|---|---|
| **StudentGPT** | A reflective mentor that asks before it advises. English and Hinglish safety screening on every message, a structured understanding record, and a clarity summary at the end. |
| **Classroom** | Turns a goal into a diagnostic, a personalised roadmap, generated lessons with an AI teacher, quizzes, graded projects and adaptive mastery tracking. |
| **Engineering** | FastAPI and React (TypeScript) monorepo, PostgreSQL, streamed replies over SSE, a provider-agnostic LLM layer (Gemini by default), one Docker image. |
| **Quality** | pytest on SQLite and PostgreSQL, Playwright end-to-end tests on desktop and mobile, CI on every push, and a 24-scenario evaluation suite including crisis cases. |

[![Live demo](https://img.shields.io/badge/Live%20demo-mahaguru--ai.onrender.com-1D4ED8?style=for-the-badge)](https://mahaguru-ai.onrender.com)
[![Source](https://img.shields.io/badge/Source-MahaGuru--V1-181717?style=for-the-badge&logo=github)](https://github.com/aviraj1805/MahaGuru-V1)

[Research behind it](https://mahaguru-ai.onrender.com/research) · [Architecture](https://github.com/aviraj1805/MahaGuru-V1/blob/main/docs/architecture.md) · [Evaluation method](https://github.com/aviraj1805/MahaGuru-V1/blob/main/docs/evaluation.md) · [Screenshots](https://github.com/aviraj1805/MahaGuru-V1#screenshots)

---

## Other Projects

Projects from my resume first, with live demos wherever one is available.

| Project | What it does | Links |
|---|---|---|
| **Customer Churn Prediction** | Kaggle Playground S6E3. XGBoost and LightGBM on ~594K telecom records (21 features) with 5-fold stratified CV; XGBoost reached **0.916 mean ROC-AUC**. EDA surfaced the strongest churn drivers: electronic-check payment, month-to-month contracts, fiber-optic internet and first-year customers. | [Live demo](https://churn-predictor-aviraj.onrender.com/) · [Source](https://github.com/aviraj1805/Customer-Churn-Prediction) |
| **CreditWise: Loan Approval** | scikit-learn pipeline on 950 applicants (18 features). A class-balanced Random Forest reached **0.91 F1 and 0.98 ROC-AUC**, versus 0.81 F1 for a logistic-regression baseline. Deployed with live predictions, confidence scores and feature importance. | [Live demo](https://creditwiseloanapprovall.streamlit.app/) · [Source](https://github.com/aviraj1805/CreditWise-Loan-Approval-System) |
| **IAMARS: Drone Detection and Tracking** | Team project. YOLOv8n fine-tuned on VisioDECT with a leakage-aware split: **0.965 mAP@0.5** on a 1,800-image held-out set. ByteTrack tracking, 88.5 FPS on an RTX 2050, and intercept-point prediction in 3D simulation. | [Live demo](https://huggingface.co/spaces/AvirajV/iamars-drone-tracking) · [Source](https://github.com/aviraj1805/intelligent-aerial-monitoring) |
| **PhonePe Pulse Insights** | Internship project. ETL of PhonePe Pulse JSON data (2018 to 2024) into a 9-table MySQL database, 10 SQL business questions, and a multi-page Streamlit and Plotly dashboard. | [Live charts](https://aviraj1805.github.io/portfolio/demos/phonepe/) · [Source](https://github.com/aviraj1805/PhonePe) |
| **Mental Health in Tech: EDA** | 1,251 survey responses analysed for what drives treatment-seeking: family history, work interference and employer benefits. Published as an interactive Plotly dashboard. | [Live dashboard](https://aviraj1805.github.io/portfolio/demos/mental-health/) · [Source](https://github.com/aviraj1805/mental-health-survey-eda) |
| **Tesla Stock Prediction** | Deep learning pipeline: SimpleRNN, LSTM and a tuned LSTM with 1, 5 and 10-day forecasts. | [Source](https://github.com/aviraj1805/Tesla-Stock-Price-Prediction) |
| **Real Estate Advisor** | XGBoost model predicting property profitability and future value. | [Source](https://github.com/aviraj1805/Real-Estate-Investment-Advisor-XGBoost-) |
| **Yes Bank Stock Price Prediction** | Machine learning on historical OHLC data to predict Yes Bank closing prices. | [Source](https://github.com/aviraj1805/YesBank_Internship) |
| **iTunes Music Store Analysis** | SQL analysis of the Apple iTunes database for insights on customer behaviour. | [Source](https://github.com/aviraj1805/iTunes-Data-Analysis) |

More in my [portfolio](https://aviraj1805.github.io/portfolio/) and on [GitHub](https://github.com/aviraj1805?tab=repositories).

---

## What I'm Doing

- **Building Fix with Me** — A bilingual AI repair assistant: Bayesian diagnosis, verified RAG answers and a trained safety gate
- **Maintaining MahaGuru AI** — A reflective AI mentor and an adaptive AI classroom for students, open source and live
- **Evaluating LLM systems** — Benchmarks against plain-LLM baselines, per-claim verification, safety recall and calibration
- **Shipping ML pipelines end-to-end** — From EDA and model selection to deployment and monitoring
- **Researching human-centered AI** — Presented at INMEC-2026, Keystone School of Engineering, Pune (reflective mentorship with LLMs)

---

## Experience

**Founder — MahaGuru AI** *(Jan 2024 – Nov 2025; rebuilt as open source in 2026)*
Founded an AI student-guidance platform, selected into **COEP's I2I Startup Program** for mentorship and incubation. Designed a multi-agent LLM architecture (FastAPI, React), curated a custom student-mentor dialogue dataset, and collected feedback from about 150 student users on early prototypes; the underlying research was presented at INMEC-2026. After the company shut down, rebuilt the product as an open-source platform that is now [live](https://mahaguru-ai.onrender.com).

**Data Science Intern — Innovexis** *(Feb 2026 – May 2026)*
Built an ETL pipeline loading PhonePe Pulse JSON data (2018–2024) into a 9-table MySQL database, and a multi-page Streamlit + Plotly dashboard answering 10 business questions via SQL.

---

## GitHub Activity

<div align="center" style="margin: 25px 0; padding: 30px 20px; background: #ffffff; border-radius: 12px; border: 1px solid #e1e4e8; box-shadow: 0 2px 12px rgba(0,0,0,0.08); width: 100%;">
  
![GitHub Contribution Graph](https://ghchart.rshah.org/aviraj1805)

  <p style="color: #666; font-size: 12px; margin-top: 10px;">52 Weeks Contribution Activity</p>
</div>

---

### LeetCode Profile

[![LeetCode Profile](https://img.shields.io/badge/LeetCode-Profile-FFA116?style=flat-square&logo=leetcode&logoColor=black)](https://leetcode.com/u/aviraj_virape/)

**Statistics**

![Problems Solved](https://img.shields.io/badge/Problems%20Solved-275-FFA116?style=flat-square)
![Current Rank](https://img.shields.io/badge/Current%20Rank-Top%205%25-1DB954?style=flat-square)
![Consistency](https://img.shields.io/badge/Consistency-Active-4CAF50?style=flat-square)
![Difficulty Focus](https://img.shields.io/badge/Difficulty%20Focus-Medium%2FHard-FF6B6B?style=flat-square)

**Badges Earned**

<p style="text-align: center; margin: 20px 0;">
  <img src="50_days_badge.png" alt="50 Days Badge" width="180" style="margin: 0 10px; box-shadow: 0 2px 8px rgba(0,0,0,0.1); border-radius: 8px;">
  <img src="pandas_badge.png" alt="Introduction to Pandas Badge" width="180" style="margin: 0 10px; box-shadow: 0 2px 8px rgba(0,0,0,0.1); border-radius: 8px;">
  <img src="100_days.png" alt="100 Days Badge" width="180" style="margin: 0 10px; box-shadow: 0 2px 8px rgba(0,0,0,0.1); border-radius: 8px;">

</p>

---

### LeetCode Heatmap

<a href="https://leetcode.com/u/aviraj_virape/" align="center">
  <img src="https://leetcard.jacoblin.cool/aviraj_virape?theme=dark&font=Sora&ext=heatmap&site=lc" alt="LeetCode Stats" style="width: 100%; max-width: 100%; display: block; margin: 25px auto; border-radius: 12px; border: 1px solid #30363d;">
</a>

<p align="center" style="color: #8b949e; font-size: 12px; margin-top: 15px;">52 Weeks Submission Heatmap | Last Updated — 01/05/2026</p>

---

## Publication

Presented **"AI-Powered Reflective Mentorship"** at INMEC-2026 (1st International Conference, Keystone School of Engineering, Pune, Mar 2026)

---

## Education

**B.E. — Artificial Intelligence & Data Science**, APCOER, Pune *(2023 – 2027, expected May 2027)* — CGPA 9.28

**HSC Science**, Yashodhara Junior College, Solapur *(2021 – 2022)* — 78%

---

## Connect

<p align="center">
  <a href="https://www.linkedin.com/in/avirajvirape/">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/>
  </a>
  <a href="https://github.com/aviraj1805">
    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white"/>
  </a>
  <a href="https://leetcode.com/u/aviraj_virape/">
    <img src="https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=leetcode&logoColor=black"/>
  </a>
  <a href="mailto:virapeaviraj@gmail.com">
    <img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white"/>
  </a>
</p>

---

### Recognition

- Presented at **INMEC-2026, Keystone School of Engineering, Pune** — AI-Powered Reflective Mentorship
- Selected into **COEP's I2I Startup Program** — institutional backing for MahaGuru AI
- **Certified AI/ML Engineer** - Apna College Prime 2.0 Batch

### Philosophy

> Build systems that are useful, measurable, and honest. Ship working prototypes. Iterate from real feedback. Let the model do the heavy lifting — but understand every layer beneath it.

<details>
<summary>Random Facts</summary>

- Curated my first LLM dataset by hand: student-mentor dialogues for MahaGuru AI
- Founded an AI startup before finishing undergrad
- Competed on LeetCode to sharpen DSA fundamentals
- Believe in building small, shipping fast, and improving in production
- Based in Pune — powered by chai and curiosity

</details>
