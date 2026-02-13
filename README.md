# Turkish–English Intra-Word Code-Switching Corpus

An annotated corpus of Turkish–English intra-word code-switching compiled from Reddit data and annotated using the TREN system. The corpus provides token-level language labels, Leipzig-based morphological glossing for intra-word structures and a structured metadata system linking each sentence to its original subreddit source.

---

## Overview

This repository contains a dataset focusing specifically on intra-word code-switching, where an English lexical stem combines with Turkish morphological suffixes. The corpus was created as part of a research project on Turkish–English code-switching and was fully annotated using the TREN annotation system. The corpus contains 236 intra-word code-switching instances and a total of 3,132 tokens.

The dataset includes:

• Token-level language labels  
• Morphological glossing following Leipzig Glossing Rules  
• Matrix and Embedded Language information  
• Sentence-level identifiers  
• Structured source metadata  
• Raw subreddit data batches  

---

## Data Collection

All data were collected from publicly available Reddit posts using the Reddit API through Python-based data scripts.Subreddits were collected in structured batches. Each raw data file contains three subreddits grouped together.

Example batch structure:

"Bogazici", "CodingTR", "AnketTR"

Each batch is stored as:

raw_subreddit_data_1.txt  
raw_subreddit_data_2.txt  
raw_subreddit_data_3.txt  
...

Each batch contains the full raw textual data. You can find associated subreddit-level metadata in subreddits_metadata.txt file.

---

## Corpus Structure

The repository contains four main data components:

1. Annotated Dataset  
2. Annotated Dataset with Metadata  
3. Raw Extracted Text  
4. Raw Subreddit Batch Files and Metada file

### 1. Annotated Dataset

File example:

intraCS_annotated_data.csv  
intraCS_annotated_data.txt  

Contains:

• SentenceID  
• Token  
• Item  
• Label  
• Gloss  

Each row corresponds to a token-level annotation.

### 2. Annotated Dataset with Metadata

File example:

intraCS_with_metadata.txt  

This file includes:

• SentenceID  
• Subreddit name  
• Post-level metadata  
• Contextual information  

This file acts as a bridge between the annotated corpus and the original Reddit source.

### 3. Raw Extracted Text

File example:

intraCS_raw.txt  

Contains the raw sentences selected for intra-word code-switching analysis before annotation.

### 4. Raw Subreddit Batch Files

Files:

from raw_subreddit_data_1.txt  to raw_subreddit_data_14.txt  

Each file contains full raw text and sentence environment.

Each batch corresponds to three subreddits collected together.

### 5. Subreddit Metadata

This file contains structured metadata for each subreddit batch included in the corpus, specifying subreddit names, collection timeframes, and batch groupings in order to trace each sentence back to its original Reddit source environment. 
• Subreddit-level grouping  
• Metadata entries  
• Batch-specific numbering  

---

## Metadata Navigation System

The corpus follows a structured multi-layer traceability system.

The corpus follows a structured multi-layer traceability system.

To locate the original context of a sentence:

Step 1: Identify the SentenceID in the annotated dataset.  

Step 2: Locate the same SentenceID inside the metadata file (`intraCS_with_metadata.txt`).  

Step 3: From that metadata entry, identify the subreddit name.  

Step 4: Open `subreddits_metadata.txt` and locate the subreddit.  
        The file lists subreddits together with their group number (batch ID).  

Step 5: Use the group number to determine the corresponding `raw_subreddit_data_X.txt` file.  
        Each group number directly matches a specific raw subreddit batch file.  

Step 6: Open the relevant `raw_subreddit_data_X.txt` file and locate the subreddit section to retrieve the original sentence context.  

This layered mapping system ensures transparent data provenance and full reproducibility of each annotated intra-word code-switching instance.
This multi-layered structure ensures transparency and reproducibility of the dataset.

---

## Annotation Format

Token-level annotation includes:

Label categories:

TR = Turkish  
EN = English  
MIXED = Intra-word code-switching  
UID = Unidentified item  
NE = Named entity  
LANG3 = Third language  
OTHER = Numbers, punctuation marks, symbols and non-lexical items  

Gloss column contains morphological segmentation following Leipzig Glossing Rules.

---

## Methodology of Data Collection

Data were retrieved using the Reddit API via Python scripts.

Procedure:

• Subreddits were selected based on relevance to Turkish–English bilingual usage.  
• Posts and comments were programmatically retrieved.  
• Texts were filtered for potential intra-word code-switching patterns.  
• Selected sentences were manually verified.  
• Annotation was performed using the TREN application.  

This process ensured both computational scalability and manual linguistic validation.

---

## Ethical Considerations

All data were collected from publicly available Reddit content. No private messages or restricted data were accessed. Usernames and personally identifying information were not included in the annotated dataset. This corpus is for academic and research purposes.

---

## License

Creative Commons Attribution 4.0 International (CC BY 4.0)
Copyright (c) 2026 Berkay Bostan
This work is licensed under the Creative Commons Attribution 4.0 International License.
You are free to share and adapt the material for any purpose, even commercially, under the condition that appropriate credit is given.
To view a copy of this license, visit:
https://creativecommons.org/licenses/by/4.0/

### Third-Party Content Notice

The textual data contained in this corpus was collected from publicly accessible Reddit posts using the official Reddit API. 
Copyright of the original Reddit content remains with the respective Reddit users.  
Use of the corpus is therefore also subject to Reddit’s Terms of Service and applicable platform policies.
The corpus creators do not claim ownership over the original Reddit content.  
This license applies to the structured dataset, annotations, and corpus design.
