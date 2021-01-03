[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

    import random
    import thinkstats2
    
    #Create a list with 1000 random numbers
    random_list = []
    for _ in range(1000):
        random_list.append(random.random())
        
    #Make a Cdf with the list of random numbers
    random_cdf = thinkstats2.Cdf(random_list)
    
    #Plot the Cdf of random numbers
    thinkplot.Cdf(random_cdf)
    thinkplot.Show(xlabel='percentile rank', ylabel='CDF')
    
    #Make a Pmf with the list of random numbers
    random_pmf = thinkstats2.Pmf(random_list)

    #Plot the Pmf of random numbers
    thinkplot.PrePlot(2)
    thinkplot.Pmf(random_pmf)
    thinkplot.Show(xlabel='number', ylabel='PMF')
    

