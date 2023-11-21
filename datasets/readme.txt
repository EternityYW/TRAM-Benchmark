TRAM is a temporal reasoning benchmark composed of ten datasets, encompassing various temporal aspects of events, designed to facilitate a comprehensive evaluation of the temporal reasoning capabilities of large language models.

=====================
DIRECTORY STRUCTURE
=====================
├── data
│   ├── ambiguity_resolution.zip
|   ├── arithmetic.zip
|   ├── causality.zip
|   ├── duration.zip
|   ├── frequency.zip
|   ├── nli_mcq.zip / nli_saq.zip
|   ├── ordering.zip
|   ├── relation.zip
|   ├── storytelling.zip
│   └── typical_time.zip
└── readme.txt

=============
DATASET FILES
=============
The dataset files are 11 .zip files.
Each .zip file contains two to four .csv files. For the .zip file with two files, it has data_mcq.csv and data_shots_mcq.csv. Here, "data" corresponds to the name of the .zip file itself, and "MCQ" represents multiple-choice questions.
 * data_mcq.csv: the test set
 * data_shots.csv: the 5-shot development set (per category/source)
All the questions are in the format of MCQs. Every question has a unique correct answer.

In each file (data_mcq.csv and data_shots_mcq.csv), the typical format is:
 * Question: May have multiple columns if there are context sentences.
 * Options: 2-4 options from all datasets. Format: Option A, Option B, etc.
 * Answer: The correct answer (e.g., A, B, etc.)
 * Source / Category: If the final column in a data file is labeled "Category", it indicates multiple subtasks. If it's labeled "Source", it indicates the same problem type, but derived from various existing datasets.

In the .zip file containing four files, in addition to the two files mentioned above, there are data_saq.csv and data_shots_saq.csv. Here, 'saq' represents short-answer questions.
In each file (data_saq.csv and data_shots_saq.csv), the typical format is:
 * Question: May have multiple columns if there are context sentences.
 * Answer: The correct answer (natural texts)
 * Source / Category: If the final column in a data file is labeled "Category", it indicates multiple subtasks. If it's labeled "Source", it indicates the same problem type, but derived from various existing datasets.

In addition to the above, for causality.zip, we have causality_mirrored_mcq.csv, which contains a mirrored instance for each original instance found in causality_mcq.csv and causality_shots_mcq.csv.


===========
EVALUATION
===========
The majority of tasks employ accuracy as the evaluation metric due to their straightforward MCQ structure. However, for tasks like "relation" and "temporal NLI", which exhibit an imbalanced label distribution inherent to their fixed class structure, both accuracy and the F1 score are utilized, even when they are presented as MCQs.

===========
DATA CONSTRUCTION
===========
TRAM incorporates existing natural language understanding datasets, human-crafted templates and questions, web sources, and program generation, comprising a total of 526.1k questions. Answers have been derived through a combination of expert annotations and programmatic generation.
Please refer to Appendix A of the paper for the detailed data construction process.

      
      
