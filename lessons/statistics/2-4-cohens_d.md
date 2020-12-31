[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

    import math

    def CohenD(group1, group2):
      
        len_gropu1 = len(group1)
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
    
    group1 = totalwgt_lb > totalwgt_lb.mean()
    group2 = totalwgt_lb <= totalwgt_lb.mean()
  
    CohenD(group1,group2)
