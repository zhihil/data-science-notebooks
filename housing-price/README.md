# Housing Prices

---

## Overview

The notebook is for the [Housing Prices - Advanced Regression Techniques](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data) competition on Kaggle. You can also download the `train.csv` and `test.csv` files to run this notebook. My [ranking](https://www.kaggle.com/sunlightsky/competitions) for this competition as of time of writing is 3089/9629 (top 33%).



## Setup

You can view (but not write) the notebooks on [Google Colab](https://colab.research.google.com/notebooks/intro.ipynb#recent=true) using the following links:

- `model-selection` - [link](https://colab.research.google.com/drive/1w5AIptS1EI7Cffw19Kqe3bAdqBHgRMQu?usp=sharing)
- `eda` - [link](https://colab.research.google.com/drive/18rJe-y9QW6VWWT8UkdoWCXaG7uEgRlsL)

If you want to run this notebook, then you'll have to download the data and setup the proper folder structure.

1. Open this share [link](https://colab.research.google.com/drive/1w5AIptS1EI7Cffw19Kqe3bAdqBHgRMQu?usp=sharing) to see the `model-selection.ipynb` file on Google Colab.
2. Click File > Save a copy in Drive to duplicate the `model-selection.ipynb` the Jupyter Notebook to your personal drive.
3. Open this share [link](https://colab.research.google.com/drive/18rJe-y9QW6VWWT8UkdoWCXaG7uEgRlsL) to see the `eda.ipynb` file on Google Colab
4. Click File > Save a copy in Drive to duplicate the `eda.ipynb` Jupyter Notebook to your personal drive.
5. Put your copies of `model-selection.ipynb` and `eda.ipynb` into a folder called  `"My Drive/Colab Notebooks/housing-prices"`.
   1. For reference, `"My Drive"` is the root of your Google Drive filesystem, as shown below:

<img width="907" alt="Screen Shot 2021-05-06 at 10 27 22 AM" src="https://user-images.githubusercontent.com/32404412/117316574-b6123880-ae56-11eb-8a28-cce9cdc958b8.png">

6. Open the Kaggle competition link given in the Overview
7. Click the Data tab
8. Download `train.csv` and `test.csv`
9. Put `train.csv` and `test.csv` into `"My Drive/Colab Notebooks/housing-prices"`.
10. Open either notebook and hit Run All
11. Authorize the notebook to read/write to your Google Drive
    1. The notebooks need this permission because they will read `train.csv` from Google Drive and output the predictions to a `.csv` file. The code-cell that requests this authorization is shown below:

<img width="671" alt="Screen Shot 2021-05-06 at 10 30 05 AM" src="https://user-images.githubusercontent.com/32404412/117316506-a98de000-ae56-11eb-8a02-d38c56ffd79f.png">



## Skills Demonstrated

### eda.ipynb

For recruiters, the following skills are demonstrated by this notebook. This list is not comprehensive, but summarizes most of what is shown in the notebook.

- "Basic Exploration"
  - Researching the problem and the domain before starting any "actual" work.
  - Reading the feature documentation to understand the data type of each feature, assigning it to an informal category for later reference, and assigning a hypothetical importance of the predictor.
- "Constructing a Baseline Model"
  - Quickly prototyping a baseline model to drive further exploration.
- "Missing Values"
  - Investigating the "domain rationale" behind missing values. 
    - e.g. `BsmtQual` uses `"NA"` to mean that the basement does not exist. This feature should not be imputed and the `"NA"` should instead be renamed to something that isn't misinterpreted by the code.
    - e.g. `Electrical` does use `"NA"` to indicate "no information is known." Therefore, this feature can be imputed
    - e.g. `GarageYrBlt` cannot be imputed, because `"NA"` means the basement does not exist. Attempting to impute `GarageYrBlt` violates the domain rules by enforcing the assumption that every house has a garage.
- General principles
  - Avoiding train-test contamination by fitting on the training dataset, rather than training + validation/test. 
  - Plotting learning curves to identify overfitting and underfitting.
- Exploratory data analysis
  - Univariate analysis
    - Summary statistics for predictors and the target
    - Histograms to identify the distribution of the feature, e.g, is it Normal or not?
    - Using skewness and kurtosis as supplementary evidence of a Normal distribution for a feature.
  - Bivariate analysis
    - Using boxplots to visualize possible relationships between categorical and continuous variables.
    - Using regression plots to visualize possible relationships between continuous variables.
  - Multivariate analysis
    - Using Pearson correlation for identify the strength of linear relationships between numerical features and identifying multicollinearity.
    - Using Cramer's V for identifying the strength of association between categorical variables.
    - Using Kruskall-Wallis H Test to test for any statistically significant relationships between a categorical and numerical variable.
  - Visualization
    - Using Principal Component Analysis to compress high-dimensional data into 2D or 3D to have some limited visualization on its structure.
- General programming skills
  - Creating utility functions like `construct_contigencny_table` or `cramers_v` to reduce duplicated code.
- `pandas` - Loading data with `pd.read_csv`, separating object and numerical columns, etc.
- `scikit-learn`
  - `model_selection.train_test_split` - Avoids train-test contamination.
  - `compose.ColumnTransformer` - Using `ColumnTransformer` to apply transformations to specific columns.
  - `preprocessing.StandardScaler` - Scaling features for gradient-based learning models
  - `pipeline.Pipeline` - Using `Pipeline` to compose transformations and simplify the code
  - Writing custom `Pipeline` classes - See `class ColumnDropper`
- `matplotlib` - Working with low-level `matplotlib` commands to fine-tune graphs, e.g, see `plot_dist`, `discrete_plot`, `timeline_plot`, and `continuous_plot`
- Models
  - `LinearRegression` - Checking basic assumptions of a linear regression model
    - Linear function - Residuals vs. Fit plot
    - Homoscedasticity - Residuals vs. Fit plot
    - No autocorrelation - Using Durbin-Watson Test to identify possible autocorrelation.
    - Normally-distributed residuals - Qqplot
    - No multicollinearity - Using Pearson correlation
    - No outliers - Using boxplots and IQR range

### model-selection.ipynb

- Plotting learning curves to identify overfitting and underfitting
- Fitting dataset transformations to the cross-validation set.
- Using L1 and L2 regularization to handle overfitting. Shown in Lasso and Ridge regression, respectively.
- Models:
  - Linear Regression
  - Random Forest Regression
  - XGBoost Regression
  - Artificial Neural Network
- Hyperparameter tuning
  - Using `RandomizedSearchCV` to narrow the search space by randomly sampling hyperparameter settings.
  - Using `GridSearchCV` on a narrowed search space to deterministic identify the best hyperparameter setting within the given range.
- TensorFlow
  - `tf.keras.layers.experimental.preprocessing.Normalization` - Used to feature scale the ANN for gradient-based learning.
  - Constructing, compiling, and training a model with `tf.keras.Sequential`
