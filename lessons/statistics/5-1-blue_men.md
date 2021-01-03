[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> Question: In the BRFSS (see Section 5.4), the distribution of heights is roughly normal with parameters µ = 178 cm and σ = 7.7 cm for men, and µ = 163 cm and σ = 7.3 cm for women. In order to join Blue Man Group, you have to be male between 5’10” and 6’1” (see http://bluemancasting.com). What percentage of the U.S. male population is in this range? Hint: use scipy.stats.norm.cdf.

First, we set parameter values for mu and sigma:
```{python}
mu = 178
sigma = 7.7
```

We then calculate the percentile for values 5'10" and 6'1' after converting the values to cm and subtract to find the percentage that fall within the range:
```{python}
min_percentile = scipy.stats.norm.cdf(177.8, loc=mu, scale=sigma)
max_percentile = scipy.stats.norm.cdf(185.4, loc=mu, scale=sigma)
max_percentile - min_percentile
```
Output: 0.3420946829459531

34.2% of US males is between 5'10" and 6'1'
