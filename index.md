---
title       : Data Structures & Subsetting
subtitle    : Based on material by Hadley Wickham
author      : Sunanda Garg
job         : 
logo        : r_image.png
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [quiz, bootstrap]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
---

## Data Structures[^1]

|    | Homogeneous   | Heterogeneous |
|----|---------------|---------------|
| 1d | Atomic vector | List          |
| 2d | Matrix        | Data frame    |
| nd | Array         |               |
 
#### Source: [Advanced R Programming](http://adv-r.had.co.nz/Data-structures.html) by Hadley Wickham

<br/>
Understanding data structures is very boring but very **important** :)



---&twocol

## Atomic Vectors

*** =left
    Vector Types

* __Logical__
* __Integer__
* __Double__
* __Character__
* __Complex__
* __Raw__

*** =right
    Creating Vectors

Vectors are created using the command `c()`    


```r
log <- c(TRUE, FALSE)
inte <- c(1L, 2L)
doub <- c(2.3, 4.6, 7.9)
string <- c("a", "b", "c")
```

---
## Structural Tests

Try the commands `typeof()` & `str()`

```r
typeof(logi)
str(inte)
```


Other commands to figure out the structure of a vector are `is.double()`,`is.logical()` etc.

```r
is.double(doub)
```

```
[1] TRUE
```

```r
is.double(string)
```

```
[1] FALSE
```

---
## Coercion

### Atomic Vectors are **homogenous**

Try creating a few mixed vectors and determine their types


```r
mixed_1 <- c(1, T)
mixed_2 <- c("Sunanda", 25)
```


Homogenous data structures do not allow different types of data to be clumped together.

---
## Subsetting Vectors

Subsetting means extracting certain observations you are interested in and there are various ways to do it


```r
my_vector <- c("blue", "green", "yellow")

my_vector[2]

named_vec <- c(color = "green", type = "light")  ##each element can have a name associated to it

names(named_vec)  ##an attribute of the vector

named_vec["color"]

```


---
## Conditional Subsetting


```r
num_vec <- c(1:10, 20:35)  ##numeric vector

num_vec[num_vec > 15]
```

```
 [1] 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35
```

```r

num_vec[num_vec < 15 | num_vec > 30]  #or seperation
```

```
 [1]  1  2  3  4  5  6  7  8  9 10 31 32 33 34 35
```

```r

```


---
## Lists

### Lists are a type of vector **BUT** can contain any type of vector i.e. heterogenous

```r
my_list <- list(log, doub, inte, string)
new_list <- list(my_list, c(1, 2, 3, 4))  ##list in a list
```


Try out these commands

```r
str(my_list)
```

```
List of 4
 $ : logi [1:2] TRUE FALSE
 $ : num [1:3] 2.3 4.6 7.9
 $ : int [1:2] 1 2
 $ : chr [1:3] "a" "b" "c"
```


```r
is.recursive(new_list)
```

---
## Dataframes
<br/>
- Dataframes are a 'special' type of list where each vector is equi-length
- Dataframes are always 2-dimensional (row and columns)
<br/>
<br/>

### Try to create the dataframe in the same way as the list using the `data.frame()` function

### What error do you get?


---
## Getting Help

For getting the R Documentation on any R function simply type `?[function_name]`

For additional help, usually google is the best resource.

A lot of forums like **stackoverflow** have very active R user communities.

---
## Working with a Dataframe

#### Setting the working directory

```r
## set the working directory
setwd("//filer001.office.nugg.ad/Data/Statistik/RPTN/Learning/R/Lerngruppe")

my_data <- read.table("data_s.csv", sep = "\t", header = T)

```


**read.table() Options**
- _file_ :name of the file to be read
- _sep_ :how the data is seperated
- _header_ :whether data has column names of not
.. and many others. Try ?read.table

---

## Subsetting Dataframe

R has an indexing system, which makes it pretty easy to extract information



```r
## 4th row, & 5th column
my_data[4, 5]

new_data <- subset(my_data, s4n > 20)

dim(new_data)  ##dimensions of the newly created data

```


---middle
## Thats all for this time..


For more information: Advanced R Programming by Hadley Wickham (Chapter: Data Structures)








