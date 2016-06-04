# Homework 4 Bootstrap
Vinh Le  
June 1, 2016  
# Boostrap for normal distribution with sample size 50

```r
x1<-rnorm(50,22,5)
xbar1 <- mean(x1)
deviationX1<-sd(x1)
```


```r
xbar1 # average value of x1 vector
```

```
## [1] 22.16969
```

```r
deviationX1 # standard deviation of x1
```

```
## [1] 6.461591
```


```r
bootnormX1<-numeric(1000) #initialize bootnorm vector to have 1000 spots in it. # Run loop 1000 times
for (i in 1:1000){
bootsampleX1 <- sample(x1, size=length(x1), replace=T)
bootmeanX1 = mean(bootsampleX1)
bootnormX1[i] <- bootmeanX1 # put 1000 mean into bootnorm vector
}
```


```r
mean(bootnormX1) # This value should be close to xbar1
```

```
## [1] 22.2223
```

```r
sd(bootnormX1) # This will give the standard deviation for bootnormX
```

```
## [1] 0.9165923
```

```r
hist(bootnormX1) # histogram of bootnormX
```

![](Bootstrap_files/figure-html/unnamed-chunk-4-1.png)<!-- -->

# Boostrap for normal distribution with sample size 40

```r
x2<-rnorm(40,22,5)
xbar2 <- mean(x2)
deviationX2<-sd(x2)
```


```r
xbar2 # average value of x2 vector
```

```
## [1] 22.69943
```

```r
deviationX2 # standard deviation of x2
```

```
## [1] 5.016299
```


```r
bootnormX2<-numeric(1000) #initialize bootnorm vector to have 1000 spots in it. # Run loop 1000 times
for (i in 1:1000){
bootsampleX2 <- sample(x2, size=length(x2), replace=T)
bootmeanX2 = mean(bootsampleX2)
bootnormX2[i] <- bootmeanX2 # put 1000 mean into bootnormX2 vector
}
```


```r
mean(bootnormX2) # This value should be close to xbar2
```

```
## [1] 22.67686
```

```r
sd(bootnormX2) # This will give the standard deviation for bootnormX2
```

```
## [1] 0.7971501
```

```r
hist(bootnormX2) # histogram of bootnormX2
```

![](Bootstrap_files/figure-html/unnamed-chunk-8-1.png)<!-- -->

# Bootstrap for normal distribution with two unequal sample size

```r
x1<-rnorm(50,22,5)
x2<-rnorm(40,20,4)
xbar1 <- mean(x1)
xbar2 <- mean(x2)
meandiffX <- xbar1- xbar2
deviationX1<-sd(x1)
deviationX2<-sd(x2)
```


```r
xbar1 # average value of x1
```

```
## [1] 21.8122
```

```r
xbar2 # average value of x2
```

```
## [1] 20.51664
```

```r
meandiffX # the mean difference between two samples
```

```
## [1] 1.295557
```


```r
bootnormX<-numeric(1000) #initialize bootnorm vector to have 1000 spots in it. # Run loop 1000 times
for (i in 1:1000){
bootsampleX1 <- sample(x1, size=length(x1), replace=T)
bootsampleX2 <- sample(x2, size=length(x2), replace=T)
bootmeanX = mean(bootsampleX1) - mean(bootsampleX2) # the mean difference between two samples
bootnormX[i] <- bootmeanX # put 1000 mean difference from the boot samples into bootnorm
}
```


```r
mean(bootnormX) # This value should be close to meandiffX
```

```
## [1] 1.240844
```

```r
hist(bootnormX) # histogram of bootnormX
```

![](Bootstrap_files/figure-html/unnamed-chunk-12-1.png)<!-- -->

# Boostrap for expenential distribution with sample size 50


```r
yexp1<-rexp(50)
ybar1 <- mean(yexp1)
deviationYexp1<-sd(yexp1)
```


```r
ybar1 # average value of ybar1
```

```
## [1] 0.8461923
```

```r
deviationYexp1 # the standard deviation of yexp1
```

```
## [1] 0.9013435
```


```r
bootexp1<-numeric(1000) #initialize bootnorm vector to have 1000 spots in it. # Run loop 1000 times
for (i in 1:1000){
bootsampleYexp1 <- sample(yexp1, size=length(yexp1), replace=T)
bootmeanExp1 = mean(bootsampleYexp1)
bootexp1[i] <- bootmeanExp1 # put 1000 mean into bootexp vector
}
```


```r
mean(bootexp1) # This value should be close to ybar1
```

```
## [1] 0.8449283
```

```r
sd(bootexp1) # This will give the standard deviation for bootexp1
```

```
## [1] 0.1265022
```

```r
hist(bootexp1) # histogram of bootexp
```

![](Bootstrap_files/figure-html/unnamed-chunk-16-1.png)<!-- -->

# Boostrap for exponential distribution with sample size 40


```r
yexp2<-rexp(40)
ybar2 <- mean(yexp2)
deviationYexp2<-sd(yexp2)
```


```r
ybar2 # the average value of ybar2 vector
```

```
## [1] 1.282525
```

```r
deviationYexp2 # the standard deviation of yexp2
```

```
## [1] 1.404775
```


```r
bootexp2<-numeric(1000) #initialize bootnorm vector to have 1000 spots in it. # Run loop 1000 times
for (i in 1:1000){
bootsampleYexp2 <- sample(yexp2, size=length(yexp2), replace=T)
bootmeanExp2 = mean(bootsampleYexp2)
bootexp2[i] <- bootmeanExp2 # put 1000 mean into bootexp2 vector
}
```


```r
mean(bootexp2) # This value should be close to ybar2
```

```
## [1] 1.281661
```

```r
sd(bootexp2) # This will give the standard deviation for bootexp2
```

```
## [1] 0.2183648
```

```r
hist(bootexp2) # histogram of bootexp2
```

![](Bootstrap_files/figure-html/unnamed-chunk-20-1.png)<!-- -->

# Bootstrap for exponential distribution with unequal sample size


```r
yexp1<-rexp(50)
yexp2<-rexp(40)
Yexpbar1 <- mean(yexp1)
Yexpbar2 <- mean(yexp2)
meanexpdiff <- Yexpbar1- Yexpbar2
deviationYexp1<-sd(yexp1)
deviationYexp2<-sd(yexp2)
```


```r
Yexpbar1 # average value of yexp1
```

```
## [1] 0.7989176
```

```r
Yexpbar2 # average value of yexp2
```

```
## [1] 0.8685822
```

```r
meanexpdiff # the mean difference between yexp1 and yexp2 
```

```
## [1] -0.06966457
```


```r
bootexpY<-numeric(1000) #initialize bootnorm vector to have 1000 spots in it. 
# Run loop 1000 times
for (i in 1:1000){
bootexpsampleY1 <- sample(yexp1, size=length(yexp1), replace=T)
bootexpsampleY2 <- sample(yexp2, size=length(yexp2), replace=T)
bootexpmeanY = mean(bootexpsampleY1) - mean(bootexpsampleY2) # the mean difference between two samples
bootexpY[i] <- bootexpmeanY # put 1000 mean difference from the boot samples into bootexpY
}
```


```r
mean(bootexpY) # This value should be close to meanexpdiff
```

```
## [1] -0.06859636
```

```r
sd(bootexpY) # This will give the standard deviation for bootexp
```

```
## [1] 0.1910158
```

```r
hist(bootexpY) # histogram of bootexp
```

![](Bootstrap_files/figure-html/unnamed-chunk-24-1.png)<!-- -->

# Summary
### The central limit theorem states that if we draw enough samples from the population then the sampling distribution of the mean of the sample will be normal and the deviation of the distribution is smaller than the orignal. The idea behind the bootstrap is that we treat the orignal sample as the population and then resample from the population many times to give us a better approximation of the sampling distribution. The evidence supports the central limit theorem because the mean of these random samples is very close to the theoretical mean and their distribution is roughly normal. The standard deviation decreases so the variance in the distribution is smaller than the original. 
