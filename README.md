# CLEF2025--CheckThat-Lab--4b

This project focuses on solving the subtask 4b of the 2025 CheckThat lab:
- **Subtask 4b (Scientific Claim Source Retrieval):** Given an implicit reference to a scientific paper, i.e., a social media post (tweet) that mentions a research publication without a URL, retrieve the mentioned paper from a pool of candidate papers.

There are 3 different approaches provided to solve this problem:
- **Traditional IR:** The BM25 is used as a foundational method and different metadata fields are incorporated and weighted.
- **Neural NLP:** Bi-Encoder Transformer models are used such as the general-purpose models `all-MiniLM-L6-v2` and `all-mpnet-base-v2`. Fine-tuning is applied with `MultipleNegativesRankingLoss` to improve model performance.
- **Neural Re-ranking:** As an initial ranking baseline the BM25 model from the traditional IR approach is used. The input is processed as a single concatenated input and fed into the Cross-encoder `cross-encoder/ms-marco-MiniLM-L6-v2` to allow for learning intricate contextual relationships. In a final step the model is fine-tuned using up to 50 hard negative
pairs from the initial BM25 rankings.

# Licensing

Please check the task-specific directory for the licensing of the respective dataset.

# Credits

**Lab Organizers:** Please find on the task website: https://checkthat.gitlab.io/
