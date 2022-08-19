# Clustering Cryptocurrency Asset Performance with Sklearn

This Jupyter Notebook usess clustering methods to cluster cryptocurrency performance metrics. 

## Technologies

This program is written in Python (3.7.13) and developed using JupyterLabs notebooks using Windows. Additional libraries that are used in this application are pandas (1.3.5), sklearn (1.0.2), and hvplot (0.7.3) (see parenthesis for versions used in program development).

## Installation Guide

Downloading the code & associated files using `git clone` from the repository is sufficient to download the Jupyter Notebook, ensure that the associated libaries (see Technologies section) are installed on your machine as well. If there are any issues with the library functions please refer to the versions used for app development (see Technnologies section for this information as well).  Please note that this is a Jupyter notebook. 

## Usage

This notebook is referencing data stored in the file 'crypto_market_data.csv' (which is in the Resources folder) to make the analysis. 

41 different types of cryptocurrency assets (bitcoin, ethereum, tether, ripple, etc...) are included in the file.

7 different performance metrics (asset returns over a period of an hour up to a period of a year) are included in the file for clustering. 

## Code examples

The data is loaded in to the Jupyter notebook, and `StandardScaler()` is used to normalize the data. 

Clustering is then performed, and the Elbow method is used to determine the optimal number of clusters for the dataset. 

```python
for i in k:
    k_model = KMeans(n_clusters=i, random_state=1)
    k_model.fit(df_market_data_scaled)
    inertia.append(k_model.inertia_)
```

Clustering is performed a second time, after PCA (principal component analysis) is used on the dataset to reduce the dimensions. 

```python
pca=PCA(n_components=3)
crypto_pca = pca.fit_transform(df_market_data_scaled)
```

Hvplot is then used to compare and contrast the different clustering methods, with `hvplot.scatter` and `hvplot.line`.

## References

For more information about the libraries, check out the documentation!

[Sklearn library](https://scikit-learn.org/stable/)

[Hvplot library](https://hvplot.holoviz.org/)

## Contributors

Project contributors are the Rice FinTech bootcamp program team (instructor Eric Cadena) who developed the tasks for this project along with myself (Paula K) who's written the code in the workbook.
