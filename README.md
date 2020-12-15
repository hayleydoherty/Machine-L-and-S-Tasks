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
To complete this task, the difference between the way you would use the 2 versions of Excel's STDEV is discussed as well as the difference in their formulas. Then an array was made that represents a sample of a population and its STDEV was calculated using Excel's STDEV.s and NumPy's SD formula.
When the SD of an array is calculated using the default NumPy formula the result = 0.9521904571390466; when SD is calculated in Excel using STDEV.S, SD= 0.9856107606. As the Excel formula takes into account the fact that the array is a sample of the population data, it would suggests that this calculation is more accurate compared to the NumPy formula.


### Task 4: $k$-means Clustering
---
This task involves using a machine learning technique, $k$-means clustering, to make predictions as to which species of Iris a set of measurements comes from. 
To complete this task, I first imported the data set with Pandas, located the rows of interest and applied the $k$-means clustering method from the sklearn package.
```
                kmeans = skcl.KMeans(n_clusters=3, random_state=0).fit(x)
```
kmeans.labels_ then lebelled each of the 150 data points with their corresponding cluster, i.e. 0= Iris-Versicolor, 1= Iris-Setosa and 2= Iris-Virginica. To determine the accuracy of the clustering, I split the labels array into 3 in order to separate the clusters and added each separate array to compare it to the total number expected for the cluster(I could do this as the data was ordered in their iris species when entered into the .fit method). From this I found that 16 point were clustered incorrectly meaning this model is 89.333% accurate. (There is probably a simpler way to do that but it was the easiest way I could think of.)
Next I used the kmeans.predict method to predict which cluster 2 made-up data points would be grouped into using the clusters made from the Iris data set. 
```
                testPoints = np.array([[5.3, 2.8, 4.8, 1.0], [6.8, 2.5, 5.2, 1.8]])
                predictions = kmeans.predict(testPoints)
                predictions
```
One of the test points was added to the Versicolor cluster and the other was added to the Virginica cluster. Below is a graph of the 3 clusters as well as the test points. 


































