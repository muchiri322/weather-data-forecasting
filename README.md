# weather-data ingestion into snowflake

This project demonstrates how to collect and insert weather data into a Snowflake data warehouse using Python. It uses `pandas` for data manipulation and `snowflake-connector-python` to interface with Snowflake.

## Objective
The objective is to Build a lightweight ETL pipeline that pushes weather data into a Snowflake table using Python.

## Technologies Used

- Python 3.+
- Jupyter Notebook
- pandas
- requests (if API-based expansion is desired)
- snowflake-connector-python
- sqlalchemy (optional)

- 
##  Setup Instructions

Install required packages:

pip install pandas snowflake-connector-python

Project Structure

### 1. Connect to Snowflake

```python
import snowflake.connector

conn = snowflake.connector.connect(
    user='YOUR_USERNAME',
    password='YOUR_PASSWORD',
    account='YOUR_ACCOUNT',
    warehouse='COMPUTE_WH',
    database='YOUR_DATABASE',
    schema='YOUR_SCHEMA'
)
cursor = conn.cursor()


### 2. Create Table

create a table in  snowflake with columns matching those in the data

### 3. Insert Sample Data

# python
cursor.execute("""
INSERT INTO weather_data (weather_type, temperature, humidity, wind_speed, city, country)
VALUES 
('clear sky', 25.0, 40, 5.0, 'Nairobi', 'KENYA'),
('few clouds', 26.0, 45, 3.5, 'Nairobi', 'KENYA'),
('scattered clouds', 24.0, 50, 4.0, 'Nairobi', 'KENYA'),
('broken clouds', 23.0, 55, 2.5, 'Nairobi', 'KENYA'),
('shower rain', 22.0, 60, 6.0, 'Nairobi', 'KENYA'),
('rain', 21.0, 65, 7.0, 'Nairobi', 'KENYA')
""")

