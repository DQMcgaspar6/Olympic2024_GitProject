# Assignment 3: Github Project
Name: Claire Anne Gaspar

# 1. Introduction

### Olympic 2024 Medallists Analysis

This dataset contains information about athletes who won medals in the 2024 Olympics. It includes details such as medal type, athlete name, gender, country, discipline, and event. Tha analysis include:
* Understanding the structure and content of the dataset.
* Describing the data.
* Generating summaries and visualizations to uncover insights and patterns.

# 2. Load the data


```python
##import any libraries/ modules 

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```


```python
##Load the Dataset

data = pd.read_csv('Olympic2024_Medallists.csv')

data.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>medal_date</th>
      <th>medal_type</th>
      <th>medal_code</th>
      <th>name</th>
      <th>gender</th>
      <th>country_code</th>
      <th>country</th>
      <th>country_long</th>
      <th>nationality</th>
      <th>team</th>
      <th>team_gender</th>
      <th>discipline</th>
      <th>event</th>
      <th>event_type</th>
      <th>url_event</th>
      <th>birth_date</th>
      <th>code_athlete</th>
      <th>code_team</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2024-07-27</td>
      <td>Gold Medal</td>
      <td>1.0</td>
      <td>EVENEPOEL Remco</td>
      <td>Male</td>
      <td>BEL</td>
      <td>Belgium</td>
      <td>Belgium</td>
      <td>Belgium</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Cycling Road</td>
      <td>Men's Individual Time Trial</td>
      <td>ATH</td>
      <td>/en/paris-2024/results/cycling-road/men-s-indi...</td>
      <td>2000-01-25</td>
      <td>1903136</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2024-07-27</td>
      <td>Silver Medal</td>
      <td>2.0</td>
      <td>GANNA Filippo</td>
      <td>Male</td>
      <td>ITA</td>
      <td>Italy</td>
      <td>Italy</td>
      <td>Italy</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Cycling Road</td>
      <td>Men's Individual Time Trial</td>
      <td>ATH</td>
      <td>/en/paris-2024/results/cycling-road/men-s-indi...</td>
      <td>1996-07-25</td>
      <td>1923520</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2024-07-27</td>
      <td>Bronze Medal</td>
      <td>3.0</td>
      <td>van AERT Wout</td>
      <td>Male</td>
      <td>BEL</td>
      <td>Belgium</td>
      <td>Belgium</td>
      <td>Belgium</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Cycling Road</td>
      <td>Men's Individual Time Trial</td>
      <td>ATH</td>
      <td>/en/paris-2024/results/cycling-road/men-s-indi...</td>
      <td>1994-09-15</td>
      <td>1903147</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2024-07-27</td>
      <td>Gold Medal</td>
      <td>1.0</td>
      <td>BROWN Grace</td>
      <td>Female</td>
      <td>AUS</td>
      <td>Australia</td>
      <td>Australia</td>
      <td>Australia</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Cycling Road</td>
      <td>Women's Individual Time Trial</td>
      <td>ATH</td>
      <td>/en/paris-2024/results/cycling-road/women-s-in...</td>
      <td>1992-07-07</td>
      <td>1940173</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2024-07-27</td>
      <td>Silver Medal</td>
      <td>2.0</td>
      <td>HENDERSON Anna</td>
      <td>Female</td>
      <td>GBR</td>
      <td>Great Britain</td>
      <td>Great Britain</td>
      <td>Great Britain</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Cycling Road</td>
      <td>Women's Individual Time Trial</td>
      <td>ATH</td>
      <td>/en/paris-2024/results/cycling-road/women-s-in...</td>
      <td>1998-11-14</td>
      <td>1912525</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



# 3. Describing the data


```python
## Number of rows and columns
print("There are",data.shape[0], "rows.")
print("There are",data.shape[1], "columns.")
```

    There are 2315 rows.
    There are 18 columns.
    


```python
data.describe(include = "all").round(2)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>medal_date</th>
      <th>medal_type</th>
      <th>medal_code</th>
      <th>name</th>
      <th>gender</th>
      <th>country_code</th>
      <th>country</th>
      <th>country_long</th>
      <th>nationality</th>
      <th>team</th>
      <th>team_gender</th>
      <th>discipline</th>
      <th>event</th>
      <th>event_type</th>
      <th>url_event</th>
      <th>birth_date</th>
      <th>code_athlete</th>
      <th>code_team</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>2315</td>
      <td>2315</td>
      <td>2314.00</td>
      <td>2312</td>
      <td>2312</td>
      <td>2312</td>
      <td>2312</td>
      <td>2312</td>
      <td>2310</td>
      <td>1555</td>
      <td>1555</td>
      <td>2315</td>
      <td>2315</td>
      <td>2315</td>
      <td>2294</td>
      <td>2312</td>
      <td>2315.00</td>
      <td>1555</td>
    </tr>
    <tr>
      <th>unique</th>
      <td>16</td>
      <td>3</td>
      <td>NaN</td>
      <td>2050</td>
      <td>2</td>
      <td>92</td>
      <td>92</td>
      <td>92</td>
      <td>92</td>
      <td>101</td>
      <td>4</td>
      <td>45</td>
      <td>288</td>
      <td>6</td>
      <td>489</td>
      <td>1745</td>
      <td>NaN</td>
      <td>284</td>
    </tr>
    <tr>
      <th>top</th>
      <td>2024-08-10</td>
      <td>Bronze Medal</td>
      <td>NaN</td>
      <td>ZHANG Yufei</td>
      <td>Female</td>
      <td>USA</td>
      <td>United States</td>
      <td>United States of America</td>
      <td>United States</td>
      <td>United States of America</td>
      <td>W</td>
      <td>Athletics</td>
      <td>Men</td>
      <td>HTEAM</td>
      <td>/en/paris-2024/results/football/men/fnl-000100--</td>
      <td>1998-04-19</td>
      <td>NaN</td>
      <td>FBLWTEAM11--BRA01</td>
    </tr>
    <tr>
      <th>freq</th>
      <td>371</td>
      <td>807</td>
      <td>NaN</td>
      <td>6</td>
      <td>1162</td>
      <td>330</td>
      <td>330</td>
      <td>330</td>
      <td>332</td>
      <td>230</td>
      <td>678</td>
      <td>231</td>
      <td>342</td>
      <td>843</td>
      <td>43</td>
      <td>8</td>
      <td>NaN</td>
      <td>22</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.02</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1893320.81</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>std</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>0.82</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>262827.59</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>min</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1532872.00</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1896552.00</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1924464.00</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1950498.50</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>max</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>4980004.00</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
data.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 2315 entries, 0 to 2314
    Data columns (total 18 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   medal_date    2315 non-null   object 
     1   medal_type    2315 non-null   object 
     2   medal_code    2314 non-null   float64
     3   name          2312 non-null   object 
     4   gender        2312 non-null   object 
     5   country_code  2312 non-null   object 
     6   country       2312 non-null   object 
     7   country_long  2312 non-null   object 
     8   nationality   2310 non-null   object 
     9   team          1555 non-null   object 
     10  team_gender   1555 non-null   object 
     11  discipline    2315 non-null   object 
     12  event         2315 non-null   object 
     13  event_type    2315 non-null   object 
     14  url_event     2294 non-null   object 
     15  birth_date    2312 non-null   object 
     16  code_athlete  2315 non-null   int64  
     17  code_team     1555 non-null   object 
    dtypes: float64(1), int64(1), object(16)
    memory usage: 325.7+ KB
    


```python
# How many NA values do we have?
data.isna().sum()
```




    medal_date        0
    medal_type        0
    medal_code        1
    name              3
    gender            3
    country_code      3
    country           3
    country_long      3
    nationality       5
    team            760
    team_gender     760
    discipline        0
    event             0
    event_type        0
    url_event        21
    birth_date        3
    code_athlete      0
    code_team       760
    dtype: int64



# 4. Summaries



```python
## Top 5 Countries by Medal Count
print(data["country"].value_counts().head())
```

    country
    United States    330
    France           186
    China            168
    Great Britain    161
    Australia        123
    Name: count, dtype: int64
    


```python
## Mean age as of 2024

from datetime import datetime

data["birth_date"] = pd.to_datetime(data["birth_date"], errors='coerce')
current_year = 2024
data["age"] = current_year - data["birth_date"].dt.year
mean_age = data["age"].mean().astype(int)

print(f"The mean age of the athletes is {mean_age:.0f}.")
```

    The mean age of the athletes is 26.
    


```python
## pivot table
data.groupby("medal_type").agg({"age":['count','min', 'median','mean', 'max']})..astype(int)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead tr th {
        text-align: left;
    }

    .dataframe thead tr:last-of-type th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="5" halign="left">age</th>
    </tr>
    <tr>
      <th></th>
      <th>count</th>
      <th>min</th>
      <th>median</th>
      <th>mean</th>
      <th>max</th>
    </tr>
    <tr>
      <th>medal_type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bronze Medal</th>
      <td>805</td>
      <td>16</td>
      <td>26</td>
      <td>26</td>
      <td>57</td>
    </tr>
    <tr>
      <th>Gold Medal</th>
      <td>751</td>
      <td>14</td>
      <td>27</td>
      <td>26</td>
      <td>55</td>
    </tr>
    <tr>
      <th>Silver Medal</th>
      <td>756</td>
      <td>15</td>
      <td>26</td>
      <td>26</td>
      <td>59</td>
    </tr>
  </tbody>
</table>
</div>




```python
top_disciplines = (data.groupby("discipline")
    .agg({"medal_type": "count"})
    .rename(columns={"medal_type": "Total Medals"})
    .sort_values(by="Total Medals", ascending=False)
    .head(10))

print(top_disciplines)
```

                   Total Medals
    discipline                 
    Athletics               231
    Swimming                219
    Rowing                  144
    Football                124
    Judo                    105
    Hockey                  102
    Handball                 94
    Fencing                  90
    Cycling Track            87
    Water Polo               78
    


```python
## United States Medal Count by Discipline and Gender
usa_data = data[data["country"] == "United States"]
usa_medal_count_by_discipline_gender = (usa_data.groupby(["discipline", "gender"])["medal_type"].count().unstack(fill_value=0).sort_values(by="Male", ascending=False)  
)
print(usa_medal_count_by_discipline_gender)
```

    gender                 Female  Male
    discipline                         
    Swimming                   40    30
    Athletics                  30    28
    Rowing                      0    13
    Water Polo                  0    13
    Volleyball                 13    13
    Basketball                 12    12
    Artistic Gymnastics        11     6
    Tennis                      0     4
    Skateboarding               0     3
    Equestrian                  1     3
    Wrestling                   4     3
    Shooting                    3     3
    Triathlon                   2     2
    Archery                     1     2
    Sailing                     0     2
    Breaking                    0     1
    Boxing                      0     1
    Fencing                     6     1
    Golf                        0     1
    Weightlifting               1     1
    Sport Climbing              1     1
    Taekwondo                   1     0
    Surfing                     1     0
    3x3 Basketball              4     0
    Rugby Sevens               12     0
    Diving                      2     0
    Cycling Track               7     0
    Cycling Road                2     0
    Cycling Mountain Bike       1     0
    Cycling BMX Freestyle       1     0
    Canoe Sprint                1     0
    Canoe Slalom                1     0
    Artistic Swimming           9     0
    Football                   20     0
    

# 5. Visualization


```python
## Top 10 countries by medal count
top_countries = data["country"].value_counts().head(10)

plt.figure(figsize=(10, 6))
sns.barplot(x=top_countries.values, y=top_countries.index)
plt.xlabel("Number of Medals")
plt.ylabel("Country")
plt.title("Top 10 Countries by Medal Count")
plt.show()
```


    
![png](output_18_0.png)
    


### Top 10 Countries by Medal Count
The bar chart shows that the United States leads with the highest number of medals (330), followed by France (186) and China (168). This shows the strong performance of these countries across different disciplines during the 2024 Olympics.


```python
## Gender Distribution of Medalists
gender_distribution = data["gender"].value_counts()

plt.figure(figsize=(8, 8))
plt.pie(
    gender_distribution,
    labels=gender_distribution.index,
    autopct="%1.1f%%",
    startangle=90,
    colors=["skyblue", "lightcoral"],
    wedgeprops={"edgecolor": "black"})
plt.title("Gender Distribution of Medalists")
plt.show()

```


    
![png](output_20_0.png)
    


### Gender Distribution of Medalists
The pie chart shows that the distribution of male and female medalists is nearly equal, with 50.3% female and 49.7% male athletes. This reflects progress toward achieving gender equality in sports.


```python
## Age Distribution of Athletes

plt.figure(figsize=(10, 6))
sns.histplot(data["age"].dropna(), kde=True, color="skyblue", edgecolor="black")
plt.xlabel("Age")
plt.ylabel("Count")
plt.title("Age Distribution of Athletes")
plt.show()
```


    
![png](output_22_0.png)
    


### Age Distribution of Athletes
The histogram shows that the majority of athletes are between 20 and 35 years old, with an average age of 26. This is consistent with the peak physical performance age for many sports.


```python
## Distribution of Medal Types by Gender

plt.figure(figsize=(10, 6))
sns.countplot(x="medal_type", hue="gender", data=data, palette="Set2")
plt.title("Distribution of Medal Types by Gender")
plt.xlabel("Medal Type")
plt.ylabel("Count")
plt.legend(title="Gender")
plt.grid(True, axis='y', linestyle="--", alpha=0.7)
plt.xticks(rotation=0)
plt.show()

```


    
![png](output_24_0.png)
    


### Distribution of Medal Types by Gender
The bar chart shows the distribution of medal types (Gold, Silver, and Bronze) by gender. The chart reflects progress in achieving gender equality in sports, as both genders are equally competitive in winning medals.


```python

```
