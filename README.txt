DMML Project (Predictive Analytics for Municipal Operations: A Multi-Dataset Study ofNew York City)
====================================

Project Description
-------------------
This project processes and analyzes multiple datasets using a structured 
approach. The workflow includes data loading, cleaning, preparation, 
and analysis steps.

Files Processed
---------------
- Open_Restaurants_Inspections.csv
- Motor_Vehicle_Collisions_-_Crashes.csv
- NYC_street_segment.csv
- Facilities_Database_20251208.csv

Processing Steps
----------------

Step 1: Data Loading and Initial Analysis
- Loaded 4 CSV files with different encodings
- Dataset sizes range from 34,708 to 2,225,404 records
- Columns range from 18 to 54 features per dataset
- Total missing values identified across all datasets

Step 2: Data Cleaning Operations
For each dataset:
- Removed columns with more than 50% missing data
- Filled remaining missing values:
  - Numeric columns: used median values
  - Categorical columns: used mode or placeholder values
- Processed date columns and extracted features (year, month, day, weekday)
- Capped outliers in numeric columns using IQR method

Step 3: Data Preparation
- Created training and testing splits (80/20 ratio)
- Identified target variables for each dataset
- Saved cleaned datasets and splits

Step 4: Analysis Preparation
- Loaded cleaned datasets for further analysis
- Created summary statistics
- Saved data samples for review

Dataset Statistics After Processing
-----------------------------------

Facilities Database
- Records: 34,708
- Features: 37
- Memory: 58.45 MB
- Missing values handled: 33,771

Restaurant Inspections
- Records: 81,553
- Features: 18
- Memory: 49.06 MB
- Missing values handled: 8,089

Street Segment Data
- Records: 90,327
- Features: 52
- Memory: 58.68 MB
- Missing values: 0 after cleaning

Vehicle Collisions
- Records: 2,225,404
- Features: 30
- Memory: 1724.06 MB
- Missing values handled: 3,086,844

Output Structure
----------------
The project creates organised output directories:

Cleaned Data Files
Contains processed versions of all datasets with cleaned data

Data Splits
Training and testing datasets for machine learning preparation

Analysis Reports
Summary files documenting processing results and data characteristics

Machine Learning 8 model Results
Initial analysis outputs and dataset summaries

Technical Implementation
------------------------

Data Loading Features
- Multiple encoding support (UTF-8, Latin-1, ISO-8859-1, CP1252)
- Low-memory reading for large files
- Automatic file detection

Cleaning Methods
- Column removal based on missing data thresholds
- Statistical imputation for missing values
- Date parsing and feature extraction
- Outlier detection and capping

Preparation Functions
- Random shuffling with fixed seed
- Automated train/test splitting
- Target variable identification
- Feature/target separation

Key Results
-----------

Columns Removed
- Restaurant data: 2 columns removed
- Collision data: 7 columns removed
- Street data: 2 columns removed
- Facilities data: 1 column removed

Outliers Processed
Multiple numeric columns across all datasets had outliers capped 
using statistical methods

Target Variables Identified
Automatic detection identified appropriate target variables for 
each dataset's analysis

File Management
---------------
All outputs are saved with descriptive names in organized directory structure:
- Processed datasets
- Training and testing splits
- Summary reports
- Analysis samples

Requirements
------------
Python with these libraries:
- pandas for data manipulation
- numpy for numerical operations
- matplotlib for visualization
- seaborn for statistical graphics
- SHAP/LIME for explainability approach 

Usage Notes
-----------
1. Place source CSV files in specified directory
2. Run processing steps sequentially
3. Review generated reports and outputs
4. Use cleaned data for further analysis

Processing Summary
------------------
The project successfully processed four diverse datasets, handling 
different data types, sizes, and quality issues. All data is now 
prepared for subsequent analysis tasks.

Directory Structure
-------------------
dataset/
├── cleaned/
│   ├── Open_Restaurants_Inspections_processed.csv
│   ├── Motor_Vehicle_Collisions_-_Crashes_processed.csv
│   ├── NYC_street_segment_processed.csv
│   └── Facilities_Database_20251208_processed.csv
├── splits/
│   ├── [dataset_name]_train.csv
│   └── [dataset_name]_test.csv
├── reports/
│   └── processing_summary.txt
└── ml_results/
    ├── [dataset_name]_processed_sample.csv
    └── all_datasets_summary.csv

