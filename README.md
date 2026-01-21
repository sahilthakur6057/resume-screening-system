# Resume Screening & Candidate Ranking System 
Simple ML-based resume ranking using TF-IDF + skill keyword matching
A simple yet effective **Machine Learning project** that automatically screens resumes and ranks candidates based on how well they match a given job description.

This project simulates a basic ATS (Applicant Tracking System) using keyword skill matching + text similarity.

### What it does
- Cleans resume text (lowercase, remove punctuation & extra spaces)
- Extracts key skills from a predefined list (Python, SQL, Machine Learning, NLP, Pandas, NumPy, Keras, etc.)
- Calculates **text similarity** using **TF-IDF + Cosine Similarity**
- Combines two scores into final ranking:
  - 60% → semantic/text similarity to job description
  - 40% → number of matching skills
- Outputs ranked list of best-fitting candidates

### Sample Result  
Job Description used:  
"Looking for a Data Scientist with strong Python, SQL, Machine Learning, NLP, Pandas, NumPy and data visualization skills."

**Top ranked candidates** from the dataset:

| Rank | Category          | Skills Found (count)                              | Skill Score | Text Similarity | Combined Score |
|------|-------------------|----------------------------------------------------|-------------|------------------|----------------|
| 1    | Data Science      | numpy, keras, pandas, machine learning, matplotlib, ... | 13          | 0.245           | **0.547**      |
| 2    | Data Science      | numpy, pandas, machine learning, deep learning, ...     | 8           | 0.260           | 0.402          |
| 3    | Data Science      | numpy, pandas, machine learning, matplotlib, ...        | 9           | 0.097           | 0.335          |
| 4    | Data Science      | machine learning, python                               | 2           | 0.338           | 0.264          |
| 5    | Data Science      | machine learning, deep learning, nlp, sql, python, ...  | 6           | 0.102           | 0.246          |
| 6    | Data Science      | nlp, machine learning, python                          | 3           | 0.239           | 0.236          |
| 7    | Data Science      | machine learning, python, keras, ml                    | 4           | 0.137           | 0.205          |
| 8    | Python Developer  | tensorflow, numpy, python, sql                         | 4           | 0.126           | 0.199          |

(You can see the full ranking table when you run the notebook)

### Tech Stack
- Python 3
- pandas
- numpy
- scikit-learn (TfidfVectorizer + cosine_similarity)
- re (regular expressions)

### How to Run
1. Clone or download this repository
2. Install dependencies:

```bash
pip install pandas numpy scikit-learn jupyter
jupyter notebook resume_screening.ipynb
.
├── resume_screening.ipynb          # Complete code + results
├── UpdatedResumeDataSet.csv        # 962 sample resumes (~1 MB, public dataset)
└── README.md
