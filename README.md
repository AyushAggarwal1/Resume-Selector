# Resume-Selector

## Overview
Resume-Selector is a machine learning project designed to analyze and classify resumes based on industry sectors. Using a dataset from Kaggle, this project employs various preprocessing techniques and machine learning algorithms to streamline the hiring process.

## Features
- **Data Cleaning:** Remove special characters, stopwords, and irrelevant information from resumes.
- **Feature Extraction:** Utilize TF-IDF to convert textual data into numerical vectors suitable for machine learning.
- **Classification:** Implement a machine learning model to categorize resumes by industry.

## Dataset Description
The dataset for this project was sourced from Kaggle and is in Excel format, consisting of three columns:

- **ID:** Sequence number of the resume
- **Category:** Industry sector to which the resume belongs
- **Resume:** The complete CV of the candidate

## Preprocessing Steps
The preprocessing of resumes involves several key steps to ensure data quality:
- **Data Cleaning:**
   - Remove special characters, single-letter words, and unique letters/numbers from resumes.
   - Tokenize the text using the NLTK tokenizer.

- **Masking:**
   - Mask strings using `\w`.
   - Mask escape characters like `\n`.
   - Mask all numbers.
   - Remove email addresses.

- **Stopword Removal:**
   - Common stopwords (e.g., "and", "the", "was") are removed as they limit prediction accuracy.
   - Input words are tokenized into individual tokens and checked against the NLTK stopwords list:
     ```python
     from nltk.corpus import stopwords
     stop_words = set(stopwords.words('english'))
     ```
   - Words found in the stopwords list are removed from the main array until no stopwords remain.

- **Feature Extraction:**
   - The TF-IDF (Term Frequency-Inverse Document Frequency) method is used to extract features from the preprocessed dataset.
   - Cleaned data is transformed into numerical vectors for classification.
   - Utilized `TfidfVectorizer` from the Scikit-learn library with the following configurations:
     - **Sub-linear DF:** Set to True to apply a logarithmic scale for frequency.
     - **Min DF:** Defines the minimum number of documents a word must appear in to be included.
     - **Norm:** Set to L2 to ensure all feature vectors have the same Euclidean norm.
     - **N-gram Range:** Set to (1, 2) to include both unigrams and bigrams.

By following these steps, the project effectively prepares the resumes for accurate analysis and classification.

## Dataset
The dataset used in this project is sourced from Kaggle and is in Excel format. It includes the following columns:
- **ID:** Sequence number of the resume
- **Category:** Industry sector associated with the resume
- **Resume:** Full text of the candidate's CV

## Technologies Used
- Python
- NLTK for natural language processing
- Scikit-learn for machine learning
- Pandas for data manipulation
- NumPy for numerical operations

## Installation
 - Clone the repository:
   ```bash
   git clone https://github.com/AyushAggarwal1/Resume-Selector.git
   cd Resume-selector
