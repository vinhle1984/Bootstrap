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
```

```r
xbar
```

```
## [1] 22.79884
```

```r
ybar
```

```
## [1] 19.66316
```

```r
meandiff
```

```
## [1] 3.135687
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
## [1] 3.117359
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
```

```r
meanexpdiff
```

```
## [1] -0.3785525
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
## [1] -0.3814534
```

```r
hist(bootexp) # histogram of bootexp
```

![](Bootstrap_files/figure-html/unnamed-chunk-8-1.png)<!-- -->
