# R Language  matrice's
## matrix to data.frame conversion
### with usage notes.

First read in your demo.csv file into a variable popmatrix.
Then find means and sum of columns using the apply command.

```r
popmatrix <- read.csv("demo.csv")
colMeans <- apply(popmatrix,2,mean)
colSum <- apply(popmatrix,2,sum)
```
Convert popmatrix to a data.frame & view the first few lines
```sh
pop.df <- data.frame(popmatrix)
head(pop.df)
```
What are the names of the columns?
```r
names(pop.df)
```
How many rows and how many columns are there in this dataset?
```r
nrow(pop.df)
ncol(pop.df)
```

What is the average age, weight and height of this data.matrix ?
Remember that column 1 (pop.df$Sex) is a factor , while column 
2 to 4 are numeric so an average can be calculated.

```sh
apply(pop.df[,2:4],Sex,mean)
```

In order to NOT use the long format for data.frames as shown below : 
```sh
pop.df$age 
pop.df$weight 
pop.df$height 
```

Use the attach() command to just use age,weight and height for variable names.

 
What is the average age, weight and height by sex ?
```sh
attach(pop.df)
by(pop.df[,2:4],Sex,colMeans)
```
What is the average weight by sex?
```sh
with(pop.df,tapply(weight,Sex,mean))
```

Uses
> If you need a sample data table to work with
> If you need commands to work with a table or data.matrix but
> can't remember what commands go with which matrix or data.frame' then
> this is the download for you.

This git hub project is to quickly get up and running using and reading text files specifically in the csv format.

### Version
0.0.1


### Todo's

 - Write Tests
 - Add more matrix commands
 - Add Code Comments
 - Add more matrix functions
 - Add more data.frame functions

License
----
MIT. Copyright (c) 2013 - 2014  by Carlos Martinez
