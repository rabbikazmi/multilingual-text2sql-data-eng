# AISAFETY: Multilingual Text-to-SQL Pipeline

This repository contains the processing notebooks, dataset tracking variables, and evaluation logs used to build a robust, multi-lingual Text-to-SQL system with integrated security filters. 


## Directory Overview

```text
├── README.md
├── notebooks/       # Implementation and data engineering scripts
├── data/            # Generated training, validation, and security datasets
└── logs/            # Zero-shot model testing metrics
```

#### Data Folder Catalog
1. multilingual_sql_security_dataset (.csv / .json)
- An unrolled dataset combining multi-lingual baseline translations with malicious SQL injection strings.
- 20,000 rows (14,000 benign, 6,000 malicious).

2. spider_multilingual_mapped_train (.csv / .json)
- The translation corpus linked directly to its relational database backend metadata markers.
- Matches baseline Spider translation array footprint.

3. spider_multilingual_unmapped_base (.csv / .json)
- The raw cross-lingual text tiers decoupled from database files.
- Matches baseline source text variants.

#### Notebooks Folder Catalog

- dataset_cleaning.ipynb: Standardizes missing text lines and fixes format anomalies.

- dataset_eval.ipynb: Runs evaluation statistics over data frames to check text metrics.

- hinglish_query_corpus.ipynb: Generates and validates the custom Hinglish and phonetic Hindi text variants.

- mapping_db.ipynb: Attaches specific Spider database schemas to raw prompt strings.

- security_dataset_merge.ipynb: Mixes the safe dataset with SQLShield, upsamples data pools, and outputs the final 70/30 security file.

#### Logs Folder Catalog
- qwen_1.5b_zero_shot_detailed_logs.csv: Performance logging metrics tracking structural accuracy and error profiles during early zero-shot testing runs on the Qwen architecture.