# Diabetic-Complication-Detection-from-Clinical-Notes
This project identifies diabetic complications like neuropathy, nephropathy, and retinopathy, from unstructured clinical notes using regular expressions and negation detection. It was completed as part of the Clinical Natural Language Processing course from the University of Colorado on Coursera.

 Objective
To develop and evaluate a rule-based NLP system that classifies clinical notes for the presence or absence of diabetic complications using only free-text data (no structured fields).

 Background
Diabetic complications are often mentioned in narrative notes rather than coded data. The challenge is to accurately detect these mentions, while handling negations, synonyms, and variations in expression. 

 Methodology
 Text Processing Technique: Keyword Window Method
Instead of using section headers (which were unreliable in this corpus), we extracted a 20-word window around keywords for each complication. This helps catch mentions that may appear in different places or formats.

 Evaluation Metrics
We computed:
Confusion Matrix
Accuracy
Precision
Recall
F1 Score
Against a gold standard manually labeled dataset.

 Results
Complication	Accuracy	Precision	Recall	F1 Score
Neuropathy	86.5%	43.8%	93.3%	59.6%
Nephropathy	90.8%	42.9%	90.0%	58.1%
Retinopathy	97.2%	33.3%	33.3%	33.3%

 Sample Output
Correctly detected:
"Patient suffers from diabetic nephropathy and has elevated creatinine."
Incorrectly detected:
"No signs of retinopathy observed" → incorrectly classified as positive due to negation not being caught early in development.

 Future Work
Use section-aware filtering in combination with keyword windows.
Incorporate machine learning (e.g. logistic regression or BERT-based classifiers).
Improve negation scope detection using dependency parsing (like spaCy or NegEx).

 Files
Identifying Diabetic Complications from Clinical Notes.R – main code
README.md – this document
Identifying Diabetic Complications from Clinical Notes.ppt – final presentation deck


 Environment
Language: R
Packages: tidyverse, stringr, bigrquery, DBI, magrittr

 Acknowledgements
University of Colorado System – Clinical Data Science Specialization
MIMIC-III demo dataset (used via BigQuery)

