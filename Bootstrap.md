# Homework 4 Bootstrap
Vinh Le  
June 1, 2016  

# Bootstrap for normal distribution with unequal sample size

```r
x<-rnorm(50,22,5)
y<-rnorm(40,20,4)
xbar <- mean(x)
ybar <- mean(y)
meandiff <- xbar- ybar
deviationX<-sd(x)
deviationY<-sd(y)
```

```r
xbar
```

```
## [1] 21.79892
```

```r
ybar
```

```
## [1] 19.7948
```

```r
meandiff
```

```
## [1] 2.004113
```

```r
deviationX
```

```
## [1] 5.636067
```

```r
deviationY
```

```
## [1] 3.64889
```

```r
bootnorm<-numeric(1000) #initialize bootnorm vector to have 1000 spots in it. # Run loop 1000 times
for (i in 1:1000){
bootsample1 <- sample(x, size=length(x), replace=T)
bootsample2 <- sample(y, size=length(y), replace=T)
bootmean = mean(bootsample1) - mean(bootsample2) # the mean difference between two samples
bootnorm[i] <- bootmean # put 1000 mean difference from the boot samples into bootnorm
}
```

```r
mean(bootnorm) # This value should be close to meandiff
```

```
## [1] 1.995415
```

```r
sd(bootnorm) # This will give the standard deviation for bootnorm
```

```
## [1] 1.006797
```

```r
hist(bootnorm) # histogram of bootnorm
```

![](Bootstrap_files/figure-html/unnamed-chunk-4-1.png)<!-- -->

# Bootstrap for exponential distribution with unequal sample size


```r
xexp<-rexp(50)
yexp<-rexp(40)
xexpbar <- mean(xexp)
yexpbar <- mean(yexp)
meanexpdiff <- xexpbar- yexpbar
deviationXexp<-sd(xexp)
deviationYexp<-sd(yexp)
```

```r
xexpbar
```

```
## [1] 0.9419045
```

```r
yexpbar
```

```
## [1] 1.072969
```

```r
meanexpdiff
```

```
## [1] -0.1310649
```

```r
deviationXexp
```

```
## [1] 0.8275953
```

```r
deviationYexp
```

```
## [1] 1.055587
```

```r
bootexp<-numeric(1000) #initialize bootnorm vector to have 1000 spots in it. 
# Run loop 1000 times
for (i in 1:1000){
bootexpsample1 <- sample(xexp, size=length(xexp), replace=T)
bootexpsample2 <- sample(yexp, size=length(yexp), replace=T)
bootexpmean = mean(bootexpsample1) - mean(bootexpsample2) # the mean difference between two samples
bootexp[i] <- bootexpmean # put 1000 mean difference from the boot samples into bootexp
}
```

```r
mean(bootexp) # This value should be close to meanexpdiff
```

```
## [1] -0.1298894
```

```r
sd(bootexp) # This will give the standard deviation for bootexp
```

```
## [1] 0.2034324
```

```r
hist(bootexp) # histogram of bootexp
```

![](Bootstrap_files/figure-html/unnamed-chunk-8-1.png)<!-- -->

# Summary
### The central limit theorem states that if we draw enough samples from the population then the sampling distribution of the mean of the sample will be normal and the deviation of the distribution is smaller than the orignal. The idea behind the bootstrap is that we treat the orignal sample as the population and then resample from the population many times to give us a better approximation of the sampling distribution. The evidence supports the central limit theorem because the mean of these random samples is very close to the theoretical mean and their distribution is roughly normal. The standard deviation decreases so the variance in the distribution is smaller smaller than the original. 
