# Movies-ETL
## Overview of the project:
Utilizing python and SQL to build-out ETL pipelines that clean, transform, and load datasets into a existing tables by using SQLAlchemy library in Python for further data manipulation in a hackathon competition.
## Resources:
1. Python,
2. Jupyter Notebook,
3. PostgreSQL, and
4. I have 3 datasets in different formats:
* Movie data scrapped from Wikipedia in JSON file
* The Kaggle dataset in CSV file with details about the movies from The Movie Database (TMDb)
* MovieLens dataset as CSV file of over 20 million reviews.
## Different stages of the pipeline:
Among the datasets, Wikipedia data required a lot of work to be done. After importing JSON file to a dataframe, the dataframe had 193 columns. Most of them had only few values in a column or similar data but with different column name. The Kaggle and MovieLens datasets were in a better state. I only needed few adjustments. I have changed data types and sorted movies to select only non-adult films.

![Initial View of DF](https://github.com/shamayun/Movies-ETL/blob/main/Resources/Initial_view.png)

Also, I merged similar columns and removed columns which had 90% NaN values. Resulted reduced number of columns, shrinked to 24. The data of box office, budget, release date and running time had inconsistent format. Using regex I was able to extract values and converted them to appropriate data type (date or float). Executed below plan to transform all the information into desired view:

![Data Transformation Plan](https://github.com/shamayun/Movies-ETL/blob/main/Resources/Transformation_plan.png)

## Results:
After executing all the transformation steps, I had the clean dataset required for the hackathon. To make data accessible for the participants, I uploaded into 2 tables, movies & ratings to a DB named movie_data. I needed to import create_engine from the sqlalchemy module to perform these tasks. Once both tables were exported to SQL, ensured to match the number of rows were equal befor and after. Below snip confirms successful completion of load to SQL.

![Movies Table Confirmation](https://github.com/shamayun/Movies-ETL/blob/main/Resources/movies_query.png)
