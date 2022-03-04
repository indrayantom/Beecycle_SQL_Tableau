# :star:Beecycle Dataset : Data Analysis Using SQL Queries and Tableau:star:

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
To determine the best number of clusters, the Total Within Sum of Square of each amount cluster iteration must be calculated, and the result is shown as follow:
![numclusters](https://user-images.githubusercontent.com/92590596/156587456-817640ac-2de1-40fe-9373-d4d85ad35f10.jpg)
The best number of cluster is usually found using elbow method, a method to find a point where  sum squares start decreasing slowly in a linear fashion (many literatures/sources say this, e.g https://www.geeksforgeeks.org/elbow-method-for-optimal-value-of-k-in-kmeans/). Based on this characteristic, it is concluded that the optimal number of clusters for this dataset is 3.

From the Petal.Length vs Petal.Width plot, one can see that the model is able to perfectly identify the setosa species among all observations. Unfortunately, when attempting to identify the versicolor and virginica species, the model begins to make 'mistakes'. This errors may comes from the fact that there are several Virginica and versicolor samples with quite similar characteristics to each other.
![cluster3](https://user-images.githubusercontent.com/92590596/156587499-c6612980-160f-429d-b50f-c24d818ff77c.jpg)


