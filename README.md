## Machine-L-and-S-Tasks
#### Submission for Machine Learning and Statistics Tasks Assessment


### Task 1: Square root of 2 to 100 decimal places
---
The aim of this task is to write a Python function that calculates the square root of 2 and returns the answer to 100 decimal places. Newton's methos is used to calculate the square root of 2. This method produces successively better approximations of the root of a number. Below is the code used to calculate the square root of 2 with Newton's Method:
```
                        def sqrt2():
                            z = 2/2
                            while abs(2-(z * z)) > 0.000001:
                                z-= (z * z - 2)/ (2 * z)
                            return z
        
```
I compared the result output from my code with the result given by the NumPy package math to ensure that the square root was eing calculated correctly. When I was happy with this I then formatted the output so that it would be displayed to 100 decimal places:
```
                        
                            return format(z, '.100f')
        
```


### Task 2: Chi-Square
---
This task involved using a Python library, SciPy.stats, to perform Chi-squared test for independence on a set of values given as an example on the Chi-square Wikipedia page and determine if the output from this calculation matches that on Wikipedia. The data from the Wikipedia example was converted into a NumPy array, then passed into the chi-squared function from SciPy.stats. The Chi-squared statistic and *p*-value return from the function are shown below:

                            Chi Stat
                            24.5712028585826

                            P-Value
                            0.0004098425861096696

This Chi-squared matches the one from the Wikipedia example and as the *p*-value is below 0.05, this suggests that there is a significant difference between the 3 groups. 


### Task 3: STDEV.s vs. STDEV.P
---
The purpose of this task was to research the Excel functions for calculating the standard deviation (SD) of an array, STDEV.s and STDEV.P, then demonstrate why STDEV.s is a better estimate for the SD when performed on a sample compared to the NumPy formula used to calculate SD. 

When the SD of an array is calculated using the default NumPy formula the result = 0.9521904571390466; when SD is calculated in Excel using STDEV.S, SD= 0.9856107606. As the Excel formula takes into account the fact that the array is a sample of the population data, it would suggests that this calculation is more accurate compared to the NumPy formula.








































