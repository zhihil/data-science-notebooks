# Heart Disease

---

## Overview

This notebook is run on the [Heart Disease UCI Dataset](https://www.kaggle.com/ronitf/heart-disease-uci) from Kaggle. You can download the `heart.csv` dataset from this link.



## Setup

You can view (but not write) the notebooks on [Google Colab](https://colab.research.google.com/notebooks/intro.ipynb#recent=true) using the following [link](https://colab.research.google.com/drive/1G-k_pn-DD09SHHeZ0Lpk5k696ichqXa1?usp=sharing).

If you want to run this notebook, then you'll have to download the data and setup the proper folder structure.

1. Open this share [link](https://colab.research.google.com/drive/1G-k_pn-DD09SHHeZ0Lpk5k696ichqXa1?usp=sharing) to see the `heart-disease.ipynb` file on Google Colab.
2. Click File > Save a copy in Drive to duplicate the `heart-disease.ipynb` notebook to your personal drive.
3. Move your copy of `heart-disease.ipynb` into a folder called  `"My Drive/Colab Notebooks/heart-disease"`.
   1. For reference, `"My Drive"` is the root of your Google Drive filesystem, as shown below:

<img width="907" alt="Screen Shot 2021-05-06 at 10 27 22 AM" src="https://user-images.githubusercontent.com/32404412/117316574-b6123880-ae56-11eb-8a28-cce9cdc958b8.png">

6. Open the Kaggle competition link given in the Overview
7. Click the Data tab
8. Download the `heart.csv` dataset
9. Put `heart.csv` into  `"My Drive/Colab Notebooks/heart-disease"`.
10. Open the notebook and run all of the cells. 
11. Authorize the notebook to read/write to your Google Drive
    1. The notebooks need this permission because they will read `heart.csv` from Google Drive and output the predictions to a `.csv` file. The code-cell that requests this authorization is shown below:

<img width="671" alt="Screen Shot 2021-05-06 at 10 30 05 AM" src="https://user-images.githubusercontent.com/32404412/117316506-a98de000-ae56-11eb-8a02-d38c56ffd79f.png">



## Skills Demonstrated

For recruiters, the following skills are demonstrated by this notebook. This list is not comprehensive, but summarizes most of what is shown in the notebook.

- "Basic Exploration"
  - Researching the problem and the domain before starting any "actual" work.
  - Reading the feature documentation to understand the data type of each feature, assigning it to an informal category for later reference, and assigning a hypothetical importance of the predictor.
- "Identifying Skewed Classes"
  - Identifying if the classification problem is a skewed classes problem. 
  - Using precision to minimize the number of false positives. Using recall to minimize the number of false negatives. Using F1 score as a combined indicator to balance precision and recall.
- General principles
  - Avoiding train-test contamination by fitting on the training dataset, rather than training + validation/test. 
  - Plotting learning curves to identify overfitting and underfitting.
- Exploratory data analysis
  - Univariate analysis
    - Summary statistics for predictors and the target
    - Histograms to identify the distribution of the feature, e.g, is it Normal or not?
    - Using skewness and kurtosis as supplementary evidence of a Normal distribution for a feature.
  - Bivariate analysis
    - Cramer's V for determining strength of association between categorical variables.
  - Multivariate analysis
    - Pearson correlation for identify the strength of linear relationships between numerical features and identifying multicollinearity.
    - Using boxplots to visualize possible relationships between categorical and continuous variables.
    - Using scatterplots to visualize possible relationships between continuous variables.
  - Visualization
    - Using Principal Component Analysis to compress high-dimensional data into 2D or 3D to have some limited visualization on its structure.
- General programming skills
  - Creating utility functions like `construct_contigencny_table` or `cramers_v` to reduce duplicated code.
- `pandas`
  - Loading data with `pd.read_csv`
  - Separating object and numerical columns.
  - Combining columns with `pd.merge` 
- `scikit-learn`
  - `model_selection.train_test_split` - Avoids train-test contamination.
  - `compose.ColumnTransformer` - Using `ColumnTransformer` to apply transformations to specific columns.
  - `preprocessing.StandardScaler` - Scaling features for gradient-based learning models
  - `pipeline.Pipeline` - Using `Pipeline` to compose transformations and simplify the code
  - `decomposition.PCA` - Using `PCA` for data visualization of high-dimensional features.
  - Writing custom `Pipeline` classes - See `class ColumnDropper`
- `seaborn`
  - `pairplot` 
- Models
  - `LogisticRegression` - Using the model and validation its assumptions: no multicollinearity, large sample size, independent observations, binary target, linearity of predictors and logits, no outliers.
  - Support Vector Machines - Using the model and tuning the $C$ hyperparameter for regularization.
  - K-Nearest Neighbor Classifier
  - Random Forest Classifier
  - Artificial Neural Network with 1 hidden layer.
- Model selection
  - Cross-validation with `RepeatedKFold` to avoid unstable and unreliable generalization estimates.
  - Hyperparameter tuning using cross-validation techniques, e.g, tuning the $C$ parameter for an SVM.