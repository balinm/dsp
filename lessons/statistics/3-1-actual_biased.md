[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>> 
from __future__ import print_function, division

%matplotlib inline

import numpy as np
import pandas
import random
import nsfg
import first
import analytic
from collections import Counter
import thinkstats2
import thinkplot

def BiasPmf(pmf, label):
    new_pmf = pmf.Copy(label=label)

    for x, p in pmf.Items():
        new_pmf.Mult(x, x)
        
    new_pmf.Normalize()
    return new_pmf
    
resp = nsfg.ReadFemResp()

pmf = thinkstats2.Pmf(resp['numkdhh'],label = 'acutal')
biased_pmf = BiasPmf(pmf, label = 'observed')
thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf, biased_pmf])
thinkplot.Config(xlabel='Number of children', ylabel='PMF')



unbiased_mean = pmf.Mean()

biased_mean = biased_pmf.Mean()

print('Unbiased mean: {0} \nBiased mean: {1}'.format(unbiased_mean,biased_mean))

Unbiased mean: 1.024205155043831 
Biased mean: 2.403679100664282
