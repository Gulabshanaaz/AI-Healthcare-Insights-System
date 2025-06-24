# 🧠 AI-Based Healthcare Research Insights System

This academic capstone project automates the process of analyzing healthcare research papers using Artificial Intelligence (AI) and Natural Language Processing (NLP). The goal is to extract meaningful insights from large volumes of academic literature and visualize them via interactive dashboards.

---

## 🎯 Project Objective

Manual review of extensive medical literature is time-consuming. This system:
- Extracts text from PDF research papers
- Summarizes key findings using BERT
- Identifies major themes using LDA topic modeling
- Stores results in a SQLite database
- Visualizes insights using Metabase dashboards

---

## 📁 Repository Structure

| File Name                          | Description                                |
|-----------------------------------|--------------------------------------------|
| `AI_Healthcare_Insights_Pipeline.ipynb` | End-to-end Jupyter Notebook pipeline       |
| `Healthcare_Research_DB.sqlite`         | SQLite database used for dashboard         |
| `Capstone_Research_Report.pdf`          | Detailed academic report                   |
| `requirements.txt`                      | Python dependencies                        |
| `README.md`                             | Project overview and setup guide           |

---

## ⚙️ Tech Stack

- **Text Extraction**: PyPDF2
- **Text Preprocessing**: spaCy
- **Summarization**: BERT Extractive Summarizer
- **Topic Modeling**: LDA (via Gensim)
- **Database**: SQLite
- **Dashboard**: Metabase (Docker deployment)
- **Platform**: Jupyter Notebook (Colab/Local)

---

## 🚀 How to Run This Project

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/AI-Healthcare-Insights-System.git
cd AI-Healthcare-Insights-System
```

### 2. Install Python Dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the Notebook
Open `AI_Healthcare_Insights_Pipeline.ipynb` in Jupyter or Google Colab.  
Follow the cells in order to:
- Upload a research paper
- Extract, clean, and summarize text
- Generate topics and store in the SQLite DB

---

## 📊 Launch Metabase with Docker (for Dashboard)

Make sure Docker is installed. Then run:

```bash
docker run -d -p 3000:3000 \
  -v "$PWD:/metabase" \
  -v "$PWD/Healthcare_Research_DB.sqlite:/metabase/Healthcare_Research_DB.sqlite" \
  --name metabase metabase/metabase
```

1. Open [http://localhost:3000](http://localhost:3000)
2. Choose SQLite as DB and point it to the `Healthcare_Research_DB.sqlite` file
3. Build dashboards for:
   - Topic frequency
   - Research trends
   - Word clouds

---


## 📌 Notes
- Ensure the database path is correctly mapped in Docker
- For large PDFs, runtime on Colab may vary
- This setup uses open-source tools only – no paid licenses needed

---

## 👥 Authors
- **Shaik Mohammad Gulab Shanaaz**
- **Jai Raj Yadav**

_Capstone project for MIS 6349 – Digital Consulting Project, University of Texas at Dallas_

---

## 📚 References
- [BERT](https://arxiv.org/abs/1810.04805)
- [spaCy](https://spacy.io/)
- [PyPDF2](https://pypi.org/project/PyPDF2/)
- [Gensim LDA](https://radimrehurek.com/gensim/)
- [Metabase Docs](https://www.metabase.com/docs/latest/)
- [Docker](https://docs.docker.com/get-started/)