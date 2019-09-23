[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> REPLACE THIS TEXT WITH YOUR RESPONSE
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

preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]
firsts = live[live.birthord == 1]
others = live[live.birthord != 1]

def CohenEffectSize(group1, group2):
    """Computes Cohen's effect size for two groups.
    
    group1: Series or DataFrame
    group2: Series or DataFrame
    
    returns: float if the arguments are Series;
             Series if the arguments are DataFrames
    """
    diff = group1.mean() - group2.mean()

    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)

    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / np.sqrt(pooled_var)
    return d
    
CohenEffectSize(firsts['totalwgt_lb'], others['totalwgt_lb'])

-0.088672927072602

The Cohen's effect size for totalwgt_lb between first babies and others is -0.0887, which is an effect approximately three times greater than pregnancy length (0.0289). This means that first babies tend to weigh 0.0887 standard deviations less than other babies.
