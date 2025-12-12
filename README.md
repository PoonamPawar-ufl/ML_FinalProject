

SmartApply: Automated LinkedIn Messaging for Job Hunters

GitHub link : https://github.com/PoonamPawar-ufl/ML_FinalProject.git

Link to data file : https://uflorida-my.sharepoint.com/:f:/g/personal/p_pawar_ufl_edu/IgAWv0njen7dQYxuvHC73hycAeoESSVL8c8U0AqjFCQxA4g?e=mhC8cy

Data folder is uploaded to cloud instead of git due to large file size

Project Description

Job hunting for data-focused roles often involves tedious manual tasks such as scanning job postings, tailoring resumes, and drafting personalized messages. SmartApply auto-
mates this process by intelligently matching candidate resumes with job postings and generating customized LinkedIn messages. This paper presents a data-driven approach using a Kaggle job
posting dataset to simulate the workflow. The system analyzes job descriptions, extracts required skills, compares them with candidate profiles, and generates personalized outreach messages
highlighting the most relevant qualifications. In this updated version, the system includes extended evaluation metrics such as precision, recall, NDCG@K, and BLEU to assess ranking and
message quality. Additionally, the Streamlit interface has been enhanced for real-time interaction, Top-N ranking display, and skill highlighting, improving usability for job seekers. Updated
documentation provides setup instructions, architecture overview, and visual evidence of system performance. These refinements improve usability, interpretability, and reproducibility while maintaining effective resume-job matching.

Project Goal & Motivation

Job hunting for data-focused roles (like Data Scientist, AI Engineer, ML Engineer) often requires manually scanning job postings, tailoring resumes, and writing personalized messages—making the process repetitive, inefficient, and error-prone.

SmartApply aims to solve this by:
✔ Automating resume–job matching using NLP and embedding-based semantic similarity
✔ Highlighting matching skills for better interpretability
✔ Generating personalized recruiter messages automatically
✔ Providing a simple, interactive Streamlit interface for seamless user experience

This approach empowers job seekers to apply faster, smarter, and more effectively—while retaining control over message personalization and ethical AI use.

Installation and Setup

1. Clone the repository
    git clone https://github.com/yourusername/SmartApply.git
    cd SmartApply

2. Create and Activate Virtual Environment
    python -m venv venv
    source venv/bin/activate     # Mac/Linux
    venv\Scripts\activate        # Windows

3. Install Dependencies
    pip install -r requirements.txt

4. Add Dataset and Resume (These datasets are uploaded on cloud )
    SmartApply/data/postings.csv  
    SmartApply/data/cleaned_jobs.csv  
    SmartApply/data/Your_Resume.txt  

5. Run the App
    streamlit run UI/app.py


Dataset

Source: Kaggle Job Postings Dataset

Type: Tabular CSV, text-based fields (job title, company, description)

Size: ~100,000 postings

Location in Repo: Place CSV file in /data/postings.csv


SYSTEM ARCHITECHTURE

![alt text](screenshots/architecture_diagram.png)

SmartApply uses a modular, multi-layered architecture to automate resume–job matching and generate personalized LinkedIn messages. It consists of three core layers:

Presentation Layer (UI)

Streamlit interface for uploading resumes, viewing top-matched jobs, similarity scores, and generated messages.

Handles user interactions and requests backend processing.

Application & Business Logic Layer

Job Matcher API: Preprocesses text, retrieves job embeddings, computes semantic similarity, and returns ranked results.

ML/AI Microservices:

Resume Parser (SpaCy/NLTK)

Skill Extraction Engine (regex, TF-IDF, NER)

Embedding Service (Sentence-BERT)

Similarity Engine (cosine similarity & ranking)

Message Generator (GPT/T5/OpenAI)

Data Layer

Job Database (CSV)

Logs & Analytics Store (evaluation metrics, user interactions)

Embeddings Cache for faster similarity computation

Benefits: Scalable, maintainable, interpretable, and easily integrates AI/NLP services for automated job matching and messaging.



Example Usage 

🔹 Upload Resume & Select Job Type

![alt text](screenshots/demoStep1.png)

🔹 View Top-N Matching Jobs

![alt text](screenshots/demoStep2.png)

🔹 Auto-Generated LinkedIn Message

![alt text](screenshots/AutoGenerate.png)


Performance Metrics

🔹  Model Performance Metrics 
![alt text](screenshots/ModelPerformance.png)

🔹 Precision / Recall / NDCG vs K
![alt text](screenshots/performanceGraph.png)

🔹 Match Score Distribution (Top N)
![alt text](screenshots/TopN_MatchScore.png)

🔹  Top Match Results (Table)
![alt text](screenshots/TopMatchTable.png)

Author

Name: Poonam Pawar
Email: p.pawar@ufl.edu

Project Structure


smartApply/
│
├── data/                   # Kaggle dataset CSV
│   ├── postings.csv
│   ├── cleaned_jobs.csv
│   ├── Poonam_Kishor_Pawar_Resume.txt
│
├── docs/                          # Project documentation
│   ├── Report_deliverable_2.pdf
|   ├── Report_deliverable_3.pdf
│   └── Technical Blueprint Report.pdf
│
├── results/                       # Analytics results & visualizations
│   ├── correlation_heatmap.png
│   ├── Job Distribution.png
│   ├── Salary_by_Experience_Level.png
│   ├── Salary_by_workType.png
│   ├── Salary_distribution.png
│   ├── top_10_job_title.png
│   └── top_10_locations.png
│
├── src/                           # Core backend logic & data processing
│   ├── EDA_smarApply.ipynb        # Exploratory Data Analysis notebook
│   ├── job_matcher.py             # Job-resume matching logic
│   └── metrics.py                 # Evaluation metrics (similarity, ranking, etc.)
│
├── UI/                            # Frontend / User Interface
│   └── app.py                     # Streamlit or Flask UI application
│
│
├── Screenshots/                            
│   └── architecture_diagram.png                              
│   └── demoStep1.png                             
│   └── demoStep2.png                              
│   └── AutoGenerate.png                            
│   └── ModelPerformance.png                             
│   └── performanceGraph.png                        
│   └── TopN_MatchScore.png                           
│   └── TopMatchTable.png
│
├── README.md                      # Main documentation file
└── requirements.txt               # Python package dependencies
