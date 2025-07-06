# Predicting Elastic Properties of Materials using Machine Learning

This project focuses on predicting the **bulk modulus** and **shear modulus** of inorganic crystal materials using machine learning techniques. The dataset was obtained from the [Materials Project](https://materialsproject.org/) and includes over 13,000 entries.

We explore both **Random Forest** and **Linear Regression** models using 150+ compositional features generated through the **Matminer** library.

---

## 📁 Repository Structure

```
├── elastic_properties_dataset.csv       # Source dataset (downloaded from Materials Project)
├── bulk_modulus_random_forest.ipynb     # Bulk modulus prediction using Random Forest
├── bulk_modulus_regression.ipynb        # Bulk modulus prediction using Ridge Regression
├── shear_modulus_random_forest.ipynb    # Shear modulus prediction using Random Forest
├── shear_modulus_regression.ipynb       # Shear modulus prediction using Ridge Regression (to be added)
├── README.md                            # This file
```

---

## 🔍 Features Used

- Features were extracted from the `formula` column using **Matminer**'s `ElementProperty` featurizer (Magpie preset)
- \~150 composition-based features including:
  - Atomic number stats (mean, max, range, etc.)
  - Atomic radius
  - Ionization energy
  - Thermal conductivity

---

## ⚙️ Models Trained

For both **bulk modulus** and **shear modulus**, we trained:

- **Random Forest Regressor**
- **Ridge Regression**

### Training Pipeline:

- Remove null and outlier targets (`0 < modulus < 500` GPa)
- 60% Training, 20% Validation, 20% Testing split
- Evaluate models with:
  - R² score
  - MAE
  - RMSE
  - Predicted vs Actual plots
  - Feature importance and PCA analysis

---

## 📊 Results Snapshot (Random Forest - Example)

| Property      | Model         | R² (Test) | MAE     | RMSE    |
| ------------- | ------------- | --------- | ------- | ------- |
| Bulk Modulus  | Random Forest | 0.94      | \~6 GPa | \~9 GPa |
| Shear Modulus | Random Forest | 0.93      | \~5 GPa | \~8 GPa |

*Results vary depending on exact cleaning and random seed.*

---

## 📦 Dependencies

Install using pip:

```bash
pip install matminer pymatgen scikit-learn pandas matplotlib seaborn
```

---

## 📘 Acknowledgements

- Dataset: [Materials Project](https://materialsproject.org/)
- Featurization: [Matminer](https://hackingmaterials.lbl.gov/matminer/)
- Modeling: [scikit-learn](https://scikit-learn.org/)

---



