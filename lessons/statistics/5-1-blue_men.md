[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> 
import scipy.stats

mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc = mu, scale = sigma)

def height_to_cm(feet, inches):
    height_inch = feet * 12 + inches
    height_cm = height_inch * 2.54
    return height_cm
    
blue_man_min = height_to_cm(5,10)
blue_man_max = height_to_cm(6,1)

(dist.cdf(blue_man_max) - dist.cdf(blue_man_min)) * 100

34.27468376314746
