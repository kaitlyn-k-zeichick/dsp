[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

    import math
    import firsts 
    import ThinkStats2

    def CohenD(group1, group2):
      
        len_group1 = len(group1)
        len_group1 = len(group2)
    
        pooled_std = ((len_group1 * var_group1) + (len_group2 * var_group2)) / (len_group1 + len_group2) 
        d = mean_diff / math.sqrt(pooled_std)
        return d
    
        mean_diff = group1.mean() - group2.mean()
    
        var_group1 = group1.var()
        var_group2 = group2.var()
    
        pooled_std = ((len_group1 * var_group1) + (len_group2 * var_group2)) / (len_group1 + len_group2) 
        d = mean_diff / math.sqrt(pooled_std)
        return d
    
    group1 = firsts.totalwgt_lb
    group2 = totalothers.totalwgt_lb
  
    CohenD(group1,group2)

Description: Above is the code to find Cohen's d for the weight of babies born first versus other babies.
I wrote the CohenD function based on the equation for calculation cohen's d: the mean of the first group minus the mean
of the second group all divided by the square root of pooled standard deviation. I then input the weights of the 
first-born children as group1 and the weights of the other children as group2.

Results: The resulting Cohen's d was -.08. This was similar to the result for the effect size of pregnancy length, which was
.029.

