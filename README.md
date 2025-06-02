# -Task-1-Data-Cleaning-and-preprocessing
# Netflix Dataset Cleaning & Preprocessing

## Overview
This project focuses on cleaning and preprocessing a Netflix dataset to ensure consistency, accuracy, and usability for data analysis. The dataset contains multiple columns including `show_id`, `type`, `title`, `director`, `cast`, `country`, `date_added`, `release_year`, `rating`, `duration`, `listed_in`, and `description`.

## Data Cleaning Steps
### 1. **Handling Missing Values**
- Identified missing values using `.isnull().sum()`.
- Filled missing values in categorical columns (`country`, `rating`) using `"Unknown"` as a placeholder.
- Used median imputation for numerical columns like `release_year`.

### 2. **Handling Duplicates**
- Checked for duplicate entries using `.duplicated().sum()`.
- Removed duplicate records using `.drop_duplicates()`.

### 3. **Standardizing Formats**
- Converted `date_added` to **datetime format** for consistency.
- Ensured `release_year` was stored as an integer (`astype(int)`).
- Stripped extra spaces and standardized text fields (`title`, `director`, `cast`) using `.str.strip().str.title()`.

### 4. **Cleaning Rating Column**
- Standardized ratings into broader categories for easier classification:
  - `"TV-MA"` → `"Mature"`
  - `"R"` → `"Restricted"`
  - `"PG-13", "TV-14"` → `"Teen"`
  - `"PG", "TV-PG"` → `"Parental Guidance"`
  - `"G", "TV-G"` → `"General"`
  - `"TV-Y7", "TV-Y7-FV"` → `"Children 7+"`
  - `"TV-Y"` → `"Children"`
  - `"NC-17"` → `"Adults Only"`
  - `"UR", "NR"` → `"Unrated"`

### 5. **Final Dataset Preparation**
- Ensured a clean dataset with well-structured data by applying all preprocessing steps.
- Verified changes with `.value_counts()` to confirm successful transformations.

## Usage
This dataset is now ready for:
- **Exploratory Data Analysis (EDA)**
- **Visualization & Insights**
- **Machine Learning Applications**
