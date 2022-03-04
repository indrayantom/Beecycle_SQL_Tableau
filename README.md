# :star:Beecycle Dataset : Data Analysis Hands-on Using SQL Queries and Tableau:star:

This work contains Data Analysis Hands-on using PostgreSQL Queries and Tableau on Beecycle Customer's Dataset (Artificial Data) . As said in the name, Beecycle is a company that sold and produced bycycle.

![python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![tableau](https://img.shields.io/badge/Tableau-E97627?style=for-the-badge&logo=Tableau&logoColor=white)
![postgresql](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)

These are the links related to the work :

- [Google Collab docs (contains SQL Queries)](https://colab.research.google.com/drive/1GKTl_xAw7CjP1hzPoC5s6xCAFsdn4O2m#scrollTo=NG_E_Gjz3jwQ)
- [Tableau Dashboard](https://public.tableau.com/app/profile/indra.yanto.simanihuruk/viz/HW_30_Indra/Soal4?publish=yes)
- [Tableau Exercise Full](https://public.tableau.com/app/profile/indra.yanto.simanihuruk/viz/HW_30_Indra_AllSheets/Soal4?publish=yes)

## Libraries
The PostgreSQL can be integrated with Python using [psycopg2](https://www.tutorialspoint.com/postgresql/postgresql_python.htm) module. sycopg2 is a PostgreSQL database adapter for the Python programming language. psycopg2 was written with the aim of being very small and fast, and stable as a rock. However, I also used [plotnine](https://plotnine.readthedocs.io/en/stable/) to make a better (and easier) plots, as well as [pandas](https://pandas.pydata.org/) to convert the result of SQL queries into Pandas Dataframe.
```python
import psycopg2
%load_ext sql 
%sql postgresql://ugevpyllcosyvj:c6d71dd4ed2886ccd8eb2286879a05dc3ebb21046ff280be09bff424ec3d15ff@ec2-44-198-100-81.compute-1.amazonaws.com:5432/db4vmf7pt6qmqj

import pandas as pd
from sqlalchemy import create_engine
from matplotlib import pyplot as plt
import seaborn as sns
from plotnine import *
%matplotlib inline
%config InlineBackend.figure_format = 'svg'
```

## Result preview
![download](https://user-images.githubusercontent.com/92590596/156812218-de368f02-3eb8-43f7-a2a5-0af087b23b8b.png)

This dataset contains 5 data such as dim_geography, dim_customer, dim_product, fact_sales, and dim_territory with information as below :

- dim_geography only has primary key which is geography_id
- dim customer has one primary key and foreign key such as customer_id and geography_id from dim_geography table
- dim_product only has primary key which is product_id
- dim_territory only has primary key which is territory_id
- fact sales has one primary key which is order_detail_id, and has 3 foreign keys such as product_id from dim_product, customer_id from dim_customer, and territory_id from dim_territory

In order to learn how the Covid-19 pandemic impacted the business, the analysis that is brought into this Hands-on is about the Company's Sales During Pandemic. The trend in term of company's profit during the pandemic can be seen below. 

![covid](https://user-images.githubusercontent.com/92590596/156812303-b714f0db-38ee-49b6-a987-8a06bbe8f2cf.jpg)

The company began the operations in 2016 and had continued to grow year after year, with significant profit increases. However, when the Covid 19 outbreak began in November 2019, profit began to decline. By 2020, the company only gained 4 Billion Rupiahs profit in total, down nearly 50% or 4 Billion Rupiahs from the previous year. By July 2021 (middle of the year), total profit had dropped to 1.1 billion Rupiah, which is even less than the company's first year profit of 2.8 billion Rupiah. This result shows the Covid 19 Pandemic has a significant negative impact on the business.



