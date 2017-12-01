

```python
import pandas as pd
import numpy as np

```


```python
print("The primary demographic is males ages 20-24.")
print("Even the biggest spenders buy very few quantities of add-ons.")
print("I would consider lowering prices to earn more from volume.")

```

    The primary demographic is males ages 20-24.
    Even the biggest spenders buy very few quantities of add-ons.
    I would consider lowering prices to earn more from volume.
    


```python
file1 = "purchase_data.json"
file2 = "purchase_data2.json"
```


```python
heroe_df1 = pd.read_json(file1)
heroe_df2 = pd.read_json(file2)
heroe_df1.head()


```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Age</th>
      <th>Gender</th>
      <th>Item ID</th>
      <th>Item Name</th>
      <th>Price</th>
      <th>SN</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>38</td>
      <td>Male</td>
      <td>165</td>
      <td>Bone Crushing Silver Skewer</td>
      <td>3.37</td>
      <td>Aelalis34</td>
    </tr>
    <tr>
      <th>1</th>
      <td>21</td>
      <td>Male</td>
      <td>119</td>
      <td>Stormbringer, Dark Blade of Ending Misery</td>
      <td>2.32</td>
      <td>Eolo46</td>
    </tr>
    <tr>
      <th>2</th>
      <td>34</td>
      <td>Male</td>
      <td>174</td>
      <td>Primitive Blade</td>
      <td>2.46</td>
      <td>Assastnya25</td>
    </tr>
    <tr>
      <th>3</th>
      <td>21</td>
      <td>Male</td>
      <td>92</td>
      <td>Final Critic</td>
      <td>1.36</td>
      <td>Pheusrical25</td>
    </tr>
    <tr>
      <th>4</th>
      <td>23</td>
      <td>Male</td>
      <td>63</td>
      <td>Stormfury Mace</td>
      <td>1.27</td>
      <td>Aela59</td>
    </tr>
  </tbody>
</table>
</div>




```python
heroe_df2.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Age</th>
      <th>Gender</th>
      <th>Item ID</th>
      <th>Item Name</th>
      <th>Price</th>
      <th>SN</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>20</td>
      <td>Male</td>
      <td>93</td>
      <td>Apocalyptic Battlescythe</td>
      <td>4.49</td>
      <td>Iloni35</td>
    </tr>
    <tr>
      <th>1</th>
      <td>21</td>
      <td>Male</td>
      <td>12</td>
      <td>Dawne</td>
      <td>3.36</td>
      <td>Aidaira26</td>
    </tr>
    <tr>
      <th>2</th>
      <td>17</td>
      <td>Male</td>
      <td>5</td>
      <td>Putrid Fan</td>
      <td>2.63</td>
      <td>Irim47</td>
    </tr>
    <tr>
      <th>3</th>
      <td>17</td>
      <td>Male</td>
      <td>123</td>
      <td>Twilight's Carver</td>
      <td>2.55</td>
      <td>Irith83</td>
    </tr>
    <tr>
      <th>4</th>
      <td>22</td>
      <td>Male</td>
      <td>154</td>
      <td>Feral Katana</td>
      <td>4.11</td>
      <td>Philodil43</td>
    </tr>
  </tbody>
</table>
</div>




```python
heroe_df = pd.concat([heroe_df1, heroe_df2], ignore_index=True)
```


```python
heroe_df.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Age</th>
      <th>Gender</th>
      <th>Item ID</th>
      <th>Item Name</th>
      <th>Price</th>
      <th>SN</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>38</td>
      <td>Male</td>
      <td>165</td>
      <td>Bone Crushing Silver Skewer</td>
      <td>3.37</td>
      <td>Aelalis34</td>
    </tr>
    <tr>
      <th>1</th>
      <td>21</td>
      <td>Male</td>
      <td>119</td>
      <td>Stormbringer, Dark Blade of Ending Misery</td>
      <td>2.32</td>
      <td>Eolo46</td>
    </tr>
    <tr>
      <th>2</th>
      <td>34</td>
      <td>Male</td>
      <td>174</td>
      <td>Primitive Blade</td>
      <td>2.46</td>
      <td>Assastnya25</td>
    </tr>
    <tr>
      <th>3</th>
      <td>21</td>
      <td>Male</td>
      <td>92</td>
      <td>Final Critic</td>
      <td>1.36</td>
      <td>Pheusrical25</td>
    </tr>
    <tr>
      <th>4</th>
      <td>23</td>
      <td>Male</td>
      <td>63</td>
      <td>Stormfury Mace</td>
      <td>1.27</td>
      <td>Aela59</td>
    </tr>
  </tbody>
</table>
</div>




```python
player_count = [] 
player_count.append(len(heroe_df["SN"].unique()))
player_count_df = pd.DataFrame(player_count)
player_count_df.columns = ["Number of Players"]
player_count_df
#print("There are " + str(player_count) + " players")
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Number of Players</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>612</td>
    </tr>
  </tbody>
</table>
</div>




```python



```


```python
total_revenue = []
total_revenue.append(heroe_df["Price"].sum())
total_revenue_df = pd.DataFrame(total_revenue)
total_revenue_df.columns=['Total Revenue']
total_revenue_df
#print("The total revenue is " + str(total_revenue))
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Total Revenue</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2514.43</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python
sales_count = []
sales_count.append(heroe_df["SN"].count())
#print("The total number of sales is " + str(sales_count))
```


```python
unique_items = []
unique_items.append(len(heroe_df["Item ID"].unique()))
#print("The number of unique items is " + str(unique_items))
```

    The number of unique items is 184
    


```python
avg_pp = []
avg_pp.append(heroe_df["Price"].sum()/heroe_df["Price"].count())
#print("The average purchase price is " + str(avg_pp))
```

    The average purchase price is 2.93057109557
    


```python
new_df = pd.DataFrame({"Player Count":player_count,"Total Revenue":total_revenue,"Sales Count":sales_count,"Unique Items":unique_items,"Avg Purchase Price":avg_pp})
new_df
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Avg Purchase Price</th>
      <th>Player Count</th>
      <th>Sales Count</th>
      <th>Total Revenue</th>
      <th>Unique Items</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2.930571</td>
      <td>612</td>
      <td>858</td>
      <td>2514.43</td>
      <td>184</td>
    </tr>
  </tbody>
</table>
</div>




```python
male_df = heroe_df.loc[heroe_df["Gender"] =="Male"]
male_df.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Age</th>
      <th>Gender</th>
      <th>Item ID</th>
      <th>Item Name</th>
      <th>Price</th>
      <th>SN</th>
      <th>Age Demographic</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>38</td>
      <td>Male</td>
      <td>165</td>
      <td>Bone Crushing Silver Skewer</td>
      <td>3.37</td>
      <td>Aelalis34</td>
      <td>35-39</td>
    </tr>
    <tr>
      <th>1</th>
      <td>21</td>
      <td>Male</td>
      <td>119</td>
      <td>Stormbringer, Dark Blade of Ending Misery</td>
      <td>2.32</td>
      <td>Eolo46</td>
      <td>20-24</td>
    </tr>
    <tr>
      <th>2</th>
      <td>34</td>
      <td>Male</td>
      <td>174</td>
      <td>Primitive Blade</td>
      <td>2.46</td>
      <td>Assastnya25</td>
      <td>30-34</td>
    </tr>
    <tr>
      <th>3</th>
      <td>21</td>
      <td>Male</td>
      <td>92</td>
      <td>Final Critic</td>
      <td>1.36</td>
      <td>Pheusrical25</td>
      <td>20-24</td>
    </tr>
    <tr>
      <th>4</th>
      <td>23</td>
      <td>Male</td>
      <td>63</td>
      <td>Stormfury Mace</td>
      <td>1.27</td>
      <td>Aela59</td>
      <td>20-24</td>
    </tr>
  </tbody>
</table>
</div>




```python
female_df = heroe_df.loc[heroe_df["Gender"]=="Female"]
female_df.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Age</th>
      <th>Gender</th>
      <th>Item ID</th>
      <th>Item Name</th>
      <th>Price</th>
      <th>SN</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>7</th>
      <td>29</td>
      <td>Female</td>
      <td>169</td>
      <td>Interrogator, Blood Blade of the Queen</td>
      <td>3.32</td>
      <td>Iathenudil29</td>
    </tr>
    <tr>
      <th>16</th>
      <td>22</td>
      <td>Female</td>
      <td>123</td>
      <td>Twilight's Carver</td>
      <td>1.14</td>
      <td>Sundista85</td>
    </tr>
    <tr>
      <th>17</th>
      <td>22</td>
      <td>Female</td>
      <td>59</td>
      <td>Lightning, Etcher of the King</td>
      <td>1.65</td>
      <td>Aenarap34</td>
    </tr>
    <tr>
      <th>22</th>
      <td>11</td>
      <td>Female</td>
      <td>11</td>
      <td>Brimstone</td>
      <td>2.52</td>
      <td>Deural48</td>
    </tr>
    <tr>
      <th>29</th>
      <td>16</td>
      <td>Female</td>
      <td>45</td>
      <td>Glinting Glass Edge</td>
      <td>2.46</td>
      <td>Phaedai25</td>
    </tr>
  </tbody>
</table>
</div>




```python
other_df = heroe_df.loc[heroe_df["Gender"]=="Other / Non-Disclosed"]
other_df.head()



```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Age</th>
      <th>Gender</th>
      <th>Item ID</th>
      <th>Item Name</th>
      <th>Price</th>
      <th>SN</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>177</th>
      <td>34</td>
      <td>Other / Non-Disclosed</td>
      <td>155</td>
      <td>War-Forged Gold Deflector</td>
      <td>3.73</td>
      <td>Assassa38</td>
    </tr>
    <tr>
      <th>209</th>
      <td>33</td>
      <td>Other / Non-Disclosed</td>
      <td>157</td>
      <td>Spada, Etcher of Hatred</td>
      <td>2.21</td>
      <td>Frichistasta59</td>
    </tr>
    <tr>
      <th>244</th>
      <td>21</td>
      <td>Other / Non-Disclosed</td>
      <td>183</td>
      <td>Dragon's Greatsword</td>
      <td>2.36</td>
      <td>Tyaerith73</td>
    </tr>
    <tr>
      <th>267</th>
      <td>33</td>
      <td>Other / Non-Disclosed</td>
      <td>65</td>
      <td>Conqueror Adamantite Mace</td>
      <td>1.96</td>
      <td>Frichistasta59</td>
    </tr>
    <tr>
      <th>276</th>
      <td>12</td>
      <td>Other / Non-Disclosed</td>
      <td>128</td>
      <td>Blazeguard, Reach of Eternity</td>
      <td>4.00</td>
      <td>Aillycal84</td>
    </tr>
  </tbody>
</table>
</div>




```python
male_per = []
male_per.append((len(male_df["SN"].unique())/player_count[0])*100)
female_per = []
female_per.append((len(female_df["SN"].unique())/player_count[0])*100)
other_per = []
other_per.append((len((other_df["SN"]).unique())/player_count[0])*100)
demographic_df_df = pd.DataFrame({"% Male":male_per,"% Female":female_per,"% Other":other_per})
demographic_df_df

#print("There are {} players, including {} males ({}%), {} females ({}%), and {} others ({}%),".format(player_count, male_cnt, male_pct, female_cnt, female_pct, other_cnt, other_pct))
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>% Female</th>
      <th>% Male</th>
      <th>% Other</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>18.300654</td>
      <td>81.372549</td>
      <td>1.470588</td>
    </tr>
  </tbody>
</table>
</div>




```python
male_sales = []
male_sales.append(male_df["SN"].count())
male_sum = []
male_sum.append(male_df["Price"].sum())
male_avg = []
male_avg.append(male_sum[0]/male_sales[0])
male_df_df = pd.DataFrame({"Sales to Men":male_sales,"Total Revenue":male_sum,"Avg Sale":male_avg})
male_df_df

#print("There were {} sales to men, averaging ${}, and totaling ${}".format(male_sales, male_avg, male_sum))
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Avg Sale</th>
      <th>Sales to Men</th>
      <th>Total Revenue</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2.944448</td>
      <td>697</td>
      <td>2052.28</td>
    </tr>
  </tbody>
</table>
</div>




```python
female_sales = []
female_sales.append(female_df["SN"].count())
female_sum = []
female_sum.append(female_df["Price"].sum())
female_avg = []
female_avg.append(female_sum[0]/female_sales[0])
female_new_df = pd.DataFrame({"Sales to F":female_sales,"Revenue from F":female_sum,"Avg Sale F":female_avg})
female_new_df
#print("There were {} sales to females, averaging ${}, and totaling ${}".format(female_sales, female_avg, female_sum))
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Avg Sale F</th>
      <th>Revenue from F</th>
      <th>Sales to F</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2.847584</td>
      <td>424.29</td>
      <td>149</td>
    </tr>
  </tbody>
</table>
</div>




```python
other_sales = other_df["SN"].count()
other_sum = other_df["Price"].sum()
other_avg = other_sum/other_sales
print("There were {} sales to others, averaging ${}, and totaling ${}".format(other_sales, other_avg, other_sum))
```

    There were 12 sales to others, averaging $3.1549999999999994, and totaling $37.85999999999999
    


```python
player_df = heroe_df#.drop_duplicates(["SN"], keep='last')
player_df["SN"].count()
bins = [0, 9, 14, 19, 24, 29, 34, 39, 44, 49]
group_names = ['0-9', '10-14', '15-19', '20-24', '25-29', '30-34', '35-39', '40-44', '45-49']
pd.cut(player_df["Age"], bins, labels=group_names)
player_df["Age Demographic"] = pd.cut(player_df["Age"], bins, labels=group_names)
player_df.head()

```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Age</th>
      <th>Gender</th>
      <th>Item ID</th>
      <th>Item Name</th>
      <th>Price</th>
      <th>SN</th>
      <th>Age Demographic</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>38</td>
      <td>Male</td>
      <td>165</td>
      <td>Bone Crushing Silver Skewer</td>
      <td>3.37</td>
      <td>Aelalis34</td>
      <td>35-39</td>
    </tr>
    <tr>
      <th>1</th>
      <td>21</td>
      <td>Male</td>
      <td>119</td>
      <td>Stormbringer, Dark Blade of Ending Misery</td>
      <td>2.32</td>
      <td>Eolo46</td>
      <td>20-24</td>
    </tr>
    <tr>
      <th>2</th>
      <td>34</td>
      <td>Male</td>
      <td>174</td>
      <td>Primitive Blade</td>
      <td>2.46</td>
      <td>Assastnya25</td>
      <td>30-34</td>
    </tr>
    <tr>
      <th>3</th>
      <td>21</td>
      <td>Male</td>
      <td>92</td>
      <td>Final Critic</td>
      <td>1.36</td>
      <td>Pheusrical25</td>
      <td>20-24</td>
    </tr>
    <tr>
      <th>4</th>
      <td>23</td>
      <td>Male</td>
      <td>63</td>
      <td>Stormfury Mace</td>
      <td>1.27</td>
      <td>Aela59</td>
      <td>20-24</td>
    </tr>
  </tbody>
</table>
</div>




```python
group_df = player_df
price_sum = group_df.groupby("Age Demographic")["Price"].sum()
price_sum.head()
```




    Age Demographic
    0-9        97.28
    10-14     105.91
    15-19     416.83
    20-24    1087.66
    25-29     396.44
    Name: Price, dtype: float64




```python
price_cnt = group_df.groupby("Age Demographic")["Price"].count()
price_cnt.head()
```




    Age Demographic
    0-9       33
    10-14     38
    15-19    144
    20-24    372
    25-29    134
    Name: Price, dtype: int64




```python
demographic_df = pd.DataFrame({"Revenue":price_sum,
                                   "Sales":price_cnt})
demographic_df
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Revenue</th>
      <th>Sales</th>
    </tr>
    <tr>
      <th>Age Demographic</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0-9</th>
      <td>97.28</td>
      <td>33</td>
    </tr>
    <tr>
      <th>10-14</th>
      <td>105.91</td>
      <td>38</td>
    </tr>
    <tr>
      <th>15-19</th>
      <td>416.83</td>
      <td>144</td>
    </tr>
    <tr>
      <th>20-24</th>
      <td>1087.66</td>
      <td>372</td>
    </tr>
    <tr>
      <th>25-29</th>
      <td>396.44</td>
      <td>134</td>
    </tr>
    <tr>
      <th>30-34</th>
      <td>211.14</td>
      <td>71</td>
    </tr>
    <tr>
      <th>35-39</th>
      <td>140.77</td>
      <td>48</td>
    </tr>
    <tr>
      <th>40-44</th>
      <td>55.68</td>
      <td>17</td>
    </tr>
    <tr>
      <th>45-49</th>
      <td>2.72</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python

demographic_df["Average Sale"] = price_sum/price_cnt
demographic_df

```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Revenue</th>
      <th>Sales</th>
      <th>Average Sale</th>
    </tr>
    <tr>
      <th>Age Demographic</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0-9</th>
      <td>97.28</td>
      <td>33</td>
      <td>2.947879</td>
    </tr>
    <tr>
      <th>10-14</th>
      <td>105.91</td>
      <td>38</td>
      <td>2.787105</td>
    </tr>
    <tr>
      <th>15-19</th>
      <td>416.83</td>
      <td>144</td>
      <td>2.894653</td>
    </tr>
    <tr>
      <th>20-24</th>
      <td>1087.66</td>
      <td>372</td>
      <td>2.923817</td>
    </tr>
    <tr>
      <th>25-29</th>
      <td>396.44</td>
      <td>134</td>
      <td>2.958507</td>
    </tr>
    <tr>
      <th>30-34</th>
      <td>211.14</td>
      <td>71</td>
      <td>2.973803</td>
    </tr>
    <tr>
      <th>35-39</th>
      <td>140.77</td>
      <td>48</td>
      <td>2.932708</td>
    </tr>
    <tr>
      <th>40-44</th>
      <td>55.68</td>
      <td>17</td>
      <td>3.275294</td>
    </tr>
    <tr>
      <th>45-49</th>
      <td>2.72</td>
      <td>1</td>
      <td>2.720000</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python
big_spenders_df = heroe_df
big_spenders_df1 = big_spenders_df.groupby("SN")["Price"].sum().reset_index()

bs = big_spenders_df1.sort_values("Price", ascending=False)
bs = bs.rename(columns={"Price":"Total Purchases"})
bs2 = bs.head()
bs2
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>SN</th>
      <th>Total Purchases</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>574</th>
      <td>Undirrala66</td>
      <td>17.06</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Aerithllora36</td>
      <td>15.10</td>
    </tr>
    <tr>
      <th>459</th>
      <td>Saedue76</td>
      <td>13.56</td>
    </tr>
    <tr>
      <th>503</th>
      <td>Sondim43</td>
      <td>13.02</td>
    </tr>
    <tr>
      <th>382</th>
      <td>Mindimnya67</td>
      <td>12.74</td>
    </tr>
  </tbody>
</table>
</div>




```python
big_spenders_df2 = big_spenders_df.loc[(big_spenders_df["SN"]=="Undirrala66") + (big_spenders_df["SN"]=="Aerithllora36") + (big_spenders_df["SN"]=="Saedue76") + (big_spenders_df["SN"]=="Sondim43") + (big_spenders_df["SN"]=="Mindimnya67")]
big_spenders_df2 = big_spenders_df2.groupby("SN")["Price"].count().reset_index()
big_spenders_df2 = big_spenders_df2.rename(columns={"Price":"Sales Count"})
big_spenders_df2
```

    C:\Users\mduke\Anaconda3\lib\site-packages\pandas\core\computation\expressions.py:183: UserWarning: evaluating in Python space because the '+' operator is not supported by numexpr for the bool dtype, use '|' instead
      unsupported[op_str]))
    




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>SN</th>
      <th>Sales Count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Aerithllora36</td>
      <td>4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Mindimnya67</td>
      <td>4</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Saedue76</td>
      <td>4</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Sondim43</td>
      <td>4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Undirrala66</td>
      <td>5</td>
    </tr>
  </tbody>
</table>
</div>




```python
top_customers_df = pd.merge(big_spenders_df2, bs2, how="outer", on="SN")
top_customers_df["Avg Purchase"] = top_customers_df["Total Purchases"]/top_customers_df["Sales Count"]
top_customers_df
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>SN</th>
      <th>Sales Count</th>
      <th>Total Purchases</th>
      <th>Avg Purchase</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Aerithllora36</td>
      <td>4</td>
      <td>15.10</td>
      <td>3.775</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Mindimnya67</td>
      <td>4</td>
      <td>12.74</td>
      <td>3.185</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Saedue76</td>
      <td>4</td>
      <td>13.56</td>
      <td>3.390</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Sondim43</td>
      <td>4</td>
      <td>13.02</td>
      <td>3.255</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Undirrala66</td>
      <td>5</td>
      <td>17.06</td>
      <td>3.412</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python


```
