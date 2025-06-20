# 📊 Assignment 3 – Data Exploration Using Spark2 & Cassandra

## 📚 Course Information
- **Course**: STQD6324 – Data Management
- **Semester**: 2, 2024/2025
- **Student**: Adam Suhail Bin Shahril
- **Dataset**: MovieLens 100k ([Link])

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

### ✅ Question 1: Calculate the average rating for each movie
We calculate the average rating for each movie using SQL queries.

### ✅ Question 2: Identify the top ten movies with the highest average ratings
We identify the top ten movies based on their average ratings.

### ✅ Question 3: Find the users who have rated at least 50 movies and identify their favourite movie genres
We find users who have rated at least 50 movies and identify their favorite genres.

### ✅ Question 4: Find all the users who are less than 20 years old
We query to find all users who are younger than 20.

### ✅ Question 5: Find all the users whose occupation is “scientist” and whose age is between 30 and 40 years old
We filter users based on their occupation and age.

## 🙏 Thank You
Thank you for reviewing this MovieLens assignment. This notebook demonstrates how to use Apache Spark and Cassandra for large-scale movie data analysis using PySpark and SQL. Feel free to explore further queries and insights!

