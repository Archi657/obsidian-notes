### Cleaning
```Python
# check missing values
dog.isna().any()
dog.isna().sum()
dog.isna().sum().plot(kind="bar") # plt.show()

# Removing missing values
dogs.dropna()
dogs.fillna(0)
```
### Create
```Python
# From CSV
new_dogs = pd.read_csv("file.csv")
# Create a list of dictionaries with new data
avocados_list = [
    {"date": "2019-11-03", "small_sold": 10376832, "large_sold": 7835071},
    {"date": "2019-11-10", "small_sold": 10717154, "large_sold": 8561348},
]
avocados_dict = {
  "date": ["2019-11-17", "2019-12-01"],
  "small_sold": [10859987, 9291631],
  "large_sold": [7674135, 6238096]
}
# Convert list into DataFrame
avocados_2019 = pd.DataFrame(avocados_list)

# Print the new DataFrame
print(avocados_2019)
```
### Essentials
```Python
import pandas as pd


# Build cars DataFrame
names = ['United States', 'Australia', 'Japan', 'India', 'Russia', 'Morocco', 'Egypt']
dr =  [True, False, False, False, True, True, True]
cpc = [809, 731, 588, 18, 200, 70, 45]

cars_dict = { 'country':names, 'drives_right':dr, 'cars_per_cap':cpc }
cars = pd.DataFrame(cars_dict)
cars = pd.read_csv('cars.csv', index_col=0)
# Specify row labels of cars
cars.index = row_labels

.isnull().sum() # quantitiy of null values

# set index with csv
pd.read_csv("file.csv", index_col=['id'])

```
![[Pasted image 20250817174718.png]]
![[Pasted image 20250817174806.png]]
![[Pasted image 20250817174848.png]]
### For
```Python
brics = pd.read_csv('xx', index_row=0)
for lab, row in brics.iterrows():
	print(lab + ": " + row['capital'])

## Add Column

for lab, row in brincs.iterrows():
	brincs.loc[lab, "name_length"] = len(row["country"])

## for larguer datasets use apply
brics["name_length"] = brincs["country"].apply(len)
```
### Filter
``` Python
# is in
is_black_or_brown = dogs["color"].isin(["Black", "Brown"])
dogs[is_black_or_brown]
# sort
homelessness_reg_fam = homelessness.sort_values(["region", "family_members"], ascending=[True, False])

# Count and sort
dept_counts_sorted = store_depts["department"].value_counts(sort=True)

# Get the proportion of stores of each department and sort
dept_props_sorted = store_depts["department"].value_counts(sort=True, normalize=True)

```
## Summary Statistics
```Python
# where the center of the data is
dogs["height"].mean()
.median(), mode(), min(), max(), .var(), .std() , sum(), quantile().
# find oldets with dates
dogs["date"].min() # max ()

df['column'].agg(function)
print(sales[["c_a", "c_b"]].agg([iqr, "median"]))

```
NEED TO STUDY QUANTILE
### Cumulative statistics
```
.cummax()
.cummin()
.cumprod()

```
### Count
```Python

vet_visit.drop_duplicates(subset="named") # subset = ["col1","col2"]

holiday_dates = sales[sales["is_holiday"]].drop_duplicates(subset="date")

# group by
store_types.groupby("store_type")["store"].count()
groupby("color")["weight"].agg([min, max, sum])

store_types["store_type"].value_counts()

# For each airline, select nb_bumped and total_passengers and sum
airline_totals = airline_bumping.groupby("airline")[["nb_bumped", "total_passengers"]].sum()
```
### Pivot Tables
![[Pasted image 20251018153750.png]]
aggfunc = ["median", "mean"]  
```Python

dogs.pivot_table(values="weight_kg", index="color", columns="breed", fill_values=0, margins=True)
# Pivot for mean weekly_sales for each store type

mean_sales_by_type = sales.pivot_table(values="weekly_sales", index="type")

```
### Explicit indexes
```Python
dogs.reset_index(drop=True)
# Set index to use index search methods 
dogs.set_index("name")
dogs.loc[["Bella", "Stella"]]
# multi level indexes/hierarchical indexes 
# Sort temperatures_ind by index values
print(temperatures_ind.sort_index())

# Sort temperatures_ind by index values at the city level
print(temperatures_ind.sort_index(level="city"))

# Sort temperatures_ind by country then descending city
print(temperatures_ind.sort_index(level=["country", "city"], ascending = [True, False]))
```
## Joining Data with Pandas Inner Join
```Python
# Merge the taxi_owners and taxi_veh tables
taxi_own_veh = taxi_owners.merge(taxi_veh, on='vid')

# Merge the taxi_owners and taxi_veh tables setting a suffix
taxi_own_veh = taxi_owners.merge(taxi_veh, on='vid', suffixes=('_own','_veh'))
# Print the value_counts to find the most popular fuel_type
print(taxi_own_veh['fuel_type'].value_counts

# merge multiple
# Merge the ridership, cal, and stations tables

ridership_cal_stations = ridership.merge(cal, on=['year','month','day']) \
                            .merge(stations, on='station_id')
                            

# usage example
# Merge the ridership, cal, and stations tables

ridership_cal_stations = ridership.merge(cal, on=['year','month','day']) \
                            .merge(stations, on='station_id')
# Create a filter to filter ridership_cal_stations
filter_criteria = ((ridership_cal_stations['month'] == 7) 
                   & (ridership_cal_stations['day_type'] == "Weekday") 
                   & (ridership_cal_stations['station_name'] == "Wilson"))
# Use .loc and the filter to select for rides
print(ridership_cal_stations.loc[filter_criteria, 'rides'].sum())
```
![[Pasted image 20251020221418.png]]
### Other Join
```Python
# Merge the movies and scifi_only tables with an inner join

movies_and_scifi_only = movies.merge(scifi_only, how='inner',

                                     left_on='id', right_on='movie_id')
```
### Concat
```Python
pd.concat([inv_jav, inv_feb, inv_mars])
```