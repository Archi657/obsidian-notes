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

```
![[Pasted image 20250817174718.png]]
![[Pasted image 20250817174806.png]]
![[Pasted image 20250817174848.png]]