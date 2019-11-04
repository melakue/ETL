# ETL

### Extract

Obtained a file from Kaggle.com on World Happiness Report and the United States International Census Age Specific Fertility. Data for the World Happiness had a range of years from 2015 to 2017 by country. Data for age specific fertility had a wider range of years by country. The data from the United States International Census on Age Specific Fertility was downloadable through google cloud platform’s public dataset using the BigQuery API. This data was then downloaded to a csv.

### Transform
Cleansing the data from the World Happiness Report. This data was provided in 3 different csv files. Each file represented a different year. During inspection it is determined that some columns had data that were not in the other years’ csv’s and their titles were not similar but the data content were the same. Using Pandas, columns renamed so that all the column names would be aligned, added a year column to the 3 csv files to prepare the files to be appended into 1 file. Similar columns from the 3 files and dropped columns that did not exist in each year of data, appended the data for the 3 years of the Happiness report into 1 csv. The final product of the World Happiness Report included data in 1 csv from the years of 2015-2017.
The Age Specific Fertility data was formatted by the country name column in order to align it with the country data column in the World Happiness Report dataset. .loc function is used to filter year 2015-2017. The cleaned data is put in to Dataframe

### Load
DataFrame is now ready to be loaded into database. An engine is created to connect to Postgres and data is loaded into Postgres.
