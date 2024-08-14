# Case Study 2: Clustering Diabetic Patient Encounters
This study clusters diabetic patients based on their hospital data to identify patterns and aid in healthcare management.

Python Libraries Used: **Numpy**, **Pandas**, **Matplotlib**, **Seaborn**

## Dataset
- File: `D2.csv`
- Key Attributes: time_in_hospital, num_lab_procedures, num_medications, age, race

## Data Pre-processing
- Corrected Data Types: Converted identifiers to categorical.
- Missing Data: Filled missing categorical values with mode.
- Outliers: Managed outliers in key variables.
- Age Mapping: Converted age ranges to numerical values.

## Clustering Model
### Method
- Algorithm: Partitioning (suitable for spherical clusters).
- Optimal Clusters: Determined K = 3 using elbow and silhouette methods.
- Scaling: Standardization applied to improve cluster quality.
### Results
- **Cluster 0**: Elderly patients with short stays, few tests/medications.
- **Cluster 1**: Middle-aged to older patients with longer stays, more tests/medications.
- **Cluster 2**: Younger patients with short stays, fewer medications.
### Race Analysis
- Method: K-prototype algorithm.
- Findings: Similar clusters as initial model; racial patterns less clear.

# Insights
The results of this task reveal the underlying pattern and provides valuable insights for the relevant stakeholder to make decisions to improve the hospital facilities management. 

They can allocate an appropriate number of resources and staff in each hospital department. For example, for the middle-aged to older patients with longer hospital stays and more lab tests and medications, the manager may allocate more doctors, nurses and other healthcare staff, also more stock items for better patient care.

The insurance companies may find these results useful to predict the hospital cost of these different groups of patients for optimizing insurance limits. For example, young patients with shorter hospital stays and fewer medicines may have lower healthcare costs.


