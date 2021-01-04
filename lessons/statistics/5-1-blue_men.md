[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

    import scipy
    import brfss
    from scipy import stats
    from scipy.stats import norm
    
    #Make the Cdf of male heights
    df = brfss.ReadBrfss()
    brfss.CleanBrfssFrame(df)
    only_male = df[df['sex'] == 1]
    male_heights = only_male['htm3']
    cdf = thinkstats2.Cdf(male_heights, label='maleheights')
    
    mu = 178
    sigma = 7.7
    dist = scipy.stats.norm(loc=mu, scale=sigma)

    five_ten = dist.cdf(177.8) 
    six_one = dist.cdf(185.4) 
    print(six_one-five_ten)
    
Result: 34.2% of men are between the heights of 5'10" and 6'1"
