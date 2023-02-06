# Recommender Systems on H&M Fashion Dataset

## Introduction

In this project I applied Exploratory Data Analytics on the H&M [Fashion Dataset](https://www.kaggle.com/competitions/h-and-m-personalized-fashion-recommendations/data) to have an insight look at the dataset and then implemented three recommender systems based on the [Turi Create](https://github.com/apple/turicreate).

## Dataset

The complete dataset is available [HERE](https://www.kaggle.com/competitions/h-and-m-personalized-fashion-recommendations/data).

The dataset contains totally three `.csv` files and 105K `.jpg` files.

The three `.csv` files are as followed:

- **articles.csv** - detailed metadata for each `article_id` available for purchase
- **customers.csv** - metadata for each `customer_id` in dataset
- **transactions_train.csv** - the training data, consisting of the purchases each customer for each date, as well as additional information. Duplicate rows correspond to multiple purchases of the same item. 

- **images/** is a folder of images corresponding to each `article_id`; images are placed in subfolders starting with the first three digits of the `article_id`; **important note!** Not all article_id values have a corresponding image!

## Exploratory Data Analytics

In this part, I applied data preprocessing methods to `articles.csv`, `customers.csv`, `transaction_tran.csv` to impute missing values and made visulizations to have a more directly look into the data. For 

![Product Type]()![Wordcloud]()

## Recommender Systems

In this part, based on [Turi Create](https://github.com/apple/turicreate), I implemented three recommender systems for the recommendation of top-12 items for each user. Turi Create simplifies the development of custom machine learning models and it's open source on GitHub. Since Turi Create is based on the [RAPID](https://github.com/rapidsai/cudf) dataframe, here we use the RAPID dataframe to read in and prepare the datasets.

### Prepare Dataset

To prepare the dataset, we first create normalized matrix with customers on rows and articles ad columns and then split the dataset into training and testing dataset.

- `Training Dataset`: 70%
- `Testing Dataset`: 30%

### Models

The three recommender systems includes _Popularity Recommender System_, _Cosine Recommender System_ and _Pearson Recommender System_. The _Popularity Recommender System_ recommends the top-12 popular items among all items while the _Cosine Recommender System_ and _Pearson Recommender System_ recommend the top-12 item that are most correlated to the user's previous purchases based on collaborative filtering.

## Results 

After the training process of each model, the RMSE, Mean Precision and Mean Recall of each model is calculated to evaluate the performance of each model. The complete evaluation output can be found in the `.txt` and '.txt'.

Here is the result of the RMSE for each model:

|              Models                |   RMSE  | 
| ---------------------------------- | ------- |
| `Popularity Recommender System`    |  1.699  |
| `Cosine Recommender System`        |  1.017  | 
| `Pearson Recommender System`       |  1.675  | 

## Project Structure

├─code
│ ├─Recommender_System_H&M.ipynb   # Jupyter Notebook for this project
├─output
│ ├─eval_counts.txt   # evaluaton results of three models  
├─public   # Some of the example images
│ ├─example1.png
│ ├─example2.png






