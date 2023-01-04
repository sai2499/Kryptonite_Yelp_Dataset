# ANALYSIS OF YELP DATASET

### Abstract
Consumer reviews have become an important deciding factor for businesses to flourish in today’s world. Consumers frequently rely on certified sources for trustworthy 
reviews of various establishments such as restaurants, hotels, and so on. Yelp is a local business directory and review site that also has social networking capabilities. It 
enables people to rate and review businesses. The goal is to create a relational database system that will integrate existing Yelp data to give insightful analytics and assist
existing and future business owners in making critical decisions about a new business or business expansion.

---
### INTRODUCTION
Every day, the internet generates an exponential amount of data. It is difficult to store massive volumes of data and extract insight from it. Yelp is a website that publishes
reviews submitted by the public about local businesses. It allows business owners to enhance their services and users to select the best business accessible. The dataset consists
of a subset of Yelp’s businesses, reviews, and user information. It was originally created for the Yelp Dataset Challenge, allowing students to conduct research or analyze Yelp’s
data and report their findings. The collection contains information on businesses in 11 metropolitan areas across four nations. We intend to create an effective database system
based on this dataset that can manage vast amounts of data and deliver insights such as reviews supplied by other consumers, ratings, tips, and so on which will be valuable to 
both consumers and businesses.

---
### TARGETED AUDIENCE

Owners that are prepared to monitor their firm and make significant decisions based on the visual plots, such as modifying the infrastructure or concentrating on an area that
will help them expand, will be the system’s users. The dataset’s real-world goal is to offer relevant insights and assist current and prospective business owners in making 
crucial choices about the business.

---
### DATA DESCRIPTION

The source data set is a JSON file, which is transformed into a CSV file using Python programs into tabular form. We chose to store the data in a database system for the
reasons listed below: 
1. The dataset is 4GB in size, making it challenging to store and access the data using CSV files. Postgres SQL, on the other hand, can store a large amount of data. 
Therefore, a database system would be a superior strategy for our instance.
2. The project’s main goal is to establish connections between the tables in order to learn more about the businesses. Through the use of primary keys and foreign keys, 
Postgre SQL aids in achieving this whereas a relational schema cannot be established using Excel.
3. The yelp data has multiple groups that are there are multiple categories for each business. Using a database system, we can enlist the business based on the groups and 
perform further analysis. Such functionality is not present in excel. 
4. The main reason behind choosing a database system over CSV for the current data is faster access as the size of the data is quite huge. Indexing can be performed on the
database tables for faster lookup whereas CSV depends on the size of the ram to access the data.

---
### DATA IMPORT AND PROCESSING
The dataset is an academic challenge distributed by Yelp. The dataset is in a compressed form. The uncompressed data is in form of JSON and hence requires extraction. 
Using python, the data is extracted into CSV and imported into Postgres via scripting. The data that we imported was in JSON format, so we extracted and scraped the data into
CSV format using python before loading it into Postgres SQL. 

---
### DATABASE AND TABLE FORMATION
After extracting the data into CSV files, we had a total of 7 CSV files. We create a database called ‘Yelp’ in Postgres SQL and the tables created are as mentioned below.
’yelp business’ table is one of the base tables created using the yelp business.csv by first extracting the CSV into a data frame object. We inserted the data into this table
using the “to sql” library which is used to insert the records present in the data frame object to a SQL database. We used this library for quicker insertion of data into 
the database. We then altered the table to add a primary key constraint on the column ‘business id’. The ’yelp user’ table is one of the base tables created using the yelp 
user.csv by first extracting the CSV into a data frame object. We inserted the data into this table using the “to sql” library which is used to insert the records present in
the data frame object to a SQL database. We used this library for quicker insertion of data into the database. We then altered the table to add a primary key constraint on
the column ‘user id’.

---
### FURTHER ENHANCEMENTS
The database that we designed is good for businesses to get enough insights, but there is a scope for a few improvements. Since this is an already populated database and 
static in nature, we can improve the time taken to fetch the data by creating views for the queries that are frequently accessed on the front end.

---
### REFERENCES
- https://www.kaggle.com/code/jagangupta/what-s-in-areview-yelp-ratings-eda
- https://www.yelp.com/dataset
- https://github.com/sai2499/Kryptonite
- https://www.yelp.com/dataset/documentation/main
- https://github.com/Yelp/dataset-examples
- https://towardsdatascience.com/converting-yelp-datasetto-csv-using-pandas-2a4c8f03bd88
