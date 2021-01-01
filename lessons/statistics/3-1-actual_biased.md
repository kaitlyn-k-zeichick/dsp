[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

    import thinkplot
    import thinkstats2
    
    #Biased Pmf function
    def BiasPmf(pmf, label):
    new_pmf = pmf.Copy(label=label)

    for x, p in pmf.Items():
        new_pmf.Mult(x, x)
        
    new_pmf.Normalize()
    return new_pmf

    #Unbiased Pmf function
    def UnbiasPmf(pmf, label):
        new_pmf = pmf.Copy(label=label)

        for x, p in pmf.Items():
            if x == 0:
                new_pmf.Mult(x, x)
            else:
                new_pmf.Mult(x, 1.0/x)
        
        new_pmf.Normalize()
        return new_pmf
        
    resp = nsfg.ReadFemResp() #read in the data from ReadFemResp
    d = resp['numkdhh'] #save the response data from children about their siblings as series 'd'
    pmf = thinkstats2.Pmf(d, label='actual') #turn the 'd' series data into a pmf
        
        
    #Print Means    
    unbiased = UnbiasPmf(biased_pmf, label='unbiased')
    print('Unbiased mean', unbiased.Mean())
    print('Actual mean', pmf.Mean())
    print('Observed mean', biased_pmf.Mean())
    
    #Plot Actual and Observed distributions
    biased_pmf = BiasPmf(pmf, label='observed')
    thinkplot.PrePlot(2)
    thinkplot.Pmfs([pmf, biased_pmf])
    thinkplot.Show(xlabel='class size', ylabel='PMF')
    
Results: The actual mean for the number of children in a household was 1.02. The biased/observed mean was 2.4. The 
unbiased mean was 1.9. 

Plotted observed and actual distributions: 

![Image of plotted and actual distributions](https://github.com/kaitlyn-k-zeichick/dsp/blob/master/img/ch3_exercise.png)


