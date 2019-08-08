---
title: "week_3_notes"
author: "Veronica Thompson"
date: "July 18, 2019"
output: 
  html_document: 
    keep_md: yes
---


##General R usage questions:  

**Q: Do you have to assign your own header in R when you upload your data?**  

Nope! When I am using my own data in R I input data into excel and make sure there are no funky formatting things that might confuse R. Then I save a copy of my file as a CSV to make extra sure that it is in a format that is easy for R to interpret. My go-to data import line is `read.csv()`. The first row of data in my file document becomes the header of my data frame by default. A template excel file is really useful if you want to make sure that column names and formats are consistent between experiments so your code is super easy to reuse.  


## dplyr basics

The functions (from 5.3.1):  
* Pick observations by their values **(filter())**.  
* Reorder the rows **(arrange())**.  
* Pick variables by their names **(select())**.  
* Create new variables with functions of existing variables **(mutate())**.  
* Collapse many values down to a single summary **(summarise())**.  

## filter()  
Subset your data by **rows**  
finds rows with specific values for specific columns.  

## arrange()  
put your rows in order
use the values in one or more columns to order the rows.
Values can be any class and arranged in assending or descending order
NAs will appear at the end  

## select()  
subset your data by **columns**  
makes data sets easier to manage for your human brain. Also useful when changing the "shape" of your data (chapter 10?)  

## mutate()  
make new variables!  

## summarise()  
condense all ouf your data into one row  
Best when used with **group_by()** and pipes  
pipes tell R "pick up this object and keep working with it, without putting it down"  
```
flights %>%
  group_by(carrier) %>%
  summarise(delay)
```
