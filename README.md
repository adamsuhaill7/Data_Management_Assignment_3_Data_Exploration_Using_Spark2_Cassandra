# 📊 Assignment 3 – Data Exploration Using Spark2 & Cassandra

## 📚 Course Information
- **Course**: STQD6324 – Data Management
- **Semester**: 2, 2024/2025
- **Student**: Adam Suhail Bin Shahril
- **Dataset**: MovieLens 100k ([Link](https://grouplens.org/datasets/movielens/100k/))

## 📝 Project Title
**"Data Exploration of MovieLens 100k: Uncovering User Preferences and Trends"**

![movies](Images/movies.jpg)

### 📥 Step 1: Download MovieLens Dataset
We download the following files from the MovieLens 100k dataset:
- `u.user` — User demographic data
- `u.data` — Ratings data
- `u.item` — Movie information

These files are saved to the `/tmp/` directory on the local file system.

### 🗂️ Step 2: Upload Dataset to HDFS
We upload the downloaded files from the local `/tmp/` directory to the Hadoop Distributed File System (HDFS) under the path: 
`/user/maria_dev/adam_suhail/assignment3/`

### 🔧 Spark Session Initialization
We begin by importing necessary PySpark libraries and creating a `SparkSession`. This session is configured to connect to Cassandra running on `localhost` (127.0.0.1).

### 👥 Load `u.user` Data from HDFS
We define the schema for the `u.user` file and load it as a DataFrame from HDFS using a pipe `|` delimiter.

### ⭐ Load `u.data` Ratings Data
Next, we load the movie ratings data from the `u.data` file. This file contains user ID, item (movie) ID, rating (on a scale of 1–5), and timestamp. The delimiter used is a tab (`\t`).

### 🎬 Load `u.item` Movies Data
We load the movie metadata from the `u.item` file. This dataset includes movie ID, title, release dates, IMDb URL, and genre information. The file is pipe (`|`) delimited.

### 🧠 Register Temp Views for SQL Queries
To enable SQL-based analysis using Spark SQL, we register the loaded DataFrames (`users`, `ratings`, and `movies`) as temporary views.

### 🗃️ Create Tables in Cassandra (`cqlsh`)
Before persisting any data into Cassandra using Spark, we manually create the required tables in the `movielens` keyspace using the `cqlsh` shell.

### Saving `users` DataFrame to Cassandra
In this step, we persist the `users` DataFrame into the `movielens` keyspace in Cassandra.

### 🔍 Step 3: Analyze Data and Answer Key Questions
We will perform analyses based on the following questions:

1. **Calculate the average rating for each movie**: Using SQL queries, we will compute the average ratings and present the results.
   
2. **Identify the top ten movies with the highest average ratings**: We will rank the movies based on their average ratings.

3. **Find users who have rated at least 50 movies and identify their favourite movie genres**: We will filter active users and determine their top-rated genres.

4. **Find all users who are less than 20 years old**: A query will identify users below this age threshold.

5. **Find all users whose occupation is “scientist” and whose age is between 30 and 40 years old**: We will filter users based on occupation and age criteria.
   
## 🙏 Thank You
Thank you for reviewing this MovieLens assignment. This notebook demonstrates how to use Apache Spark and Cassandra for large-scale movie data analysis using PySpark and SQL. Feel free to explore further queries and insights!
