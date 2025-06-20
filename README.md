# 📘 README – Assignment 3: Data Exploration using Spark2 and Cassandra

## 📌 Overview
This notebook contains the steps and code for performing exploratory data analysis on the MovieLens 100k dataset using **Apache Spark 2** and **Apache Cassandra**. It is part of the coursework for:

- **Course:** STQD6324 – Data Management  
- **Semester:** 2, 2024/2025  
- **Student:** Adam Suhail Bin Shahril

## 📂 Dataset Information
The [MovieLens 100k dataset](https://grouplens.org/datasets/movielens/) consists of 100,000 movie ratings from 943 users on 1,682 movies.

### Files Used:
- `u.user` – User demographic data  
- `u.data` – User ratings for movies  
- `u.item` – Metadata about movies  

## 🛠️ Technologies
- Apache Spark 2 (PySpark)
- Apache Cassandra (localhost)
- Hadoop HDFS
- Zeppelin Notebook or any Spark-supported notebook environment

## 🧭 Workflow Summary

1. **Download the Dataset:**  
   Files are fetched from a public URL and saved to the local `/tmp/` directory.

2. **Upload to HDFS:**  
   Local files are copied into the Hadoop Distributed File System at:  
   `/user/maria_dev/adam_suhail/assignment3/`

3. **Initialize Spark Session:**  
   Spark is configured to work with Cassandra running locally.

4. **Load & Explore Data:**  
   - Load datasets into Spark DataFrames
   - Perform schema inspection, data preview, and basic exploration
   - Prepare and clean data as needed

5. **Write to Cassandra:**  
   Transformed data is saved into appropriate Cassandra tables.

6. **Run Analytical Queries:**  
   Basic analytics such as top-rated movies, demographic patterns, etc.

## 📝 Notes
- Ensure Cassandra is running and accessible on `127.0.0.1` before executing the notebook.
- If using Zeppelin or Jupyter with Spark, ensure required connectors for Cassandra are available.

## 🔗 External Links
- [MovieLens Dataset](https://grouplens.org/datasets/movielens/)
- [Apache Spark](https://spark.apache.org/)
- [Apache Cassandra](https://cassandra.apache.org/)
- [Zeppelin](https://zeppelin.apache.org/)
