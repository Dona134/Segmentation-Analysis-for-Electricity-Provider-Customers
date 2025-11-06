# Segmentation-Analysis-for-Electricity-Provider-Customers

This project is part of a Marketing Analytics course and contains exploratory data analysis and customer segmentation of survey data related to electricity consumption. The goal is to identify distinct customer segments based on consumption behavior, preferences, and survey responses to inform targeted marketing and product design.

## Table of contents
- Overview
- Key objectives
- Features & analyses
- Data
- Installation
- Usage
  - Running the notebooks
  - Reproducing results
- Methodology
- Typical outputs
- Repository structure
- Privacy & ethics
- Contributing
- License
- Contact

## Overview
The analysis walks through data cleaning, feature engineering, exploratory data analysis (EDA), clustering and profiling. Clusters are interpreted and actionable recommendations for marketing, pricing, and communication strategies are suggested.

## Key objectives
- Clean and prepare survey and usage data for analysis
- Engineer features that summarize electricity consumption and preferences
- Apply clustering algorithms to uncover customer segments
- Profile segments by demographics, attitudes, and usage patterns
- Provide marketing recommendations per segment

## Features & analyses
- Data cleaning and missing-value handling
- Feature engineering (e.g., normalized consumption, tariff preferences, appliance ownership indicators)
- Dimensionality reduction (PCA) and visualization
- Multiple unsupervised algorithms (KMeans, Agglomerative, DBSCAN, Gaussian Mixture)
- Cluster evaluation (silhouette score, Calinski-Harabasz, Davies-Bouldin)
- Segment profiling and visual summaries (boxplots, bar charts)
- Simple rule-based labeling and recommendations for each segment

## Data
- Expected inputs: survey CSV(s) and optional meter/consumption CSV(s).
- Typical columns: respondent id, age, gender, household size, location, consumption metrics (kWh), appliance ownership, tariff choice, environmental attitudes, willingness-to-pay.
- Place raw data in a `data/raw/` folder and processed files in `data/processed/`.
- If the dataset is sensitive or under NDA, keep only anonymized, aggregated samples in the repo.

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Dona134/Segmentation-Analysis-for-Electricity-Provider-Customers.git
cd Segmentation-Analysis-for-Electricity-Provider-Customers
```

2. (Recommended) Create and activate a virtual environment:
```bash
python -m venv .venv
# macOS/Linux
source .venv/bin/activate
# Windows
.venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```
Typical packages used:
- pandas, numpy
- scikit-learn
- matplotlib, seaborn, plotly
- jupyter, notebook

If there is no requirements file, install minimal set:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn plotly jupyter
```

## Usage

### Running notebooks
Open JupyterLab or Notebook and run the notebooks sequentially:
```bash
jupyter lab
```
Notebooks are written to be executed top-to-bottom:
1. 00_data_overview_and_cleaning.ipynb — data ingestion and cleaning
2. 01_feature_engineering.ipynb — create modeling features
3. 02_clustering_analysis.ipynb — model fitting and cluster evaluation
4. 03_cluster_profiling_and_recommendations.ipynb — interpretation and outputs

### Reproducing results
- Ensure data is placed in `data/raw/`.
- If random initialization affects clustering, set a random seed in the notebook (`np.random.seed(42)` and algorithm random_state parameters).
- Use the provided processed data files in `data/processed/` if available.

## Methodology
- Preprocess categorical and numerical features (encoding, scaling).
- Use silhouette and elbow methods to choose the number of clusters.
- Validate clusters with internal metrics and domain interpretability.
- Profile clusters using summary statistics and visualizations.

## Typical outputs
- Cluster labels per respondent (CSV)
- Summary tables of cluster characteristics
- Visualizations (PCA / t-SNE plots, feature importance charts)
- A short recommendations section with suggested customer outreach strategies

## Repository structure (example)
- notebooks/
  - 00_data_overview_and_cleaning.ipynb
  - 01_feature_engineering.ipynb
  - 02_clustering_analysis.ipynb
  - 03_cluster_profiling_and_recommendations.ipynb
- data/
  - raw/
  - processed/
- results/
  - clusters.csv
  - figures/
- requirements.txt
- README.md

Adjust to match the actual filenames in the repo.

## Privacy & ethics
- Survey and consumption data are potentially sensitive; do not commit raw personally identifiable information (PII) to a public repository.
- Anonymize or aggregate data before sharing.
- Document any consent/background needed for data use.

## Contributing
- Open an issue to propose changes or report bugs.
- Fork the repo and submit pull requests for new analyses or improvements.
- Add unit tests or reproducible examples when changing core processing steps.

## License
If you want to share this work, include a LICENSE file (e.g., MIT). If none is present, default copyright applies.

## Contact
Author: Dona134