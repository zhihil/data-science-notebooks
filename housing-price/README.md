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

