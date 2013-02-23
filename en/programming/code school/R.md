# R

## Variables
* Assignment:
```x <- 42
* useful functions:
```sum(1, 3, 5)
```rep("Yo ho!", times = 3)
```sqrt(16)
```help(sum)
```example(min)
```sin(c(1, 99, 3))
```print(a)
```mean(c(2,3,4))
```median(c(2,3,4))
```deviation <- sd(c(2,3,4))
* vectors:
```c(4, 7, 9)
```c('a', 'b', 'c')
```c(1, TRUE, "three")
* sequences
```5:9
```seq(5, 9, 0.5)
```9:5
* matrices
```matrix(0, 3, 4)

## Plotting
```barplot(c(4, 5, 1))
```plot(x, y)
```abline(h = mean(limbs))
elevation <- matrix(1, 10, 10)
elevation[4, 6] <- 0
contour(elevation)
persp(elevation, expand=0.2)

## Factors
```
chests <- c('gold', 'silver', 'gems', 'gold', 'gems')
types <- factor(chests)
as.integer(types)
plot(weights, prices, pch=as.integer(types))
legend("topright", levels(types), pch=1:length(levels(types)))
```

## Data frames
```treasure <- data.frame(weights, prices, types)
```plot(countries$GDP, countries$Piracy)

### Retrieve the "weights" column
```treasure[["weights"]]
or
```treasure$weights

## Reading data files
CSV:
```read.csv("targets.csv")
or for other formats:
```read.table("infantry.txt", sep="\t", header=TRUE)

## linear model
```line <- lm(countries$Piracy ~ countries$GDP)

## Packages
```install.packages("ggplot2")