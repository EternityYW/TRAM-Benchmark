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
|   ├── nli.zip
|   ├── ordering.zip
|   ├── relation.zip
|   ├── storytelling.zip
│   └── typical_time.zip
└── readme.txt

=============
DATASET FILES
=============
The dataset files are 10 .zip files.
Each .zip file contains two .csv files: data.csv and data_shots.csv. Here, "data" corresponds to the name of the .zip file itself.
 * data.csv: the test set
 * data_shots.csv: the 5-shot development set (per category/source)
All the questions are in the format of multiple-choice questions (MCQ). Every question has a unique correct answer.

In each file (data.csv and data_shots.csv), the typical format is:
 * Question: May have multiple columns if there are context sentences.
 * Options: 2-4 options from all datasets. Format: Option A, Option B, etc.
 * Answer: The correct answer (e.g., A, B, etc.)
 * Source / Category: If the final column in a data file is labeled "Category", it indicates multiple subtasks. If it's labeled "Source", it indicates the same problem type, but derived from various existing datasets.

===========
EVALUATION
===========
The majority of tasks employ accuracy as the evaluation metric due to their straightforward MCQ structure. However, for tasks like "relation" and "temporal NLI", which exhibit an imbalanced label distribution inherent to their fixed class structure, both accuracy and the F1 score are utilized, even when they are presented as MCQs.

===========
DATA CONSTRUCTION
===========
TRAM incorporates existing natural language understanding datasets, human-crafted templates and questions, web sources, and program generation, comprising a total of 526.1k questions. Answers have been derived through a combination of expert annotations and programmatic generation.
Please refer to Appendix A of the paper for the detailed data construction process.

      
      
