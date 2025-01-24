# bayesian-model-heart-disease

This repository contains the implementation and analysis of a probabilistic graphical model (PGM), specifically Bayesian Networks, to assess the risk of heart disease based on various factors like age and cholestrol levels. This project aims to explore the functionality and application of Bayesian Networks.

## Project Overview
The goal of the project is to model the relationships between various risk factors (e.g., age, cholesterol level, blood pressure) and the likelihood of heart disease. The implementation includes:
- Data preprocessing, including binning continuous variables for compatibility with Bayesian Networks.
- Building and fitting a Bayesian Network structure.
- Performing inference to assess the probability of heart disease under different scenarios.
- Visualizing the Bayesian Network structure and data insights.

## Implementation 
1. **Data Preprocessing and Analysis**:
   - Handling missing and duplicate values.
   - Equal-frequency binning for continuous variables to enable Bayesian Network modeling.
   - Correlation analysis and heatmap visualization to identify relationships between variables.

2. **Bayesian Network Implementation**:
   - Constructed using the `pgmpy` library.
   - Defined Conditional Probability Tables (CPTs) based on dependencies between variables.
   - Performed inference using Variable Elimination.

3. **Visualization**:
   - Visualized data distributions (e.g., target class balance).
   - Displayed the Bayesian Network structure with labeled nodes and edges.

## Key Results
- Modeled the relationship between age, cholesterol, and heart disease risk.
- Demonstrated how variations in age and cholesterol levels influence the probability of heart disease.
- Provided actionable insights for risk assessment using Bayesian inference.

## Libraries Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- pgmpy

### Usage
Run the Jupyter Notebook to explore the implementation and results:
```bash
jupyter notebook bayesian_model.ipynb
```

### Example Inference
#### Probability of Heart Disease
```python
from pgmpy.inference import VariableElimination

# Example: Probability of heart disease given age=60 and cholesterol=260
infer = VariableElimination(model)
age_value = 60
chol_value = 260

# Map values to bins
age_bin = np.digitize(age_value, bin_edges['age']) - 1
chol_bin = np.digitize(chol_value, bin_edges['chol']) - 1

result = infer.query(variables=['target'], evidence={'age': age_bin, 'chol': chol_bin})
print(result)
```

## Repository Structure
```
bayesian-model-heart-disease/
├── README.md
├── bayesian_model.ipynb
├── data/
│   └── heart_disease.csv
```

- **bayesian_model**: Jupyter Notebook with the complete implementation.
- **data/**: Folder containing the dataset.
