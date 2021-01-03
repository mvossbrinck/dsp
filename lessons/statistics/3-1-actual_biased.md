[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>> Question: Something like the class size paradox appears if you survey children and ask how many children are in their family. Families with many children are more likely to appear in your sample, and families with no children have no chance to be in the sample. Use the NSFG respondent variable numkdhh to construct the actual distribution for the number of children under 18 in the respondents' households. Now compute the biased distribution we would see if we surveyed the children and asked them how many children under 18 (including themselves) are in their household. Plot the actual and biased distributions, and compute their means.

The data source was created already:
```{python}
resp = nsfg.ReadFemResp()
```

We first calculate the actual distribution for the number of children under 18 in the household:
```{python}
numkdhh_pmf = thinkstats2.Pmf(resp.numkdhh)
```

We then calculate the biased distribution:
```{python}
biased_pmf = BiasPmf(numkdhh_pmf, label = "observed")
```

We then plot the actual distribution:
```{python}
thinkplot.Pmf(numkdhh_pmf)
```
![actual distribution](https://github.com/mvossbrinck/dsp/blob/master/img/household_kids_pmf.png)

We then plot the biased distribution:
```{python}
thinkplot.Pmf(biased_pmf)
```
![biased distribution](https://github.com/mvossbrinck/dsp/blob/master/img/household_kids_pmf_biased.png)

Lastly, we find the means of both distributions:
```{python}
print('Actual mean', numkdhh_pmf.Mean())
print('Observed mean', biased_pmf.Mean())
```
Output:

Actual mean 1.024205155043831

Observed mean 2.403679100664282

The observed mean is more than twice as high as the actual mean.
