# Module-10-Challenge

For this project, I am utilizing Python and unsupervised learning to cluster cryptocurrencies by their performance over time and providing visuals.

---

## Technologies

This project uses pandas programming language and utilizes Anaconda, Python, Git Bash, Jupyter Lab, and Github. This project also uses scikit-learn and hvPlot.

---

## Installation Guide

These are the required libraries and dependencies:

import pandas as pd

import hvplot.pandas

from path import Path

from sklearn.cluster import KMeans

from sklearn.decomposition import PCA

from sklearn.preprocessing import StandardScaler


You must also install the scikit-learn and hvPlot packages in your conda dev environment using the code:

    pip install -U scikit-learn
    
    conda install -c pyviz hvplot

---

## Usage

I used the `StandardScaler()` module from scikit-learn to normalize the data from the CSV file:

    scaled_data = StandardScaler().fit_transform(df_market_data)


I created a for loop to compute the inertia with each possible value of k:

    for i in k:
    k_model = KMeans(n_clusters=i, random_state=1)
    k_model.fit(df_market_data_scaled)
    inertia.append(k_model.inertia_)
          
I created a scatter plot using hvPlot:

    market_data_predictions_df.hvplot.scatter(
    x="price_change_percentage_24h",
    y="price_change_percentage_7d",
    by="predicted_clusters",
    hover_cols="coin_id")

I created a DataFrame with the PCA data:

    market_data_pca_df = pd.DataFrame(
    market_data_pca,
    columns=["PCA1", "PCA2", "PCA3"])

and created a composite plot to contrast the clusters:

    market_data_predictions_df.hvplot.scatter(
    x="price_change_percentage_24h",
    y="price_change_percentage_7d",
    by="predicted_clusters",
    hover_cols="coin_id",
    title="Original Clusters") + market_pca_predictions_df.hvplot.scatter(
    x="PCA1",
    y="PCA2",
    by="predicted_clusters",
    hover_cols="coin_id",
    title="PCA Clusters")

---

## Contributors

Allyssa Carmin

---

## License

SMU Fintech Course