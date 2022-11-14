# Regiment

### Introduction:

Special thanks to: http://chrisalbon.com/ for sharing the dataset and materials.

### Step 1. Import the necessary libraries


```python
import pandas as pd 
import numpy as np 
```

### Step 2. Create the DataFrame with the following values:


```python
raw_data = {'regiment': ['Nighthawks', 'Nighthawks', 'Nighthawks', 'Nighthawks', 'Dragoons', 'Dragoons', 'Dragoons', 'Dragoons', 'Scouts', 'Scouts', 'Scouts', 'Scouts'], 
        'company': ['1st', '1st', '2nd', '2nd', '1st', '1st', '2nd', '2nd','1st', '1st', '2nd', '2nd'], 
        'name': ['Miller', 'Jacobson', 'Ali', 'Milner', 'Cooze', 'Jacon', 'Ryaner', 'Sone', 'Sloan', 'Piger', 'Riani', 'Ali'], 
        'preTestScore': [4, 24, 31, 2, 3, 4, 24, 31, 2, 3, 2, 3],
        'postTestScore': [25, 94, 57, 62, 70, 25, 94, 57, 62, 70, 62, 70]}
```

### Step 3. Assign it to a variable called regiment.
#### Don't forget to name each column


```python
re = pd.DataFrame(raw_data,columns=['regiment', 'company', 'name', 'battles', 'preTestScore', 'postTestScore'])
re 
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
      <th>regiment</th>
      <th>company</th>
      <th>name</th>
      <th>battles</th>
      <th>preTestScore</th>
      <th>postTestScore</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Nighthawks</td>
      <td>1st</td>
      <td>Miller</td>
      <td>NaN</td>
      <td>4</td>
      <td>25</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nighthawks</td>
      <td>1st</td>
      <td>Jacobson</td>
      <td>NaN</td>
      <td>24</td>
      <td>94</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nighthawks</td>
      <td>2nd</td>
      <td>Ali</td>
      <td>NaN</td>
      <td>31</td>
      <td>57</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Nighthawks</td>
      <td>2nd</td>
      <td>Milner</td>
      <td>NaN</td>
      <td>2</td>
      <td>62</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Dragoons</td>
      <td>1st</td>
      <td>Cooze</td>
      <td>NaN</td>
      <td>3</td>
      <td>70</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Dragoons</td>
      <td>1st</td>
      <td>Jacon</td>
      <td>NaN</td>
      <td>4</td>
      <td>25</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Dragoons</td>
      <td>2nd</td>
      <td>Ryaner</td>
      <td>NaN</td>
      <td>24</td>
      <td>94</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Dragoons</td>
      <td>2nd</td>
      <td>Sone</td>
      <td>NaN</td>
      <td>31</td>
      <td>57</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Scouts</td>
      <td>1st</td>
      <td>Sloan</td>
      <td>NaN</td>
      <td>2</td>
      <td>62</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Scouts</td>
      <td>1st</td>
      <td>Piger</td>
      <td>NaN</td>
      <td>3</td>
      <td>70</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Scouts</td>
      <td>2nd</td>
      <td>Riani</td>
      <td>NaN</td>
      <td>2</td>
      <td>62</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Scouts</td>
      <td>2nd</td>
      <td>Ali</td>
      <td>NaN</td>
      <td>3</td>
      <td>70</td>
    </tr>
  </tbody>
</table>
</div>



### Step 4. What is the mean preTestScore from the regiment Nighthawks?  


```python
re[re['regiment'] == 'Nighthawks'].groupby('regiment').mean()
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
      <th>preTestScore</th>
      <th>postTestScore</th>
    </tr>
    <tr>
      <th>regiment</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Nighthawks</th>
      <td>15.25</td>
      <td>59.5</td>
    </tr>
  </tbody>
</table>
</div>



### Step 5. Present general statistics by company


```python
re.groupby("company").describe()
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
      <th colspan="8" halign="left">preTestScore</th>
      <th colspan="8" halign="left">postTestScore</th>
    </tr>
    <tr>
      <th></th>
      <th>count</th>
      <th>mean</th>
      <th>std</th>
      <th>min</th>
      <th>25%</th>
      <th>50%</th>
      <th>75%</th>
      <th>max</th>
      <th>count</th>
      <th>mean</th>
      <th>std</th>
      <th>min</th>
      <th>25%</th>
      <th>50%</th>
      <th>75%</th>
      <th>max</th>
    </tr>
    <tr>
      <th>company</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1st</th>
      <td>6.0</td>
      <td>6.666667</td>
      <td>8.524475</td>
      <td>2.0</td>
      <td>3.00</td>
      <td>3.5</td>
      <td>4.00</td>
      <td>24.0</td>
      <td>6.0</td>
      <td>57.666667</td>
      <td>27.485754</td>
      <td>25.0</td>
      <td>34.25</td>
      <td>66.0</td>
      <td>70.0</td>
      <td>94.0</td>
    </tr>
    <tr>
      <th>2nd</th>
      <td>6.0</td>
      <td>15.500000</td>
      <td>14.652645</td>
      <td>2.0</td>
      <td>2.25</td>
      <td>13.5</td>
      <td>29.25</td>
      <td>31.0</td>
      <td>6.0</td>
      <td>67.000000</td>
      <td>14.057027</td>
      <td>57.0</td>
      <td>58.25</td>
      <td>62.0</td>
      <td>68.0</td>
      <td>94.0</td>
    </tr>
  </tbody>
</table>
</div>



### Step 6. What is the mean of each company's preTestScore?


```python
re.groupby("company").preTestScore.mean()
```




    company
    1st     6.666667
    2nd    15.500000
    Name: preTestScore, dtype: float64



### Step 7. Present the mean preTestScores grouped by regiment and company


```python
re.groupby(["company","regiment"]).preTestScore.mean()
```




    company  regiment  
    1st      Dragoons       3.5
             Nighthawks    14.0
             Scouts         2.5
    2nd      Dragoons      27.5
             Nighthawks    16.5
             Scouts         2.5
    Name: preTestScore, dtype: float64



### Step 8. Present the mean preTestScores grouped by regiment and company without heirarchical indexing


```python
re.groupby(["company","regiment"]).preTestScore.mean().unstack()
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
      <th>regiment</th>
      <th>Dragoons</th>
      <th>Nighthawks</th>
      <th>Scouts</th>
    </tr>
    <tr>
      <th>company</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1st</th>
      <td>3.5</td>
      <td>14.0</td>
      <td>2.5</td>
    </tr>
    <tr>
      <th>2nd</th>
      <td>27.5</td>
      <td>16.5</td>
      <td>2.5</td>
    </tr>
  </tbody>
</table>
</div>



### Step 9. Group the entire dataframe by regiment and company


```python
re.groupby(["company","regiment"]).mean()
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
      <th></th>
      <th>preTestScore</th>
      <th>postTestScore</th>
    </tr>
    <tr>
      <th>company</th>
      <th>regiment</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="3" valign="top">1st</th>
      <th>Dragoons</th>
      <td>3.5</td>
      <td>47.5</td>
    </tr>
    <tr>
      <th>Nighthawks</th>
      <td>14.0</td>
      <td>59.5</td>
    </tr>
    <tr>
      <th>Scouts</th>
      <td>2.5</td>
      <td>66.0</td>
    </tr>
    <tr>
      <th rowspan="3" valign="top">2nd</th>
      <th>Dragoons</th>
      <td>27.5</td>
      <td>75.5</td>
    </tr>
    <tr>
      <th>Nighthawks</th>
      <td>16.5</td>
      <td>59.5</td>
    </tr>
    <tr>
      <th>Scouts</th>
      <td>2.5</td>
      <td>66.0</td>
    </tr>
  </tbody>
</table>
</div>



### Step 10. What is the number of observations in each regiment and company


```python
re.groupby(["company","regiment"]).size()
```




    company  regiment  
    1st      Dragoons      2
             Nighthawks    2
             Scouts        2
    2nd      Dragoons      2
             Nighthawks    2
             Scouts        2
    dtype: int64



### Step 11. Iterate over a group and print the name and the whole data from the regiment


```python
for name, group in re.groupby('regiment'):
    print(name)
    print(group)
```

    Dragoons
       regiment company    name battles  preTestScore  postTestScore
    4  Dragoons     1st   Cooze     NaN             3             70
    5  Dragoons     1st   Jacon     NaN             4             25
    6  Dragoons     2nd  Ryaner     NaN            24             94
    7  Dragoons     2nd    Sone     NaN            31             57
    Nighthawks
         regiment company      name battles  preTestScore  postTestScore
    0  Nighthawks     1st    Miller     NaN             4             25
    1  Nighthawks     1st  Jacobson     NaN            24             94
    2  Nighthawks     2nd       Ali     NaN            31             57
    3  Nighthawks     2nd    Milner     NaN             2             62
    Scouts
       regiment company   name battles  preTestScore  postTestScore
    8    Scouts     1st  Sloan     NaN             2             62
    9    Scouts     1st  Piger     NaN             3             70
    10   Scouts     2nd  Riani     NaN             2             62
    11   Scouts     2nd    Ali     NaN             3             70
    
