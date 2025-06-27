The goal of this project was to analyze multiple NLP architectures and their usefulness in reframing negative thoughts into positive ones. 

The dataset used, and modified, was the PATTERNREFRAME dataset created for "Training Models to Generate, Recognize, and Reframe Unhelpful Thoughts" by Maddela et al.[10] (2023).
The "thought" and "reframe" fields were used as the input (negative thought) and output (reframed thought), respectively. For some models, additional fields from the dataset were used to see
how it affected the model's output, identified by "More Detailed Prompt" in this file, and using the "all_[DATA SPLIT]_data" naming convention in the code. It added on the "persona" and "pattern"
fields from the original dataset, as those fields contained more information about the hypothetical person expressing the thought, as well as the thought pattern/cognitive distortion they experience.
Due to the dataset being pre-split in a 20/10/70 train/valid/test split, for this project, the files were reorganized to be a 70/20/10 train/valid/test split to follow more standard
dataset splitting conventions.

The models tested in this project are as follows:
Deterministic GRU-based RNN
Non-Deterministic GRU-based RNN
Deterministic Seq2Seq with Bahdanau Attention
Non-Deterministic Seq2Seq with Bahdanau Attention
Deterministic T5 Transformer
Non-Deterministic T5 Transformer
Deterministic T5 Transformer with More Detailed Prompt (additional information added to see if output was enhanced)
Non-Deterministic T5 Transformer with More Detailed Prompt

The evaluation metrics chosen to analyze these models are Semantic Analysis, Cosine Similarity, and Manual Evaluation. This mix of metrics was chosen to ensure a comprehensive analysis of each model's output.

The codebase is organized as follows (tab indicates subfolder within above folder):
code - the Jupyter Notebook files for each model are stored here, as well as a CSV file visualizing each model's output compared to the dataset's negative and reframed thoughts. 
  data - contains all cleaned datasets (in CSV files) generated and used, both with and without extra fields for T5 Transformers. also contains JSON files to remove contractions and other words from dataset for easier training (included in original dataset)
    reframe_thoughts_dataset - original txt files of reorganized dataset splits that were used to generate the CSV file datasets for the rest of the project.
  data(ORIGINAL) - contains JSON files to remove contractions and other words from dataset for easier training (included in original dataset)
    reframe_thoughts - contains original, untouched dataset txt files
  model_outputs - contains all generated reframed thought outputs from each model, as well as true text (reframed thought from dataset) and sometimes containing original text (negative thought from dataset)
  results - contains in-depth results for each model's evaluation metrics, as well as one file summarizing the results for all metrics for each model. also contains a file with the manual evaluation results.

As stated in the description, the results and experiment were formalized and expanded upon in the research paper written for this project, which is available upon request.
