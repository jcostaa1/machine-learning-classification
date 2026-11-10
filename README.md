# 📊 Machine Learning Applied to Recruitment and Selection

## 📌 About the Project
As an academic assignment, a Supervised Machine Learning project was developed, using the structure of a practical case focused on sales analysis as a reference. The dataset used in this repository is different from the one originally proposed, because some of the data contained sensitive and fragile information. Because of this, the project mainly reuses the code logic, analytical methodology, and project structure, with adaptations made by the group for learning purposes.

In this repository, the dataset was adapted to a Recruitment and Selection scenario, made up of 500 fictional candidates generated with Python (Faker, NumPy), with no real information whatsoever.

## 🗂️ Dataset
File: `database_recruiter.csv` (simulated data, no real information).

| Variable | Description |
|---|---|
| `ID_Candidato` | Candidate identifier |
| `Status` | Final result: Approved / Rejected (target variable) |
| `Data_Inscricao` | Date the candidate applied for the position |
| `Data_Finalizacao` | Date the process ended |
| `Motivo_Reprovacao` | Rejection reason (empty for approved candidates) |
| `Tempo_Processo_Dias` | Duration of the selection process in days |
| `Pretensao_Salarial` | Expected salary informed by the candidate (R$) |
| `Recrutador` | Recruiter in charge |
| `Origem_Candidato` | Application channel (LinkedIn, Gupy, Referral, Catho, Indeed, Company Website) |
| `Senioridade` | Junior, Mid-level, or Senior |
| `Area` | Data, IT, Finance, HR, Marketing, or Operations |
| `Teste_Tecnico` | Technical test result |

## 🎯 Objective
Identify factors associated with the approval or rejection of candidates and assess whether it is possible to predict the outcome of the selection process.

**Business questions analyzed**

- Which application channel generates the most approvals?
- Are there differences in approval between areas and seniority levels?
- Does the expected salary influence the result?
- Is the duration of the selection process associated with approval?
- What are the main reasons for rejection?
- Is there a performance difference between recruiters?
- Is it possible to predict whether a candidate will be approved or rejected?

## 🧩 Methodology (CRISP-DM)
1. Business understanding
2. Data understanding (dictionary, quality, nulls, and duplicates)
3. Data preparation (date typing, target definition, null handling)
4. Exploratory data analysis (EDA)
5. Modeling (K-Means and Decision Tree)
6. Evaluation of results

## ⚙️ Techniques and Tools
Python · Pandas · NumPy · Matplotlib · Seaborn · SciPy (KS test) · Scikit-Learn · K-Means (Elbow and Silhouette) · Decision Tree · Temporal train/test split · ROC/AUC · Confusion Matrix · SHAP Values · Faker

## 🔎 What was done
- **EDA:** approved vs. rejected by origin, area, seniority, recruiter, and application month; approval rate by category; main rejection reasons; expected salary by seniority; process duration by status.
- **KS (Kolmogorov-Smirnov):** univariate importance of the numeric variables.
- **K-Means:** segmentation by expected salary and process duration, with K chosen via Silhouette.
- **Decision Tree:** approval prediction with a temporal split (oldest 70% for training, most recent 30% for testing) and interpretation via SHAP.

## 📈 Main Results and Learnings
- **Data leakage:** `Motivo_Reprovacao`, `Tempo_Processo_Dias`, `Data_Finalizacao`, and `Teste_Tecnico` are only known after the outcome (or are determined by it). For this reason they were left out of the model, which uses only variables available at the screening stage: expected salary, seniority, area, recruiter, and origin.
- Expected salary varies with seniority, but this reflects the way the dataset was simulated.
- Longer processes appear associated with rejections and withdrawals, but since `Tempo_Processo_Dias` is a consequence of the outcome, this relationship should not be read as causal.
- **Model performance:** since the dataset is fictional and mostly random, the model performs close to chance (AUC ≈ 0.5). This is expected and reinforces the importance of validating hypotheses and checking for leakage before trusting high metrics.
- Results by channel, area, and recruiter vary slightly from one another, but without strong differences, which is consistent with randomly generated data. (Update this section with the numbers from your own run.)

> ⚠️ **Warning:** the data is simulated and the results are for educational purposes only. They do not represent real selection processes and must not be used for decision-making.
