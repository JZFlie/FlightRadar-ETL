# Real-time-Petfinder-ETL

Extraction:
With my project, I aim to leverage the data from Petfinder.com to create an ETL for animal shelter through the Petfinder API. To connect my code to the API, I will be using the Petpy Python wrapper for easier utilization of the API.
The data will be extracted using the "requests" library and stored in JSON format, with information such as adoption listings, records, shelters, etc. being stored as the contents. Following a automated scheudule, data will be ingested in 20 minute intervals and stored into an Amazon S3 bucket.

Transformation:
Using PySpark, The data will be cleaned to rid of any issues such as missing or null values, duplicate data, or missing values. The data will be batch processed and stored in a separate Amazon S3 bucket from the raw data. Utilizing Apache Airflow, PySpark jobs will be scheduled to execute upon completion of data extraction. 

Loading:
With Amazon S3 being the target destination both raw and processed data will be stored in separate S3 buckets for organization. As mentioned before, Apache Airflow will be used to schedule the execution of data loading scripts, which will be automated to run after transformation is completed. To connect my code to Amazon S3, the Python SDK is required to use boto3.

Representation:
Lastly, for the visualization of data, I am considering using the Seaborn Python library to represent data such as adoption rates by region over specified intervals to identify trends.

https://github.com/aschleg/petpy
https://spark.apache.org/docs/latest/api/python/reference/index.html
https://boto3.amazonaws.com/v1/documentation/api/latest/index.html
https://www.petfinder.com/developers/v2/docs/#api-calls
