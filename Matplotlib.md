```Python
import matplotlib.pyplot as plt
year = [1950, 1970, 1990, 2010]
pop = [2.519, 3.692, 5.263, 4,321]

plt.plot(year, pop)

plt.xlabel('year')
plt.ylabel('populaation')
plt.title('world pption projections')
plt.yticks([0,2,4,6],
           ['0','2B','4B','6B'])
plt.grid(True)
plt.scatter(year, pop) # points
plt.show()
```
### Histogram
![[Pasted image 20250817115719.png]]
### Scatter
```Python
plt.scatter(x = gdp_cap, y = life_exp, s = np.array(pop) * 2, 
c = col, alpha=0.8)

# Previous customizations
plt.xscale('log') 
plt.xlabel('GDP per Capita [in USD]')
plt.ylabel('Life Expectancy [in years]')
plt.title('World Development in 2007')
plt.xticks([1000,10000,100000], ['1k','10k','100k'])
```
![[Pasted image 20250817150916.png]]