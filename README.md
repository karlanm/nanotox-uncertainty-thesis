# Computational Toxicology: ML Models for Metal-Oxide Nanoparticle Cytotoxicity Prediction

Repositorio de reproducibilidad para la tesis de Karla Mosquera (Yachay Tech), "Computational toxicology: Machine learning for predicting NPs cytotoxicity", incluyendo cuantificación de incertidumbre bayesiana.

## Contenido

| Archivo | Descripción |
|---|---|
| `ML_new_dataset_FIXED.ipynb` | Split group-aware, SMOTE post-split, entrenamiento y evaluación de Random Forest / SVM / MLP sobre el subconjunto curado de 483 nanopartículas metal-óxido |
| `ToxicityModel_Flujo_Python_FIXED.ipynb` | Pipeline alternativo que incluye `coresize`, con análisis de dominio de aplicabilidad (distancia de Mahalanobis) |
| `Qsar_FIXED.ipynb` | Análisis de importancia de variables multi-método (Pearson, Spearman, información mutua, Random Forest, permutación, VIF inverso), incluyendo chequeos de robustez decorrelacionados |
| `bayes_FIXED.ipynb` | Red Neuronal Bayesiana (Pyro/PyTorch): entrenamiento SVI, muestreo genuino del posterior, cuantificación de incertidumbre, calibración, y demostración del pipeline de dos pasos |

## Datos necesarios

Estos dos archivos deben colocarse en el mismo directorio que los notebooks (no se incluyen en este repositorio por tamaño/licencia de los datos originales — ver "Fuente de datos" abajo):

- `dataset_nanotox_datos_originales.xlsx` (483 filas, usado por `ML_new_dataset_FIXED.ipynb` y `ToxicityModel_Flujo_Python_FIXED.ipynb`)
- `NanoTox__unidas.csv` (1,363 filas complete-case, usado por `Qsar_FIXED.ipynb` y `bayes_FIXED.ipynb`)

## Fuente de datos

Ambos archivos derivan del dataset NanoTox de Subramanian, N. A., & Palaniappan, A. (2021). *NanoTox: Development of a Parsimonious In Silico Model for Toxicity Assessment of Metal-Oxide Nanoparticles Using Physicochemical Features*. ACS Omega, 6(18), 11729–11739. https://doi.org/10.1021/acsomega.1c00753

## Entorno

Todos los notebooks fueron ejecutados de punta a punta ("Restart & Run All") con Python 3.12 y las siguientes librerías principales:

```
pandas
numpy
scikit-learn
imbalanced-learn
torch
pyro-ppl
statsmodels
matplotlib
seaborn
scipy
```

Ver `requirements.txt` (o `pyproject.toml` + `uv.lock` si usas `uv`) para versiones exactas.

Semilla aleatoria fija (`random_state=42` / `torch.manual_seed(42)`) en todos los pasos estocásticos para reproducibilidad.

## Cómo citar

Si usas este código, por favor cita:

```
Mosquera, K. (2026). [Computational toxicology: Machine learning for
predicting NPs cytotoxicity]. Yachay Tech University.
Código: [DOI DE ZENODO AQUÍ UNA VEZ GENERADO]
```

