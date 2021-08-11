To see the date function in R we have to install the "tidyverse" package by typeing 
install.packages("tidyverse")
then  library(tidyverse)
and then 
       library(lubridate)
       to manipulate with date and time functions in R.
       Let's see 1st function today() to see the today's date
       
    today()
    
you will see following result->
  [1] "2021-08-11"
  
Then to see today's date plus current time we have to execute now() function then we get today's date plus current time

now()
  you will see following result->
[1] "2021-08-11 18:35:21 IST"

-When working with R, there are three ways you are likely to create date-time formats: 

From a string

From an individual date

From an existing date/time object

R creates dates in the standard yyyy-mm-dd format by default. 

Converting from strings :-

    Date/time data often comes as strings. You can convert strings into dates and date-times using the tools provided by lubridate. These tools automatically work out the date/time format. First, identify the order in which the year, month, and day appear in your dates. Then, arrange the letters y, m, and d in the same order. That gives you the name of the lubridate function that will parse your date. For example, 
    for the date 2021-01-20, you use the order ymd:

   ymd("2021-08-11")
ymd("2021-01-20")

When you run the function, R returns the date in yyyy-mm-dd format. 

 [1] "2021-01-20"

It works the same way for any order. For example, month, day, and year. R still returns the date in yyyy-mm-dd format.

mdy("January 20th, 2021")

 [1] "2021-01-20"
 Or, day, month, and year. R still returns the date in yyyy-mm-dd format.

dmy("20-Jan-2021")

 [1] "2021-01-20"

These functions also take unquoted numbers and convert them into the yyyy-mm-dd format.

ymd(20210120)

 [1] "2021-01-20"
 If you try any date it will print the date but the condition is that you must have to type valid date 
 for example if you give 34 for date it gives error similarly if you give 13 for month it also gives error like 
 ymd(11111332)

*warning message:
All formats failed to parse. No formats found.
but if you give 
 ymd(12340630)
It gives 
[1] "1234-06-30"
means here as you noticed for y we gave 1234 which is valid for m- we gave 06 which is also valid because this is the 6th month means june month
and for day we gave 30 which is also valid but if we gave 29 instead of 30 in the day for february month that is 2nd month let's see what happens
ymd(12340229)
NA
Warning message:
It again gaves failed to parse
because in that year the the day 29 is not present in feb month let's see changing day from 29 to 28 what happens
ymd(12340228)
Bingo!!!!!!
it's present in that year 
result is 
[1] "1234-02-28"
Let's see changing the year and putting day equal to 29 what happens
ymd(12350229)
again failed let's see when the day 29 present in the feb month in which year 
ymd(12360229)
yes it's present in the year 1236 means we can say after every 4 years there will have 29 day in the feb month
If we type following code then it will also gives the date because we are adding 4 in that date which returns us the leap year.
ymd(12360229)+4

