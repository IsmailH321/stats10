Practical 10 : Non Parametric Test

Kruskal Wallis Test

> my_data <- PlantGrowth
> head(my_data)
  weight group
1   4.17  ctrl
2   5.58  ctrl
3   5.18  ctrl
4   6.11  ctrl
5   4.50  ctrl
6   4.61  ctrl
> kruskal.test(weight ~ group, data = my_data)

        Kruskal-Wallis rank sum test

data:  weight by group
Kruskal-Wallis chi-squared = 7.9882, df = 2, p-value = 0.01842

Wilcoxon Test

> pairwise.wilcox.test(PlantGrowth$weight, PlantGrowth$group,p.adjust.method = "BH")

        Pairwise comparisons using Wilcoxon rank sum test with continuity correction 

data:  PlantGrowth$weight and PlantGrowth$group 

     ctrl  trt1 
trt1 0.199 -    
trt2 0.095 0.027

P value adjustment method: BH 
Warning message:
In wilcox.test.default(xi, xj, paired = paired, ...) :
  cannot compute exact p-value with ties

Mann Whitney Test

>  mtcars$mpg 
 [1] 21.0 21.0 22.8 21.4 18.7 18.1 14.3 24.4 22.8 19.2 17.8 16.4 17.3 15.2 10.4 10.4 14.7 32.4 30.4
[20] 33.9 21.5 15.5 15.2 13.3 19.2 27.3 26.0 30.4 15.8 19.7 15.0 21.4
> mtcars$am 
 [1] 1 1 1 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1 1 1 0 0 0 0 0 1 1 1 1 1 1 1
> wilcox.test(mpg ~ am, data=mtcars)

        Wilcoxon rank sum test with continuity correction

data:  mpg by am
W = 42, p-value = 0.001871
alternative hypothesis: true location shift is not equal to 0

Warning message:
In wilcox.test.default(x = c(21.4, 18.7, 18.1, 14.3, 24.4, 22.8,  :
  cannot compute exact p-value with ties

Sign Test
                             
>  binom.test(5, 18) 

        Exact binomial test

data:  5 and 18
number of successes = 5, number of trials = 18, p-value = 0.09625
alternative hypothesis: true probability of success is not equal to 0.5
95 percent confidence interval:
 0.09694921 0.53480197
sample estimates:
probability of success 
             0.2777778
