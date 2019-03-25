# numpy
## creating arrays
### basic arrays
1. create an array of 5 numbers of your choice
2. create a 3x3 array of any numbers using list comprehension
3. create a length 10 integer array filled with zeros
4. create a 3x5 float array filled with ones
5. create a 3x5 array filled with 3.14s
6. create an array filled with a linear sequence starting at 0 and ending at 20, 2-stepped
7. create an array of 4 values evenly spaced between 0 and 1
8. create a 3x3 identity matrix

### random arrays
1. create a 3x3 array of uniformly random numbers between 0 and 1
2. do the same but with standard normally distributed values
3. do the same but with randome integers in the intervale [0,10)

# Array Attributes
```
np.random.seed(0)
x1 = np.random.randint(10, size=6)
x2 = np.random.randint(10, size=(3,4))
x3 = np.random.randint(10, size=(3,4,5))
```
1. for each of the above arrays output the following

	a. the number of dimensions
	b. the size of each dimension
	c. the number of elements in the array
2. output the data type of the array

# Array indexing
## Single element indexing
1. find the first element of x1
2. find the 5th element of x1
3. find the last element of x1
4. find the last but one element of x1
5. find the element in the first row and first column of x2
6. find the element in the 3rd row and first column of x2
7. find the element in the 3rd row and last column of x2
8. set the first element of x2 to 12 and check the array
9. try to set the first element of x2 to 3.141 and check the array. Why didn't it work?

## Slicing and Accessing subarrays
### One Dimensional
`x = np.arange(10)`
1. return the first 5 elements of x
2. return the elements after index 5
3. return the middle subarray (i.e. the 5th to the 7th elements)
4. return every other element
5. return every other element starting at 1
6. return all elements of the array, but reversed
7. return the elements with value 5, 3 and 1 in that order.

### Multi Dimensional
1. return an array which has the first two rows and first 3 columns of x2
2. return an array which has all rows and every other column
3. return the entire array, reversed
4. return the first column
5. return the first row - syntax should be as compact as possible
6. store a subarray of x2 with the first 2 rows and first 2 columns. Modify one element of the subarray. Print the x2. Why did the value change in x2?
7. now store an array of x2 with the first two rows and first two columns, but do it as a defensive copy

## Reshaping arrays
1. print a 3x3 array with the numbers 1 to 9 (use reshape syntax) 
`x = np.array([1,2,3])`
2. reshape the one dimensional x into a multidimensional array with 1 row and 3 columns
3. do the same using newaxis syntax
4. reshape x into a 3 row, 1 column mdim array, using both reshape and newaxis

## Concatenating
```
x = np.array([1,2,3])
y = np.array([3,2,1])
z = np.array([99,99,99])
grid = np.array([[1,2,3],[4,5,6]])
```

1. concatenate x and y into one 1d array
2. concatenate x, y and z into a 1d array
3. concatenate grid with itself so you end up with a 4 row array
4. concatenate grid with itself so you end up with a 2 row, 6 column array
5. stack x on top of grid (don't use concatenate)

`v = np.array([[99],[99]])`

6. add v as a new column on the right of grid

## Splitting
```
x = [1,2,3,99,99,3,2,1]
grid = np.arange(16).reshape((4,4))
```

1. split x into 3 arrays, `x1 = [1,2,3]`, `x2 = [99,99]`, `x3=[3,2,1]`
2. split grid into 'upper' and 'lower', having the top and bottom 2 rows respectively
3. split grid into left and right

## Computation: universal functions
`np.random.seed(0)`
1. create a function which when passed an array calculates the reciprocals.
2. time how long it takes to calculate 1,000,000 random reciprocals
3. do the same operation, but vectorised. Explain why the vectorised function is much quicker
4. create two 5 element, 1d arrays and divide one by the other
5. create a 3x3 array of the numbers 1-9. use a UFunc to create an array which has 2 to the power of each element in the array
6. create an array of the numbers 0 to 4. With an integer of your choice, perform the following ufuncs: add, subtract, mulitply, divide, floor-divide, modulo, exponent, negation
7. in a single operation use negation, multiply, addition, exponent.
8. use all these operations in a de-wrapped manner

`x=np.array([-2,-1,0,1,2])`

9. find the absolute value of this array
10. create an array of complex numbers and find the absolute value

`theta = np.linspace(0,np.pi,3)`

11.  find sin, cos and tan of theta

`x=[1,2,3]`

12. find e^x, 2^x, 3^x

`x.append(10)`

13. find ln(x), log base 2 of x, log base 10 of x

`x=[0,0.001,0.01,0.1]`

14. find e^x - 1 and log(1+x), with precision

## Specifying output
`x=np.arange(5)`

1. multiply x by 10, storing the output in a new array y.
2. raise 2 to the power of x and output in an array which has a 0 inbetween each output value - you must NOT create a temporary array

## Aggregation
`x=np.arange(1,6)`

1. reduce this array to a single element, adding each of the elements
2. create an array which stores the cumulative values resulting from adding each of the elemebts of x in order
3. find the out product of the array x with itself.

`bigarray = np.random.rand(1000000) `

4. on bigarray, time the numpy and built-in python sum functions.
5. do the same with the min and max functions
6. find the min, max and sum of bigarray using methods on the array itself (or without doing that if you did it in the first place)

## Aggregation on MDim arrays
`M=np.random.random((3,4))`

1. find the sum of all values in M
2. find the minimum value in each column of M
3. find the maximum value in each row of M

remember the axis keyword specifies the *dimension of the array that will be collapsed, not the dimension that will be returned*

[https://raw.githubusercontent.com/jakevdp/PythonDataScienceHandbook/master/notebooks/data/president_heights.csv]

4. calculate the mean, std dev, max and min of the presidents heights
5. calculate the 25th percentile, the median and the 7th percentile
6. plot a histogram of presidents heights

## Broadcasting and operations on mdim arrays
1. state the 3 rules of the broadcasting algorithm

```
M=np.ones((2,3))
a=np.arange(3)
```

2. create a 3x3 array with a column of ones, a column of 2s and a column of 3s, by using a and M
3. create a 3x3 array, [[0,1,2],[1,2,3],[2,3,4]] using using a single 1d array of [0,1,2] as a starting point
4. for questions 2 and 3, describe the shape of arrays at each step of the stretching process.

`M=np.ones((3,2))`

5. try to add M and a together. By reference to the broadcasting rules, explain why this doesn't work
6. 'correct' the oepration by modifying a in such a way that you can add a and M together.

`X=np.random.random((10,3))`

7. center this array

## Comparisons, masks and boolean logic
### Comparison operators as ufuncs
`x=np.array([1,2,3,4,5])`

1. return a mask array for values less than 3
2. return a mask array for values not equal to 3
3. return a mask array for values where 2x is the same as x^2

`x=np.random.randint(10,(3,4))`

4. how many values in x are less than 6? You should have 2 ways do this,
5. how many values in each row are less than 6
6. are there any values greater than 8?
7. are all values less than 10?
8. are all values in each row less than 8?

### Boolean operators
[https://raw.githubusercontent.com/jakevdp/PythonDataScienceHandbook/master/notebooks/data/Seattle2014.csv]
1. create a numpy array of the rainfall in inches for all 365 days. *rainfall in mm is in the 'PRCP' column of the csv. convert to inches by dividing by 254*
2. plot a histogram of the rainfall
3. list the 4 bitwise operators, what they do and their ufunc syntax
4. find how many days in 2014 had rainfall between 0.5 and 1 inches
5. calculate the same thing in a different but logically equivalent way

### Masks
1. using a masking operation, return an array of all values less than 5
2. construct a mask of all rainy days
3. construst a mask of all summer days (the 90 days from June 21st, the 172nd day)
4. using these find:
	a. the median precipitation on rainy days
	b. the mediam rain on summer days
	c. the maximum rain on summer days
	d. the median rain on non-summer rainy days


## Fancy Indexing
```
rand = np.random.RandomState(42)
x=rand.randint(100,size=10)
```

1. using FI, print elements 3, 7 and 4 of x
2. print a 2x2 array of the 3rd, 7th, 4th and 5th elements of x

`X=np.arange(12).reshape((3,4))`

3. print an array of the elements at [0,2], [1,1] and [2,3]
4. print a 3x3 array containing the elements in row 0,1 and 2, and columns 2,1 and 3.
5. by combining simple and fancy indexing, from the 2nd row return elements 2, 0 and 1
6. by combining slicing and fancy indexing, from the 1st and 2nd rows return elements 2,0,1
7. create a 1,0,1,0 mask and combine masking and FI to return a 3x2 array of all the even elements of X (including 0)

### Selecting random points
```
mean=[0,0]
cov = [[1,2],[2,5]]
X = rand.multivariate_normal(mean, cov, 100)
```
*creates 100 observations of 2 variables*

1. plot a scatter of the observations
2. select 20 random points from this, by choosing 20 random indices with no repeats
3. show which points were selected by overplotting your original graph with circles showing the selections

### using FI to modify arrays
`x=np.arange(10)`

1. replace elements 2,1,8 and 4 with the number 99
2. deduct 10 from each of these elements
3. create a 10 element of zeros, and with the mask i=[2,3,3,4,4,4] do a fancy indexed +=1 operation. Why did the operation on indices 3 and 4 only fire once?
4. use a function that, using this mask, will fire on index 3 and 4 the stated number of times

### Binning data
```
np.random.seed(42)
x=np.random.randn(100)
```

1. bin this data into 20 bins between -5 and 5
2. plot using plt.plot(x, y, linestyle='steps')
3. do the same using a native matplotlib function (histtype='step')

## Sorting arrays
`x=np.array([2,1,4,3,5])`

1. sort x using np, using inplace and non-inplace methods
2. what algorithm does np.sort use, and what others can it use when specified?
3. return the indices of the sorted elements and store as i
4. use i and fancy indexing to sort x

```
rand=np.random.RandomState(42)
X = rand.randint(0,10,(4,6))
```

5. sort each column of X
6. sort each row of X

### Partial sorts: partitioning
`x=np.array([7,2,3,1,6,5,4])`

1. create a partition with the 3 smallest elements of this array in the 1st 3 indices
2. create a partition of the 2 smallest elements of each row of (capital) X 

`X=rand.rand(10,2)`

3. compute the pairwise square-distances between each pair of points, in one line of code
4. create a 'nearest' matrix which has the row-sorted indices of the nearest pairs
5. do a lazy operation of the same to calculate the Kth nearest neighbours
6. create a dot plot of the pairs and overlay it with lines linking each to its 2 closest neigbours.

## Structured Arrays
1. using dictionary method create a structured of 4 elements with fields name (unicode of max length 10) age (integer max length 4) and weight (float of max length 8)

```
name = ['Alice', 'Bob', 'Cathy', 'Doug']
age = [25,45,37,19]
weight = [55.,85.5,68.,61.5]
```

2. fill the structured array with these values
3. get all the names in the array
4. get the first observations of the array
5. get the last name from the array	
6. get all names where the age is under 30 (use masking)
7. create the same structured array from example 1 using tuple notation
