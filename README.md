# duplicate-question-pairing-for-quora
Over 100 million people visit Quora each month, so it's no wonder that many users ask questions with similar wording. Duplicate questions with the same purpose can make it harder for users to find the best answers and may lead contributors to respond to multiple versions of the same query. Quora prioritizes canonical questions as they improve the experience for both seekers and contributors, offering greater value to both groups over time.

To address this issue, I have created and tested a model using Random Forest and XGBoost algorithms, combined with a Bag of Words-based NLP approach. This machine learning solution efficiently identifies and consolidates duplicate questions, enhancing the overall user experience.
To address the problem of detecting duplicate questions, the following features and processes were implemented:

Sampling the Dataset:
A subset of the dataset (30,000 rows) was randomly sampled to reduce computation time and maintain diversity while ensuring reproducibility using a random seed.

Feature Engineering:
Several features were derived from the questions to capture meaningful insights about their similarities and differences:

Question Lengths:

q1_len: Measures the length of question1 in terms of characters.
q2_len: Measures the length of question2 in terms of characters.
These features help identify how concise or verbose the questions are.
Number of Words in Questions:

q1_num_words: Counts the number of words in question1.
q2_num_words: Counts the number of words in question2.
These features provide insight into the structure of each question.
Common Words:

word_common: Counts the number of words shared between question1 and question2.
This feature highlights the overlap in vocabulary between the two questions.
Total Words:

word_total: Computes the total number of words in question1 and question2 combined.
This gives the overall word count of both questions together.
Word Share:

word_share: Calculates the proportion of common words relative to the total word count.
This normalized metric quantifies the similarity between the two questions.
Exploratory Data Analysis (EDA):

Distribution Analysis:
The distribution of key features (e.g., word_common, word_total, word_share) was analyzed using histograms and density plots to understand their behavior for duplicate (is_duplicate=1) and non-duplicate (is_duplicate=0) questions.

Class Imbalance Check:
The proportion of duplicate and non-duplicate questions was calculated to ensure proper understanding of the dataset's bias.

Preprocessing:

Missing values and duplicates in the dataset were checked and handled.
Question IDs were analyzed to identify repeated questions in the dataset.

