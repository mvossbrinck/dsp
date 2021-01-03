[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> Question: Using the variable totalwgt_lb, investigate whether first babies are lighter or heavier than others. Compute Cohen’s effect size to quantify the difference between the groups. How does it compare to the difference in pregnancy length?

First step is to find the means of birth weights for first babies vs other babies:
```{python}
firsts.totalwgt_lb.mean(), others.totalwgt_lb.mean()
```
Output: (7.201094430437772, 7.325855614973262)

We then calculate the Cohen's effect size:
```{python}
CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb)
```
Output: -0.088672927072602

While mean pregnancy length is slightly longer for first babies, the mean birth weight for first babies is about 0.12 lbs less than other babies. Based on the Cohen's effect size calculation, the difference is the means is 0.089 standard deviations, but in the opposite way of pregnancy length since birth weight mean for first babies is lower rather than higher. Although there is a bigger relative difference in the means of birth weights between first babies and other babies than between the means of pregnancy lengths for first babies compared to other babies, the effect is still not very large. 
