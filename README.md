# AI-Powered Resume Analyzer

A beginner-friendly Python project that compares a candidate's resume with a job description. It calculates a text-similarity score, checks for selected skills, highlights missing skills, and displays simple visualizations.

## Features

- Extracts text from text-based PDF resumes using PyPDF2.
- Compares resume text with a job description using TF-IDF and cosine similarity.
- Calculates and displays a resume-job text similarity score.
- Checks a configurable list of skills and identifies matched and missing skills.
- Displays a skill analysis table and charts.
- Prints basic suggestions based on missing skills.
- Includes sample resume and job-description text so the notebook can be tested without a personal resume.

## Technology stack

- Python
- Jupyter Notebook
- Pandas
- Matplotlib
- Scikit-learn (TF-IDF and cosine similarity)
- PyPDF2

## Project structure

```text
AI-Resume-Analyzer/
│
├── AI_Resume_Analyzer.ipynb
├── resume.pdf                 # Optional: your own PDF resume (do not commit private resumes)
├── requirements.txt
├── README.md
└── Report/
    └── AI_Resume_Analyzer_Report.docx
```

You can also keep the notebook inside a `notebooks/` folder if that is how your repository is organized. Update the PDF path in the notebook if needed.

## Setup and installation

1. Clone or download this repository.
2. Open a terminal in the project folder.
3. (Recommended) Create and activate a virtual environment:

   ```bash
   python -m venv venv
   ```

   Windows:

   ```bash
   venv\Scripts\activate
   ```

   macOS/Linux:

   ```bash
   source venv/bin/activate
   ```

4. Install the dependencies:

   ```bash
   pip install -r requirements.txt
   ```

5. Start Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

6. Open `AI_Resume_Analyzer.ipynb` and run the cells from top to bottom.

If Jupyter Notebook is not installed in your environment, install it with:

```bash
pip install notebook
```

## Using your own resume

- Place a text-based PDF resume in the same folder as the notebook.
- Name it `resume.pdf`, or edit the `resume_path` variable in the PDF extraction cell.
- Run the notebook cells in order.
- Replace the sample job description in the notebook with the job description you want to evaluate.

The notebook uses sample resume text when `resume.pdf` is not found. Scanned/image-only PDFs may not produce extractable text because OCR is not included.

## How it works

1. **PDF text extraction:** PyPDF2 reads text from each page of a PDF.
2. **Text representation:** `TfidfVectorizer` converts the resume and job description into TF-IDF feature vectors.
3. **Similarity calculation:** Cosine similarity compares the two vectors and returns a percentage-style text similarity score.
4. **Skill checking:** A configurable list of skill keywords is checked against the job description and resume text.
5. **Results:** The notebook displays matched and missing skills, a table, charts, and simple improvement suggestions.

## Important limitations

- The similarity score measures overlap in text representation; it is **not** a probability of getting hired and is not a validated measure of candidate quality.
- The skill checker uses straightforward keyword matching. It may miss synonyms, related skills, spelling variations, and context.
- The current skill list is limited and should be expanded for different job roles.
- Scanned PDFs may require OCR, which is not included.
- The project does not verify the truth of information in a resume.

## Privacy

Do not upload personal resumes, phone numbers, addresses, or other private information to a public GitHub repository. Use sample or anonymized resumes for demonstrations.

## Future improvements

- Add DOCX resume support.
- Add OCR for scanned resumes.
- Expand skill dictionaries by job role and recognize common synonyms.
- Build a simple web interface using Streamlit or Flask.
- Add structured extraction for education, experience, projects, and certifications.
- Evaluate the matching method against a larger, carefully prepared test set.

## Author

Add your name, institution, and contact or portfolio links here.

## License

Choose and add a license before allowing others to reuse or distribute this project.
