[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

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


pmf_rand = np.random.random(1000)

pmf_2 = thinkstats2.Pmf(pmf_rand, label = 'random')
thinkplot.Pmf(pmf_2,linewidth = .1)
thinkplot.Config(xlabel = 'Value', ylabel = 'PMF')


cdf = thinkstats2.Cdf(pmf_rand, label = 'random')
thinkplot.Cdf(cdf)
thinkplot.Config(xlabel = 'Random', ylabel = 'CDF')



Because there are so many values, the PMF is 'noisy', meanining it is difficult to see the differences between each value. The CDF shows a clearer picture that indicates the distribution is normal due to it's linearity.
