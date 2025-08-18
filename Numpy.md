```Python
import numpy as np

np_height = np.array(height)
np_weight = np.array(weight)

bmi = np_weight / np_height ** 2
BMI
```
### np.random.normal()
```Python
#distribution mean
#distribution standard deviation
#number of examples

height = np.round(np.random.normal(1.75, 0.20, 5000),2)
weight = np.round(np.random.normal(60.32, 15, 5000),2)
np_city = np.column_stack((height, weight))
```
### Functions
```Python
# Print out the mean of np_height_in
print(np_height_in.mean())  

# Print out the median of np_height_in
print(np.median(np_height_in))

# Print out the standard deviation on height
stddev = np.std(np_baseball[:,0])
print("Standard Deviation: " + str(stddev))

# Print out correlation between first and second column
corr = np.corrcoef(np_baseball[:,0], np_baseball[:,1])
print("Correlation: " + str(corr))
```