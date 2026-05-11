# UCI HAR Clustering

Clustering analysis on the UCI Human Activity Recognition (HAR) dataset using machine learning techniques.

## Overview

This project performs unsupervised clustering on human activity recognition data from smartphone sensors. The UCI HAR Dataset contains measurements from accelerometer and gyroscope sensors worn by subjects performing various activities (walking, walking upstairs, walking downstairs, sitting, standing, laying).

## Dataset

The **UCI HAR Dataset** consists of:
- **561 features** derived from accelerometer and gyroscope signals
- **10,299 samples** collected from 30 subjects
- **6 activity classes**:
  - Walking
  - Walking Upstairs
  - Walking Downstairs
  - Sitting
  - Standing
  - Laying

Data is split into training (70%) and test (30%) sets.

## Project Structure

```
UCIHarClustering/
├── UCI HAR Dataset/          # Raw dataset directory
├── UCI HAR Dataset.zip       # Compressed dataset
├── ClusteringModel.ipynb     # Main clustering analysis notebook
└── output/                   # Results and visualizations
```

## Methodology

The clustering analysis includes:

1. **Data Preprocessing**
   - Feature normalization/standardization
   - Handling missing values (if any)
   - Dimensionality reduction (if applicable)

2. **Clustering Algorithms**
   - K-Means
   - Hierarchical Clustering
   - DBSCAN (or other density-based methods)

3. **Evaluation Metrics**
   - Silhouette Score
   - Davies-Bouldin Index
   - Calinski-Harabasz Index
   - Inertia

4. **Visualization**
   - Cluster distributions
   - Feature importance
   - Performance comparisons

## Installation & Setup

### Requirements
- Python 3.7+
- Jupyter Notebook
- scikit-learn
- pandas
- numpy
- matplotlib
- seaborn

### Install Dependencies
```bash
pip install scikit-learn pandas numpy matplotlib seaborn jupyter
```

### Running the Analysis
```bash
jupyter notebook ClusteringModel.ipynb
```

## Key Features

- Comprehensive clustering analysis using multiple algorithms
- Detailed performance evaluation and comparison
- Visualization of clustering results
- Activity-wise cluster analysis
- Feature-importance analysis for clustering decisions

## Results

Results and output files are saved in the `output/` directory, including:
- Cluster assignments
- Evaluation metrics
- Visualization plots
- Performance reports

## Usage Example

```python
from sklearn.cluster import KMeans
import pandas as pd

# Load data
features = pd.read_csv('UCI HAR Dataset/train/X_train.txt', sep='\s+', header=None)

# Apply K-Means clustering
kmeans = KMeans(n_clusters=6, random_state=42)
clusters = kmeans.fit_predict(features)

# Evaluate clustering quality
from sklearn.metrics import silhouette_score
score = silhouette_score(features, clusters)
print(f"Silhouette Score: {score}")
```

## Notes

- The optimal number of clusters may vary based on the algorithm and evaluation metric used
- Dimensionality reduction (PCA) can be applied to improve computational efficiency
- Ground truth labels are available for external validation of clustering quality

## References

- [UCI HAR Dataset](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones)
- Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. "A Public Domain Dataset for Human Activity Recognition Using Smartphones." 21th European Symposium on Artificial Neural Networks, Computational Intelligence and Machine Learning, ESANN 2013.

## Author

[Dzuumirrah](https://github.com/Dzuumirrah)

## License

This project is provided as-is for educational and research purposes.

---

**Last Updated:** May 2026
