# MachineLearningProject
A machine-learning analysis of existentialist discourse on Reddit, using TF-IDF, NMF topic modeling, SBERT sentence embeddings, and clustering to uncover semantic and thematic patterns in large-scale online discussions.
# Dataset Access (Important)
GitHub has a 25MB file-size limit, so the full dataset cannot be uploaded directly.
Download all data files from Google Drive:

--> Download Original Reddit Dataset from:
https://drive.google.com/drive/folders/1HoqedXR-MmdldJvVFDLi99Jw0uxhnYFZ?usp=drive_link

There are four data files in this folder: "E_comments.txt" "E_submission.txt" "EC_comments.txt" "EC_submission.txt"

   
--> Download Processed Reddit Dataset from:
https://drive.google.com/drive/folders/1HS5J9NsoEpcjFcPLr8mfh8khvKb80pHo?usp=sharing

There are four data files in this folder: "ML_reddit.txt"(Combined file after first cleaning pass), "ML_clean.txt" (Intermediate cleaned version), and "ML_superclean.txt" (Final dataset used for all modeling)

After downloading, Run ML.ipynb
# Project Goals
This project investigates:
How people discuss existential questions in online spaces
What semantic themes dominate this discourse
How different machine learning methods agree or disagree about topic structure
Whether semantic clustering reveals deeper psychological and philosophical patterns
# Methods Used
1. TF-IDF + KMeans
Represents each comment as a sparse vector of weighted word frequencies
Good for surface-level clustering
Limitations: ignores context, order, semantics
2. NMF (Non-negative Matrix Factorization)
Factorizes the document-term matrix into additive topics
Highly interpretable topic-word distributions
Still a bag-of-words model (no contextual semantics)
3. SBERT Sentence Embeddings + KMeans
Encodes each comment as a 768-dimensional semantic vector
Captures meaning, paraphrase similarity, and conceptual relations
Best-performing and most meaningful method in this project
# Diagnostics and Visualization
The notebook includes:
PCA (linear structure test)
UMAP (local neighborhood test)
Elbow curves for KMeans stability
Cluster interpretability evaluation
Due to the high dimensionality and short-comment structure, projections show dense clouds (not unusual for text data).
# Limitations (Short Version)
Reddit users ≠ general population
TF-IDF + NMF ignore word order
SBERT truncates long comments at 512 tokens
Topic labeling involves subjective interpretation
PCA/UMAP do not show clear separability (common in NLP)
Full justification is in the paper.
# Future Work
Fine-tune a full BERT model on the corpus for masked-language probing
Use long-sequence models (Longformer, BigBird) to remove truncation limits
Human-coded topic labels for validation
Expand the dataset to other forums, surveys, interviews
Add sentiment/emotion classification (VADER, NRC, RoBERTa emotion model)
